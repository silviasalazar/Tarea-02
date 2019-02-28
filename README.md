# Tarea-02
Tarea 02 de site para la materia de Programación Orientada a Objetos (POO)

# Tarea 2
## UNIDAD 2
### Clases y objetos 
##### 2.1 Declaración de clases: atributos, métodos, encapsulamiento. 

*Lee y escribe un resumen con tus palabras del siguiente documento:*
 
 Las clases y estructuras son básicamente estructuras de datos que encapsulan un conjunto de datos y estructuras. 
Los miembros también son llamados como los datos y comportamientos de la clase, estos incluyen métodos y propiedades, entre otras características.  
Cuando se crea un objeto de la clase, la variable a la que se asigna el objeto contiene solo una referencia a esa memoria. Cuando la referencia de objeto se asigna a una nueva variable, la nueva variable hace referencia al objeto original. Los cambios realizados en una variable se reflejan en la otra variable porque ambas hacen referencia a los mismos datos. 
Una estructura es un tipo de valor. Existen dos tipos la estructura original y la copia o mejor dicho copias. Cuando se crea una estructura esta contiene los datos reales en ella, la cual es conocida como estructura original, cuando a dicha estructura se le asigna una nueva variable a esta se le conoce como copia, asi mismo estas dos son muy diferentes y contienen información independiente de la otra clase. 

Dentro de esto también interviene: 

 
**1. Tipos de referencia:** 
Un tipo que se define como una clase, es un tipo de referencia. Al declarar una variable de un tipo de referencia en tiempo de ejecución.
 
**2. Declarar clases:**
Las clases se declaran mediante la palabra clave class seguida por un identificador único.
![alt text](https://i.ytimg.com/vi/kI3cPBhFiDw/maxresdefault.jpg)

**3. Creación de objetos:** 
Los objetos se pueden crear usando la palabra clave new, seguida del nombre de la clase en la que se basará el objeto. 
![alt text](http://slideplayer.es/3097366/11/images/11/Pasos+Para+Crear+Objetos.jpg)

**4. Herencia**
La herencia se consigue mediante una derivación, en la que se declara una clase mediante una clase base, desde la que hereda los datos y el comportamiento. 
![alt text] (http://1.bp.blogspot.com/a98FpmjRW1k/WNGlZI4p7ZI/AAAAAAAACyY/XbCiqIZV2aMKsf9U3o5QWsQoVVPS3ejPQCK4B/s1600/EjemploHerencia.jpg)

 
Un ejemplo en donde se aplica todo esto es en el siguiente programa: 


```
class Persona 
   { 
       //Atributos o campos 
       private string nombre; 
       private int edad; 
  
       //Propiedad 
       public string Nombre 
       { 
           //Leer 
           get { return nombre; } 
           //Modificar 
           set { nombre = value; } 
       } 
       //Método constructor 
       public Persona(string nombre, int ed) 
       { 
           this.nombre = nombre; 
           edad = ed; 
       } 
       public void Imprime() 
       { 
           Console.WriteLine(nombre); 
       } 
       //Sobre carga de métodos (imprime) 
       public void Imprime(int veces) 
       { 
           for (int i = 0; i <= veces; i++) ; 
           Imprime(); 
       } 
   } 
   class Program 
   { 
       static void Main() 
       { 
           //Crear objeto 
           Persona p = new Persona("Ale",19); 
           List<Persona> personas = new List<Persona>(); 
           personas.Add(p); 
           personas.Add(new Persona("Karla", 10)); 
           p.Imprime(3); 
           Console.ReadKey(); 
       } 
   } 
} 
```


#### 2.2 Instanciación de una clase. 
 
**Investiga sobre el operador new visto en clase. Describe algunos de sus usos.**
El operador new Proporciona espacio de almacenamiento persistente, similar pero superior a la función de Librería Estándar malloc. Este operador permite crear un objeto de cualquier tipo, incluyendo tipos definidos por el usuario, y devuelve un puntero (del tipo adecuado) al objeto creado. Su utilización exige que el usuario declarare un puntero del tipo adecuado; a continuación, debe ser inicializado con el valor devuelto por el operador. </p>

**Usos:**
- Se utiliza para crear objetos e invocar constructores. 
- Para crear instancias de tipos anónimos. 
- Para invocar el constructor predeterminado de los tipos de valor. 


#### 2.3 Referencia al objeto actual. 
 
 La palabra clave this hace referencia a la instancia actual de la clase. 
 
***1. Escribe un programa donde utilices this para obtener acceso a miembros con el fin de evitar ambigüedades con nombres similares.*** 


```
{ 
   class Contacto 
   { 
       //Atributos 
       private string nombre; 
       private string correo; 
       private string celular; 
 
 
       //Método constructor 
       public Contacto(string n,string co,string cel) 
       { 
           nombre = n; 
           correo = co; 
           celular = cel; 
       } 
       public void imprime() 
       { 
           Console.WriteLine("{0}:{1}:{2}", nombre, correo, celular); //Indica el lugar 0=nombre,1=correo, 2=celular 
       } 
   } 
   class Agenda 
   { 
       private string nombre; 
       private List<Contacto> contactos; 
       public Agenda(string nombre) 
       { 
           this.nombre = nombre; //this hace referencia al objeto con el que se trabaja 
           contactos = new List<Contacto>(); 
       } 
       public void Agrega(Contacto contacto) 
       { 
           contactos.Add(contacto); 
       } 
       public void Agrega(string nombre, string correo, string celular) 
       { 
           contactos.Add(new Contacto(nombre, correo, celular)); 
       } 
       public void imprime() 
       { 
           foreach(Contacto contacto in contactos) 
           { 
               contacto.imprime(); 
           } 
       } 
   } 
   class Program 
   { 
       static void Main() 
       { 
           Agenda a = new Agenda(""); 
           Agenda b = new Agenda("amigos"); 
           a.Agrega(new Contacto("", "", "")); 
List<Contacto> Contactos = new List<Contacto>(); 
           Contactos.Add(new Contacto("Alejandra", "ale@gmail.com", "664-278-6745")); 
           Contactos.Add(new Contacto("Antonia", "antonia@gmail.com", "664-154-3027")); 
           Contactos.Add(new Contacto("Kevin", "kevin@gmail.com", "664-222-1697")); 
           Contactos.Add(new Contacto("Karla", "karla@gmail.com", "664-144-2356")); 
           Contactos.Add(new Contacto("Gregoy", "grag@gmail.com", "664-879-5654")); 
foreach (Contacto contactos in Contactos) 
           { 
               contactos.imprime();  
           } 
                  Console.ReadKey(); 
      } 
   } 
} 
```
 
***2. Escribe un programa donde se utilice this como parámetro.***

![Con titulo](https://images.techhive.com/images/article/2016/10/extensionmethods-100687247-primary.idge.jpg "titulo")

#### 2.4 Métodos: declaración, mensajes, paso de parámetros, retorno de valores. 
 Lee y escribe un resumen con tus palabras de los siguientes documentos: 
 
 
**Parámetros de métodos (Referencia de C#)**  
https://msdn.microsoft.com/es-ES/library/8f1hz171.aspx  

Un argumento o parámetro es el medio a partir del cual podemos expandir el ámbito de variables locales de funciones, hacia otras funciones y además quienes nos permiten establecer comunicaciones entre funciones.  
params especifica que este parámetro puede tomar un número variable de argumentos. 

- **in** especifica que este parámetro se pasa por referencia, pero solo se lee mediante el método llamado.
 
- **ref** especifica que este parámetro se pasa por referencia y puede ser leído o escrito por el método llamado.
 
- **out** especifica que este parámetro se pasa por referencia y se escribe mediante el método llamado.
 
 
**params (Referencia de C#)**
https://msdn.microsoft.com/es-es/library/w5zay9db.aspx    
Mediante el uso de la palabra clave params, puede especificar un parámetro de método que toma un número variable de argumentos. 
La palabra reservada params se usa en la declaración de los parámetros de un método, se antepone al tipo de dato que vamos a declarar y tiene una peculiaridad, solamente se puede anteponer a parámetros que sean arreglos, por ejemplo a string[], Persona[]. 
Esto es porque lo que nos ayuda a escribir es un método que recibe una cantidad variable de argumentos del mismo tipo y los “introduce” un un arreglo sin tener que declararlo explícitamente. 



**out (Referencia de C#)**
https://msdn.microsoft.com/es-es/library/t3c3bfhx.aspx 
    
***Puede usar la palabra clave out en dos contextos:***    
- Como un **modificador de parámetro**, que le permite pasar un argumento a un método mediante una referencia en lugar de mediante un valor. 
La palabra clave out produce argumentos que se van a pasar por referencia. Ocurre igual que con la palabra clave ref, excepto en que ref requiere que se inicialice la variable antes de pasarla.  
  
- En **declaraciones de parámetro de tipo genérico** para interfaces y delegados, que especifica que un parámetro de tipo es covariante. 
Para los parámetros de tipo genérico, la palabra clave out especifica que el parámetro de tipo es covariante. Puede usar la palabra clave out en las interfaces y delegados genéricos. 

 
**ref (Referencia de C#)**
https://msdn.microsoft.com/es-es/library/14akc2c7.aspx
 
La palabra clave ref indica un valor que se ha pasado mediante referencia. Se usa en cuatro contextos diferentes: 
En una firma del método y en una llamada al método, para pasar un argumento a un método mediante referencia. 
En una firma del método, para devolver un valor al autor de la llamada mediante referencia. 

![ref](https://social.msdn.microsoft.com/Forums/getfile/893432)


#### 2.5 Constructores y destructores: declaración, uso y aplicaciones. 
***Lee y escribe un resumen con tus palabras del siguiente documento:***
  
**Utilizar constructores**

***¿Qué es?***   
Los constructores son métodos de clase que se ejecutan cuando se crea un objeto de un tipo determinado. 

***Uso***   
Un constructor que no toma ningún parámetro se denomina constructor predeterminado. Los constructores predeterminados se invocan cada vez que se crea una instancia de un objeto mediante el operador new y no se proporciona ningún argumento a new. 
Si la clase es estática, a las clases sin constructores se les asigna un constructor público. 
Los constructores para los tipos struct son similares a los constructores de clases. Este constructor inicializa cada campo del tipo struct con los valores predeterminados. </p>

***Aplicación*** 
Este constructor predeterminado sólo se invoca si se crean instancias del tipo struct con new. 

Por ejemplo, el siguiente código contiene un error porque no se le agrega el new. 

```
int i; 
Console.WriteLine(i); 
```         
La manera correcta es:  
```
int i = new int(); 
Console.WriteLine(i); 
```   
***Existen dos tipos de constructores:***  
 Un constructor de instancia es un miembro que implementa las acciones necesarias para inicializar una instancia de una clase. Constructores de instancia se declaran mediante *constructor_declarations*.   
Un constructor estático es un miembro que implementa las acciones necesarias para inicializar un tipo de clase cerrado. Los constructores estáticos se declaran mediante *static_constructor_declarations*.</p>
 
#### 2.6 Sobrecarga de métodos. 
***Ver el ejercicio siguiente***
  
#### 2.7 Sobrecarga de operadores: Concepto y utilidad, operadores unarios y binarios. 
Un operador es un símbolo que opera en ciertos tipos de datos y produce la salida como resultado de la operación. En el lenguaje C, se pueden combinar diferentes operadores de categorías similares o diferentes y realizar una operación. En este caso, el compilador de C trata de resolver la expresión de acuerdo con las reglas de precedencia.</p>
  
  ![Con titulo](https://thamet88.files.wordpress.com/2011/09/c4.jpg "titulo")
  <p style="text-align: justify;"> 
 
**1. Implementa una clase llamada Dado, la cual es una abstracción de los dados de algún juego. **   
**2. Debe de tener por lo menos las siguientes propiedades:** 
**valor **  
**color **  

**La clase debe contar por lo menos con:**
a) Dos constructores sobrecargados. 
b) Los operadores ==, <, > sobrecargados. 
c) El uso de la palabra clave this. 
d) Utiliza tu clase dentro del método Main de tu programa, creando tres dados, arrojándolos e imprimiendo el mejor de ellos 
o si alguno es igual. 

  
 
 
 
 


