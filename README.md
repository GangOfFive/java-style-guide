**Tabla de Contenidos**

- [Estándares de Java para Gang of Five](#est%C3%A1ndares-de-java-para-gang-of-five)
	- [Nombres](#nombres)
	- [Formato de Código](#formato-de-c%C3%B3digo)
		- [Bloques](#bloques)
		- [Espacios](#espacios)
		- [Comentarios](#comentarios)

# Estándares de Java para *Gang of Five*

Basado en [Google's Java style guide](http://google-styleguide.googlecode.com/svn/trunk/javaguide.html).

## Nombres
 - Los archivos de Java se deberán llamar de la siguiente forma:
   - `User.java`
   - `PinkUnicorn.java`
 - Utilizar `camelCase` para variables y métodos, y `PascalCase` para clases y enumeraciones.
 - Utilizar el siguiente formato para constantes: `EARTH_GRAVITY`.
 - Anteponer `I` a los nombres de las interfaces: `ITaggable`, `IRecipe`.
 - Ser descriptivo con los nombres.
 - Utilizar siempre modificadores de acceso para métodos y clases (`protected`, `private` o `public`).

    ~~~java
    // No recomendado
    List<Recipe> s(String str) {
        // ...stuff...
    }

    // Recomendado
    public List<Recipe> searchRecipes(String searchTerms) {
        // ..stuff..
    }
    ~~~

## Formato de Código
 - Longitud máxima de líneas: `80`. Si no es posible utilizar menos de 80 caracteres, intentar
   al menos utilizar menos de `120`.

### Bloques
 - Utilizar corchetes para todos los bloques de más de una línea.

    ~~~java
    // No recomendado
    if (test)
        return false;

    // No recomendado
    if (test) return false;

    // Recomendado
    if (test) {
        return false;
    }

    // No recomendado
    public boolean exists() { return false; }

    // Recomendado
    public boolean exists() {
        return false;
    }
    ~~~
 - Si un bloque está vacío, no poner espacios entre los corchetes.

    ~~~java
    void doNothing() {}
    ~~~

### Espacios
 - Utilizar `4` espacios para la indentación del código.

    ~~~java
    // No recomendado
    private boolean exists() {
    ∙∙return false;
    }

    // No recomendado
    private boolean exists() {
    ∙return false;
    }

    // Recomendado
    private boolean exists() {
    ∙∙∙∙return false;
    }
    ~~~

 - Colocar un espacio antes del primer corchete.

    ~~~java
    // No recomendado
    protected void sayHello(){
        System.out.println("hello");
    }

    // Recomendado
    protected void sayHello() {
        System.out.println("hello");
    }
    ~~~

 - Colocar espacios entre operadores.

    ~~~java
    // No recomendado
    int x=y+5;

    // Recomendado
    int x = y + 5;
    ~~~

 - Colocar una línea vacía al final de los archivos.

### Comentarios

 - Utilizar sólo las siguientes `tags` para los comentarios de Javadoc:
   - `@param`
   - `@return` (no utilizar en constructores o métodos que retornen `void`)
   - `@see`
   - `@throws`

 - No utilizar comentarios para `gets` y `sets` al menos que sea necesario.
 - No utilizar comentarios para POJOs.
 - Dejar una línea en blanco antes del primer `@param`.
 - Utilizar frases (no oraciones completas) para `@param` y `@return`.

 - Utilizar `/** ... */` para comentarios multilínea. Incluir descripción, y valores para
   los parámetros y lo que retorne el método.

    ~~~java
    /**
     * Returns an Image object that can then be painted on the screen. 
     * The url argument must specify an absolute URL. The name
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

 - Colocar `FIXME` o `TODO` antes de los comentarios para indicar si hay un problema
   que se necesita solucionar o una solución que aún se debe implementar.
   - `FIXME -- need to figure this out`
   - `TODO -- need to implement`
