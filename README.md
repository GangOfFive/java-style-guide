**Table of Contents**  *generated with [DocToc](http://doctoc.herokuapp.com/)*

- [Java Style Guide for Gang of Five](#java-style-guide-for-gang-of-five)
	- [Naming Conventions](#naming-conventions)
	- [Code Formatting](#code-formatting)
		- [Blocks](#blocks)
		- [Whitespace](#whitespace)
		- [Comments](#comments)

# Java Style Guide for *Gang of Five*

Based on [Google's](http://google-styleguide.googlecode.com/svn/trunk/javaguide.html) Java style guide.

## Naming Conventions
 - Java files should be named like this:
   - `User.java`
   - `PinkUnicorn.java`
 - Use camelCase for variables, methods, and PascalCase for classes and enums.
 - Use `NAMES_LIKE_THIS` for constants.
 - Be descriptive with your naming.
 - Always declare an access modifier before each method and/or class (protected, private or public)

    ~~~java
    // bad
    List<Recipe> s(String str) {
        // ...stuff...
    }

    // good
    List<Recipe> searchRecipes(String searchTerms) {
        // ..stuff..
    }

## Code Formatting
 - Soft line length limit: 80.
 - Hard line length limit: 120.

### Blocks
 - Use braces with all multi-line blocks.

    ~~~java
    // bad
    if (test)
        return false;

    // bad
    if (test) return false;

    // good
    if (test) {
        return false;
    }

    // bad
    public boolean exists() { return false; }

    // good
    public boolean exists() {
        return false;
    }
    ~~~
 - Empty blocks. If a block is empty, do not put any spacing between the braces.
    ~~~java
    void doNothing() {}
    ~~~

### Whitespace
 - Use soft tabs set to 4 spaces

    ~~~java
    // bad
    private boolean exists() {
    ∙∙return false;
    }

    // bad
    private boolean exists() {
    ∙return false;
    }

    // good
    private boolean exists() {
    ∙∙∙∙return false;
    }
    ~~~

 - Place 1 space before the leading brace.

    ~~~java
    // bad
    protected void sayHello(){
        System.out.println("hello");
    }

    // good
    protected void sayHello() {
        System.out.println("hello");
    }
    ~~~

 - Set off operators with spaces.
    ~~~java
    // bad
    int x=y+5;

    // good
    int x = y + 5;
    ~~~

 - Place an empty newline at the end of the file.

### Comments
 - Use only the following tags for Javadoc comments:
   - @param
   - @return (do not use for methods that return void or constructors)
   - @see
   - @throws

 - Do not use comments for self-explanatory methods such as get and set methods.
 - Do not use commments for POJO classes.
 - Use one blank line before @param.
 - Treat @param and @return as a phrase
   The @param and @return should be treated as phrases rather than complete sentences.
   They should start with a lower case letter, typically using the word "the".
   They should not end with a dot.

 - Use `/** ... */` for multiline comments. Include a description, specify
   types and values for all parameters and return values.

    ~~~java
    /**
     * Returns an Image object that can then be painted on the screen. 
     * The url argument must specify an absolute {@link URL}. The name
     * argument is a specifier that is relative to the url argument. 
     * <p>
     * This method always returns immediately, whether or not the 
     * image exists. When this applet attempts to draw the image on
     * the screen, the data will be loaded. The graphics primitives 
     * that draw the image will incrementally paint on the screen. 
     *
     * @param  url  the absolute URL giving the base location of the image
     * @param  name the location of the image, relative to the url argument
     * @return      the image at the specified URL
     * @see         Image
     */
     public Image getImage(URL url, String name) {
            try {
                return getImage(new URL(url, name));
            } catch (MalformedURLException e) {
                return null;
            }
     }
    ~~~

 - Prefixing your comments with `FIXME` or `TODO` helps other developers quickly
   understand if you're pointing out a problem that needs to be revisited, or if
   you're suggesting a solution to the problem that needs to be implemented. These
   are different than regular comments because they are actionable. The actions
   are `FIXME -- need to figure this out` or `TODO -- need to implement`.
