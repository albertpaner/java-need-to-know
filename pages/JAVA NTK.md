- O.O.P.                                                                                                                                                            [Four main object-oriented programming concepts of Java](https://www.geeksforgeeks.org/four-main-object-oriented-programming-concepts-of-java/)
  collapsed:: true
	- 1) Abstraction | Astrazione                                                                                                                 
	  collapsed:: true
	  [What is abstraction in Java](https://www.softwaretestinghelp.com/what-is-abstraction-in-java/)                                                                                                       
	  L'astrazione è un processo che nasconde i dettagli di implementazione e mostra solo le funzionalità all'utente.
		- Data Abstraction | Astrazione Strutture Dati
		  collapsed:: true
			- Per la "Data Abstraction" creiamo strutture dati e nascondiamo l'implementazione. Esponiamo solo le funzionalità per manipolare queste strutture dati senza entrare nei dettagli dell'implementazione. Questo ci permette di cambiare quando si vuole l'implementazione senza cambiare le funzionalità mostrate all'utente.
		- Esempio: Guida Macchina: 
		  ```java
		  //abstract class
		  abstract class Car{  
		      abstract void accelerate();  
		  }  
		  //concrete class
		  class Suzuki extends Car{  
		      void accelerate(){
		          System.out.println("Suzuki::accelerate");
		       
		      }
		  }
		  class Main{
		      public static void main(String args[]){  
		          Car myCar = new Suzuki();    //Car myCar => contents of Suzuki
		          obj.accelerate();          //call the method  
		      }   
		  }  
		  
		  ```
	- 2) Encapsulation | Incapsulamento                                                                                          [encapsulation](https://www.javatpoint.com/encapsulation)                                                                                                                                                                                      L'incapsulamento consiste nell'avvolgere codice e dati in una singola classe.
	  collapsed:: true
		- Information Hiding | Nascondere i dati                                                                           L'incapsulamento è un meccanismo che nasconde i dati all'utente. Per esempio, se tutti gli attributi della classe sono privati,  l'utente può accedervi solo attraverso i metodi 'setter' e 'getter' presenti nella classe.
		- Esempio Conto 
		  ```java
		  //A Account class which is a fully encapsulated class.  
		  //It has a private data member and getter and setter methods.  
		  class Account {  
		  //private data members  
		  private long acc_no;  
		  private String name,email;  
		  private float amount;  
		  //public getter and setter methods  
		  public long getAcc_no() {  
		      return acc_no;  
		  }  
		  public void setAcc_no(long acc_no) {  
		      this.acc_no = acc_no;  
		  }  
		  public String getName() {  
		      return name;  
		  }  
		  public void setName(String name) {  
		      this.name = name;  
		  }  
		  public String getEmail() {  
		      return email;  
		  }  
		  public void setEmail(String email) {  
		      this.email = email;  
		  }  
		  public float getAmount() {  
		      return amount;  
		  }  
		  public void setAmount(float amount) {  
		      this.amount = amount;  
		  }  
		    
		  }  
		  
		  //A Java class to test the encapsulated class Account.  
		  public class TestEncapsulation {  
		  public static void main(String[] args) {  
		      //creating instance of Account class  
		      Account acc=new Account();  
		      //setting values through setter methods  
		      acc.setAcc_no(7560504000L);  
		      acc.setName("Sonoo Jaiswal");  
		      acc.setEmail("sonoojaiswal@javatpoint.com");  
		      acc.setAmount(500000f);  
		      //getting values through getter methods  
		      System.out.println(acc.getAcc_no()+" "+acc.getName()+" "+acc.getEmail()+" "+acc.getAmount());  
		  }  
		  }  
		  ```
	- 3) Inheritance | Ereditarietà                                                                                                                                                                                   [inheritance](https://www.geeksforgeeks.org/inheritance-in-java/)                                                                                                                                                                                   L'ereditarietà è un meccanismo che permette di creare una nuova classe utilizzando le proprietà di una classe esistente. Una classe può ereditare le proprietà (campi e metodi) di un'altra classe
	  collapsed:: true
		- Code Reusability | Riutilizzabilità codice                                                                                                                    Il codice scritto in una superclasse è comune a tutte le sottoclassi.
		- Esempio Bike 
		  ```java
		  // Java program to illustrate the
		  // concept of inheritance
		  
		  // base class
		  class Bicycle {
		  	// the Bicycle class has two fields
		  	public int gear;
		  	public int speed;
		  
		  	// the Bicycle class has one constructor
		  	public Bicycle(int gear, int speed)
		  	{
		  		this.gear = gear;
		  		this.speed = speed;
		  	}
		  
		  	// the Bicycle class has three methods
		  	public void applyBrake(int decrement)
		  	{
		  		speed -= decrement;
		  	}
		  
		  	public void speedUp(int increment)
		  	{
		  		speed += increment;
		  	}
		  
		  	// toString() method to print info of Bicycle
		  	public String toString()
		  	{
		  		return ("No of gears are " + gear + "\n"
		  				+ "speed of bicycle is " + speed);
		  	}
		  }
		  
		  // derived class
		  class MountainBike extends Bicycle {
		  
		  	// the MountainBike subclass adds one more field
		  	public int seatHeight;
		  
		  	// the MountainBike subclass has one constructor
		  	public MountainBike(int gear, int speed,
		  						int startHeight)
		  	{
		  		// invoking base-class(Bicycle) constructor
		  		super(gear, speed);
		  		seatHeight = startHeight;
		  	}
		  
		  	public void setHeight(int newValue)
		  	{
		  		seatHeight = newValue;
		  	}
		  
		  	// overriding toString() method
		  	// of Bicycle to print more info
		  	@Override public String toString()
		  	{
		  		return (super.toString() + "\nseat height is "
		  				+ seatHeight);
		  	}
		  }
		  
		  // driver class
		  public class Test {
		  	public static void main(String args[])
		  	{
		  
		  		MountainBike mb = new MountainBike(3, 100, 25);
		  		System.out.println(mb.toString());
		  	}
		  }
		  
		  ```
	- 4) Polymorphism | Polimorfismo                                                                                             [polymorphism](https://www.geeksforgeeks.org/polymorphism-in-java/)                                                                                                                                                                                      "Lo stesso oggetto assume forme e comportamenti diversi a seconda del contesto". Ci permette per esempio di implementare un metodo con lo stesso nome in modi diversi. Permette riutilizzabilità, maggiore flessibilità e migliore leggibilità del codice.
		- Compile-time Polymorphism | Polimorfismo Statico                                                                             Avviene al momento della compilazione.
			- Esempio: [Method Overloading](https://www.geeksforgeeks.org/method-overloading-in-java/)                                                                                                                      Più metodi con lo stesso nome e segnature diverse. Viene deciso quale metodo eseguire in fase di compilazione.
			  collapsed:: true
				- ```c++
				  // Java Program for Method overloading
				  // By using Different Types of Arguments
				  
				  // Class 1
				  // Helper class
				  class Helper {
				  
				  	// Method with 2 integer parameters
				  	static int Multiply(int a, int b)
				  	{
				  		// Returns product of integer numbers
				  		return a * b;
				  	}
				  
				  	// Method 2
				  	// With same name but with 2 double parameters
				  	static double Multiply(double a, double b)
				  	{
				  		// Returns product of double numbers
				  		return a * b;
				  	}
				  }
				  
				  // Class 2
				  // Main class
				  class GFG {
				  	// Main driver method
				  	public static void main(String[] args)
				  	{
				  		// Calling method by passing
				  		// input as in arguments
				  		System.out.println(Helper.Multiply(2, 4));
				  		System.out.println(Helper.Multiply(5.5, 6.3));
				  	}
				  }
				  
				  ```
		- Run-time Polymorphism | Polimorfismo Dinamico                                                                                              Avviene durante l'esecuzione del programma.
		  collapsed:: true
			- Esempio: [Method Overriding](https://www.geeksforgeeks.org/overriding-in-java/)                                                                                        
			  Quando una sottoclasse fornisce un'implementazione diversa di un metodo della superclasse con la stessa segnatura.
				- toString() Method in Object defined [here](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#toString--)
				- ```c++
				  // Java Program to illustrate Overriding
				  // toString() Method
				  
				  // Class 1
				  public class GFG {
				  	
				  	// Main driver method
				  	public static void main(String[] args) {
				  		
				  		// Creating object of class1 
				  		// inside main() method
				  		Complex c1 = new Complex(10, 15);
				  		
				  		// Printing the complex number 10.0 + 15.0i
				  		System.out.println(c1);
				  	}
				  }
				  // Class 2
				  // Helper class
				  class Complex {
				  	
				  	// Attributes of a complex number
				  	private double re, im;
				  	
				  	// Constructor to initialize a complex number
				  	// Default
				  	// public Complex() {
				  	//	 this.re = 0;
				  	//	 this.im = 0;
				  	// }
				  	
				  	// Constructor 2: Parameterized
				  	public Complex(double re, double im) {
				  		
				  		// This keyword refers to 
				  		// current complex number
				  		this.re = re;
				  		this.im = im;
				  	}
				  	// Getters
				  	public double getReal() {
				  		return this.re;
				  	}
				  	public double getImaginary() {
				  		return this.im ;
				  	}
				  	// Setters
				  	public void setReal(double re) {
				  		this.re = re;
				  	}
				  	public void setImaginary(double im) {
				  		this.im = im;
				  	}
				  	// Overriding toString() method of String class
				  	@Override
				  	public String toString() {
				  		return this.re + " + " + this.im + "i";
				  	}
				  }
				  
				  ```
- [S.O.L.I.D.](https://www.baeldung.com/solid-principles)
  collapsed:: true
	- **S**ingle Responsibility
	- **O**pen/Closed
	- **L**iskov Substitution
		- **if class *A* is a subtype of class *B*, we should be able to replace *B *with *A *without disrupting the behavior of our program.**
	- **I**nterface Segregation
	- **D**ependency Inversion
		- The *Dependency Injection Principle* is  being able to pass (inject) the dependencies when required instead of initializing the dependencies inside of the recipient class.
		- *Decouple the construction of your classes from the construction of your classes’ dependencies*
		- ```java
		  public class Windows98Machine {
		  
		      private final StandardKeyboard keyboard;
		      private final Monitor monitor;
		  
		      public Windows98Machine() {
		          monitor = new Monitor();
		          keyboard = new StandardKeyboard();
		      }
		  
		  }
		  ```
		- ```java
		  public interface Keyboard { }
		  
		  public class Windows98Machine{
		  
		      private final Keyboard keyboard;
		      private final Monitor monitor;
		  
		      public Windows98Machine(Keyboard keyboard, Monitor monitor) {
		          this.keyboard = keyboard;
		          this.monitor = monitor;
		      }
		  }
		  ```
- [Data Types in Java](https://www.javatpoint.com/reference-data-types-in-java)
  collapsed:: true
	- primitive
	  collapsed:: true
		- boolean
		- byte
		- char
		- short
		- int
		- long
		- float
		- double
	- reference
		- Class
		- Interface
		- [enum](https://docs.oracle.com/javase/tutorial/java/javaOO/enum.html)
		  collapsed:: true
			- An *enum type* is a special data type that enables for a variable to be a set of predefined constants. The variable must be equal to one of the values that have been predefined for it. Common examples include compass directions (values of NORTH, SOUTH, EAST, and WEST) and the days of the week.
			- ```java
			  public enum Planet {
			      MERCURY (3.303e+23, 2.4397e6),
			      VENUS   (4.869e+24, 6.0518e6),
			      EARTH   (5.976e+24, 6.37814e6),
			      MARS    (6.421e+23, 3.3972e6),
			      JUPITER (1.9e+27,   7.1492e7),
			      SATURN  (5.688e+26, 6.0268e7),
			      URANUS  (8.686e+25, 2.5559e7),
			      NEPTUNE (1.024e+26, 2.4746e7);
			  
			      private final double mass;   // in kilograms
			      private final double radius; // in meters
			      Planet(double mass, double radius) {
			          this.mass = mass;
			          this.radius = radius;
			      }
			      private double mass() { return mass; }
			      private double radius() { return radius; }
			  
			      // universal gravitational constant  (m3 kg-1 s-2)
			      public static final double G = 6.67300E-11;
			  
			      double surfaceGravity() {
			          return G * mass / (radius * radius);
			      }
			      double surfaceWeight(double otherMass) {
			          return otherMass * surfaceGravity();
			      }
			      public static void main(String[] args) {
			          if (args.length != 1) {
			              System.err.println("Usage: java Planet <earth_weight>");
			              System.exit(-1);
			          }
			          double earthWeight = Double.parseDouble(args[0]);
			          double mass = earthWeight/EARTH.surfaceGravity();
			          for (Planet p : Planet.values())
			             System.out.printf("Your weight on %s is %f%n",
			                               p, p.surfaceWeight(mass));
			      }
			  }
			  ```
		- record
- Classes and Interfaces
  collapsed:: true
	- Class                                                                                                                                              
	  [class](https://www.geeksforgeeks.org/classes-objects-java/)                                                                                                                                                                                          A class is a blueprint or prototype from which objects are created
		- Object : Istanza di una classe creata per usare i campi e i metodi della classe.
		  collapsed:: true
			- An object is a software bundle of related state and behavior. Software objects are often used to model the real-world objects that you find in everyday life.
			- State | Stato : Attributi o proprietà dell'oggetto
			- Behaviour | Comportamento : Metodi dell'oggetto
			- Identity | Nome : Nome identificativo dell'oggetto
			- ```c++
			  public class Person {
			      private int id;
			      private String name;
			      private int age;
			  
			      public Person (int id, String name, int age) {
			          this.id = id;
			          this.name = name;
			          this.age = age;
			      }
			  
			      public int hashCode() {
			          final int prime = 31;
			          int result = 1;
			          result = prime * result + id;
			          return result;
			      }
			  
			      public boolean equals(Object obj) {
			          if (this == obj)
			              return true;
			          if (obj == null)
			              return false;
			          if (getClass() != obj.getClass())
			              return false;
			          Person other = (Person) obj;
			          if (id != other.id)
			              return false;
			          return true;
			      }
			  
			      public static void main(String[] args) {
			          //For case 1, there are two instances of the class Person, but both instances represent the same object.
			          Person p1 = new Person(1, "Carlos", 20);
			          Person p2 = new Person(1, "Carlos", 20);
			  
			          //For case 2, there are two instances of the class Person, but each instance represent a different object.
			          Person p3 = new Person(2, "John", 15);
			          Person p4 = new Person(3, "Mary", 17);
			      }
			  }
			  ```
		- Template | Prototipo da cui possono essere istanziati oggetti.
		- Può contenere : dati o variabili di diversi tipi, metodi, costruttori
		- Esempio Completo
		  collapsed:: true
			- ```c++
			  public class Square {
			   
			      protected int width;
			   
			      public int getWidth() {
			          return width;
			      }
			   
			      public void setWidth(int width) {
			          this.width = width;
			      }
			  }
			  ```
			- ```c++
			  public interface Shape {
			   
			      double calculateArea();
			   
			      double calculatePerimeter();
			   
			  }
			  ```
			- ```c++
			  public class RoundedCornerSquare extends Square implements Shape {
			   
			      /** Field Declarations: **/
			      private static double cornerRadius;
			      private String fillColor;
			      private String borderColor;
			   
			   
			      /** Static Initializers: **/
			      static {
			          cornerRadius = 1.58;
			      }
			   
			      /** Instance Initializers: **/
			      {
			          fillColor = "White";
			          borderColor = "Black";
			      }
			   
			      /** Constructors: **/
			      public RoundedCornerSquare() {
			          this.width = 15;
			      }
			   
			      public RoundedCornerSquare(int width) {
			          this.width = width;
			      }
			   
			      public RoundedCornerSquare(int width, String fillColor) {
			          this.width = width;
			          this.fillColor = fillColor;
			      }
			   
			      /** Method Declarations: **/
			      public double calculateArea() {
			          return width * width;
			      }
			   
			      public double calculatePerimeter() {
			          return width * 4;
			      }
			   
			      public void printDetails() {
			          System.out.print("Rounded Corner Square[width=" + width);
			          System.out.print(", radius=" + cornerRadius);
			          System.out.print(", fillColor=" + fillColor);
			          System.out.println(", borderColor=" + borderColor + "]");
			      }
			   
			      public static void main(String[] args) {
			          RoundedCornerSquare square1 = new RoundedCornerSquare();
			          RoundedCornerSquare square2 = new RoundedCornerSquare(20, "Blue");
			   
			          square1.printDetails();
			          square2.printDetails();
			      }
			  }
			  
			  ```
		- Abstract Class | Classe Astratta
			- Classe dichiarata con la keyword 'abstract'
			- Può avere sia metodi astratti (senza corpo) sia non-
			- Non può essere istanziata
			- Può avere costruttori
			- Esempio Usato [HttpServlet](https://developer.adobe.com/experience-manager/reference-materials/cloud-service/javadoc/javax/servlet/http/HttpServlet.html)
			- Altri Esempi
			  collapsed:: true
				- ```c++
				  abstract class Shape {
				      protected int area;
				      public abstract void calculateArea();
				      public void displayArea() {
				          System.out.println("Area: " + area);
				      }
				  }
				  class Circle extends Shape {
				      private double radius;
				      public Circle(double radius) {
				          this.radius = radius;
				      }
				     public void calculateArea() {
				          area = (int) (Math.PI * radius * radius);
				      }
				  }
				  class Rectangle extends Shape {
				      private int length;
				      private int width;
				     public Rectangle(int length, int width) {
				          this.length = length;
				          this.width = width;
				      }
				      public void calculateArea() {
				          area = length * width;
				      }
				  }
				  public class Main {
				      public static void main(String[] args) {
				          Shape circle = new Circle(5.0);
				          circle.calculateArea();
				          circle.displayArea();
				          Shape rectangle = new Rectangle(4, 6);
				          rectangle.calculateArea();
				          rectangle.displayArea();
				      }
				  }
				  ```
	- Interface                                                                                                                                                                                                              [interface](https://docs.oracle.com/javase/tutorial/java/IandI/createinterface.html)
		- an *interface* is a reference type, similar to a class, that can contain *only* constants, method signatures, default methods, static methods, and nested types. Method bodies exist only for default methods and static methods. Interfaces cannot be instantiated—they can only be *implemented* by classes or *extended* by other interfaces.
		- An interface declaration can contain method signatures, default methods, static methods and constant definitions. The only methods that have implementations are default and static methods.
		- A class that implements an interface must implement all the methods declared in the interface.
		- An interface name can be used anywhere a type can be used.
		- ```java
		  public interface Relatable {
		          
		      // this (object calling isLargerThan)
		      // and other must be instances of 
		      // the same class returns 1, 0, -1 
		      // if this is greater than, 
		      // equal to, or less than other
		      public int isLargerThan(Relatable other);
		  }
		  ```
		- ```java
		  public class RectanglePlus 
		      implements Relatable {
		      public int width = 0;
		      public int height = 0;
		      public Point origin;
		  
		      // four constructors
		      public RectanglePlus() {
		          origin = new Point(0, 0);
		      }
		      public RectanglePlus(Point p) {
		          origin = p;
		      }
		      public RectanglePlus(int w, int h) {
		          origin = new Point(0, 0);
		          width = w;
		          height = h;
		      }
		      public RectanglePlus(Point p, int w, int h) {
		          origin = p;
		          width = w;
		          height = h;
		      }
		  
		      // a method for moving the rectangle
		      public void move(int x, int y) {
		          origin.x = x;
		          origin.y = y;
		      }
		  
		      // a method for computing
		      // the area of the rectangle
		      public int getArea() {
		          return width * height;
		      }
		      
		      // a method required to implement
		      // the Relatable interface
		      public int isLargerThan(Relatable other) {
		          RectanglePlus otherRect 
		              = (RectanglePlus)other;
		          if (this.getArea() < otherRect.getArea())
		              return -1;
		          else if (this.getArea() > otherRect.getArea())
		              return 1;
		          else
		              return 0;               
		      }
		  }
		  ```
		- When you define a new interface, you are defining a new reference data type. You can use interface names anywhere you can use any other data type name. If you define a reference variable whose type is an interface, any object you assign to it *must* be an instance of a class that implements the interface.
		  collapsed:: true
			- ```java
			  public Object findLargest(Object object1, Object object2) {
			     Relatable obj1 = (Relatable)object1;
			     Relatable obj2 = (Relatable)object2;
			     if ((obj1).isLargerThan(obj2) > 0)
			        return object1;
			     else 
			        return object2;
			  }
			  ```
		- [Evolving Interfaces](https://docs.oracle.com/javase/tutorial/java/IandI/nogrow.html)
		  collapsed:: true
			- ```java
			  public interface DoIt {
			     void doSomething(int i, double x);
			     int doSomethingElse(String s);
			  }
			  ```
			- ```java
			  public interface DoItPlus extends DoIt {
			  
			     boolean didItWork(int i, double x, String s);
			     
			  }
			  ```
			- [Default methods](https://docs.oracle.com/javase/tutorial/java/IandI/defaultmethods.html)
				- ```java
				  public interface DoIt {
				  
				     void doSomething(int i, double x);
				     int doSomethingElse(String s);
				     default boolean didItWork(int i, double x, String s) {
				         // Method body 
				     }
				     
				  }
				  ```
	- [Abstract class and Interface](https://docs.oracle.com/javase/tutorial/java/IandI/abstract.html)
		- Abstract classes are similar to interfaces. You cannot instantiate them, and they may contain a mix of methods declared with or without an implementation. However, with abstract classes, you can declare fields that are not static and final, and define public, protected, and private concrete methods. With interfaces, all fields are automatically public, static, and final, and all methods that you declare or define (as default methods) are public. In addition, you can extend only one class, whether or not it is abstract, whereas you can implement any number of interfaces.
- [Data Structures Java](https://www.javatpoint.com/data-structures-in-java)
  collapsed:: true
	- [Iterable](https://docs.oracle.com/javase/8/docs/api/java/lang/Iterable.html)                                                                                                                                                        Permette di usare il for-each per gli oggetti della classe che la implementa
		- [Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)                                                                                                                                                              Rappresenta un gruppo di oggetti o elementi
			- [Set](https://docs.oracle.com/javase/8/docs/api/java/util/Set.html)                                                                                                                                                                                                            Collezione che non contiene elementi duplicati
				- [HashSet](https://docs.oracle.com/javase/8/docs/api/java/util/HashSet.html)                                                                                                                                                       Classe che implementa Set. Ha metodi come add, remove, contains e size
				- [SortedSet](https://docs.oracle.com/javase/8/docs/api/java/util/SortedSet.html)                                                                                              
				  Set totalmente ordinato. Tutti gli elementi inseriti devono implementare [Comparable](https://docs.oracle.com/javase/8/docs/api/java/lang/Comparable.html)
					- [TreeSet](https://docs.oracle.com/javase/8/docs/api/java/util/TreeSet.html)
			- [List](https://docs.oracle.com/javase/8/docs/api/java/util/List.html)                                                                                                                                                                                                              Sequenza o Collezione Ordinata con Accesso Posizionale
				- [ArrayList](https://docs.oracle.com/javase/8/docs/api/java/util/ArrayList.html)                                                                                                                                                             Lista statica e 'resizable'.
				  collapsed:: true
					- Simple ArrayList example 
					  ```c++
					  import java.util.ArrayList;
					  
					  class Main {
					    public static void main(String[] args){
					  
					      // create ArrayList
					      ArrayList<String> languages = new ArrayList<>();
					  
					      // Add elements to ArrayList
					      languages.add("Java");
					      languages.add("Python");
					      languages.add("Swift");
					      System.out.println("ArrayList: " + languages); // ArrayList: [Java, Python, Swift]
					    }
					  }
					  ```
				- [LinkedList](https://docs.oracle.com/javase/8/docs/api/java/util/LinkedList.html)                                                                                                                                                                                       Lista dinamica e [doubly-linked](https://www.geeksforgeeks.org/data-structures/linked-list/doubly-linked-list/)
	- [Map](https://docs.oracle.com/javase/8/docs/api/java/util/Map.html)                                         
	  Mappa chiave-valore. Chiavi sono uniche e ogni chiave viene mappata ad al più un valore
		- [HashMap](https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html)                                                                                                                                              dizionario
		  collapsed:: true
			- Simple HashMap example 
			  ```c++
			  import java.util.HashMap;
			  
			  class Main {
			    public static void main(String[] args) {
			  
			      // create a hashmap
			      HashMap<String, Integer> languages = new HashMap<>();
			  
			      // add elements to hashmap
			      languages.put("Java", 8);
			      languages.put("JavaScript", 1);
			      languages.put("Python", 3);
			      System.out.println("HashMap: " + languages);   // HashMap: {Java=8, JavaScript=1, Python=3}
			    }
			  }
			  ```
		- [TreeMap](https://docs.oracle.com/javase/8/docs/api/java/util/TreeMap.html)                                                                                                                                                               dizionario con chiavi totalmente ordinate con albero binario [Red-Black Tree](https://en.wikipedia.org/wiki/Red%E2%80%93black_tree)
- Keywords
  collapsed:: true
	- [static](https://www.geeksforgeeks.org/static-keyword-java/)                                                                                                                                                         Modificatore usato per variabili o metodi propri della classe che rimangono gli stessi per ogni istanza.
	  collapsed:: true
		- Per quanto riguarda il 'Memory Management' di variabili e metodi statici, viene allocata memoria una volta solta durante l'esecuzione del programma e tale memoria è condivisa per tutte le istanze
		- Membri statici sono accessibili senza istanziazione di oggetti
		- Non possono accedere membri non-statici sennò viene sollevato il seguente errore [non-static _ cannot be referenced from a static context](https://stackoverflow.com/questions/2559527/non-static-variable-cannot-be-referenced-from-a-static-context)
		- Posso fare un Overload di metodi statici ma non un Override appunto perché sono associati alla classe e non a una sua istanza
		- Esempio
		  collapsed:: true
			- ```c++
			  public class Geometry2DUtils {
			  	public static final double PiGreco = 3.141592;
			  	public static double areaParallelogramma(double base, double altezza) { }
			  	public static double areaParallelogramma(double c1, double c2, double alpha) { }
			  	// ...
			  	public static double areaCerchio(double r) {
			  		// anche se static potrà usare la variabile statica PiGreco
			  		return PiGreco * r * r;
			  	}
			  }
			  
			  ```
			- ```c++
			  public class Parallelogramma {
			  	private double base, altezza;
			  	public Parallelogramma(double base, double altezza) { 
			  		// inzializza le variabili di istanza
			  		this.base = base;
			  		this.altezza = altezza;
			  	} 
			  	// questo metodo area non ha bisogno dei
			  	// parametri in quanto utilizza le variabili della classe
			  	public double area() {
			  		// utilizza il metodo (pubblico e statico) nella classe  di utility
			  		// chiamandolo usando il nome della classe (poi il compilatore
			  		// sceglie quello giusto sulla base dei parametri)
			  		return Geometry2DUtils.areaParallelogramma(base, altezza);
			  	}
			  	// metodi per l'accesso (getters) delle variabili private della classe,
			  	// garantiscono, tra l'altro, che i field possano essere utilizzati ma non
			  	// modificati
			  	public double getBase()    { return base; }
			  	public double getAltezza() { return altezza; }
			  }
			  ```
	- default
	- access modifiers
		- [public](https://www.javatpoint.com/public-keyword-in-java)
		- [private](https://www.javatpoint.com/private-keyword-in-java)
		- protected
- [Annotations](https://docs.oracle.com/javase/tutorial/java/annotations/basics.html)
  collapsed:: true
	- [Annotation Processing](https://reflectoring.io/java-annotation-processing/)
- [Reflection](https://www.baeldung.com/java-reflection)
- [for](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/for.html) or [for-each](https://www.javatpoint.com/for-each-loop)?
  collapsed:: true
	- Il classico 'for' è usato per iterare sugli elementi di una collezione usando un indice posizionale
	- Il 'for-each' itera sugli elementi senza aver bisogno di un indice
	  collapsed:: true
		- Non tiene traccia della posizione
		- scorre la collezione in avanti in step singoli
	- Esempio
		- ```c++
		  //Java Program to demonstrate the example of for loop  
		  //which prints table of 1  
		  public class ForExample {  
		  public static void main(String[] args) {  
		      //Code of Java for loop  
		      for(int i=1;i<=10;i++){  
		          System.out.println(i);  
		      }  
		  }  
		  }  
		  ```
		- ```c++
		  // FOR-EACH
		  
		    public static void loopMapClassic() {
		  
		        Map<String, Integer> map = new HashMap<>();
		        map.put("A", 10);
		        map.put("B", 20);
		        map.put("C", 30);
		        map.put("D", 40);
		        map.put("E", 50);
		        map.put("F", 60);
		  
		        for (Map.Entry<String, Integer> entry : map.entrySet()) {
		            System.out.println("Key : " + entry.getKey() + ", Value : " + entry.getValue());
		        }
		  
		    }
		  
		  ```
- training-project
  collapsed:: true
	- [Bean](https://www.javatpoint.com/java-bean)
	  collapsed:: true
		- 1 : 1 con tabella in DB
		- [JavaBean](https://medium.com/@mgm06bm/understanding-java-beans-a-comprehensive-guide-for-beginners-684163011c82)
		- ```c++
		  public class EmployeeBean implements Serializable {
		  
		      private static final long serialVersionUID = -3760445487636086034L;
		      private String firstName;
		      private String lastName;
		      private LocalDate startDate;
		  
		      public EmployeeBean() {
		      }
		  
		      public EmployeeBean(String firstName, String lastName, LocalDate startDate) {
		          this.firstName = firstName;
		          this.lastName = lastName;
		          this.startDate = startDate;
		      }
		  
		      public String getFirstName() {
		          return firstName;
		      }
		  
		      public void setFirstName(String firstName) {
		          this.firstName = firstName;
		      }
		  
		      // additional getters and setters
		  }
		  ```
	- [DTO](https://www.baeldung.com/java-dto-pattern) (Data Transfer Object)
	  collapsed:: true
		- deve trasportare dati tra i moduli della mia app
		- ```c++
		  public class EmployeeDTO {
		  
		      private String firstName;
		      private String lastName;
		      private LocalDate startDate;
		  
		      // standard getters and setters
		  }
		  ```
	- [DAO](https://www.baeldung.com/java-dao-pattern) (Data Access Object)
	  collapsed:: true
		- interfaccia la mia app con il database
		- ```c++
		  public interface Dao<T> {
		      
		      Optional<T> get(long id);
		      
		      List<T> getAll();
		      
		      void save(T t);
		      
		      void update(T t, String[] params);
		      
		      void delete(T t);
		  }
		  ```
		- ```c++
		  public class UserDao implements Dao<User> {
		      
		      private List<User> users = new ArrayList<>();
		      
		      public UserDao() {
		          users.add(new User("John", "john@domain.com"));
		          users.add(new User("Susan", "susan@domain.com"));
		      }
		      
		      @Override
		      public Optional<User> get(long id) {
		          return Optional.ofNullable(users.get((int) id));
		      }
		      
		      @Override
		      public List<User> getAll() {
		          return users;
		      }
		      
		      @Override
		      public void save(User user) {
		          users.add(user);
		      }
		      
		      @Override
		      public void update(User user, String[] params) {
		          user.setName(Objects.requireNonNull(
		            params[0], "Name cannot be null"));
		          user.setEmail(Objects.requireNonNull(
		            params[1], "Email cannot be null"));
		          
		          users.add(user);
		      }
		      
		      @Override
		      public void delete(User user) {
		          users.remove(user);
		      }
		  }
		  ```
	- Converter
	  collapsed:: true
		- [Entity to DTO Conversion](https://www.baeldung.com/entity-to-and-from-dto-for-a-java-spring-application)
		- toBean, toDto (?)
	- Service
- MySQL
  collapsed:: true
	- DBConnection Class uses the [JDBC](https://docs.oracle.com/javase/tutorial/jdbc/basics/index.html) API
	- CRUD
		- Create
		- Read
		- Update
		- Delete
- [Authentication and Authorization](https://docs.oracle.com/en/java/javase/11/security/java-authentication-and-authorization-service-jaas-reference-guide.html#GUID-2A935F5E-0803-411D-B6BC-F8C64D01A25C)
  collapsed:: true
	- Authentication is the process of verifying who a user is, while Authorization is about verifying what they have access to
	- [JWT]((https://www.baeldung.com/java-json-web-tokens-jjwt))
	  collapsed:: true
		- JWTs (pronounced “jots”) are URL-safe, encoded, cryptographically signed (sometimes encrypted) strings that we can use as tokens in a variety of applications
		- ```json
		  <input name="_csrf" type="hidden" 
		      value="HEADER ({"alg":"HS256"}) .
		  			PAYLOAD ( ({		CLAIMS
		    						"jti": "e678f23347e3410db7e68767823b2d70",
		   						"iat": 1466633317,
		   						"nbf": 1466633317,
		   						"exp": 1466636917
		  						}) "/>) .
		  			SIGNATURE	computeHMACSHA256(
		      						header + "." + payload, 
		     							base64DecodeToByteArray("4pE8z3PBoHjnV1AhvGk+e8h2p+ShZpOnpr8cwHmMh1w=")
		  )
		  ```
		- JSON Web Tokens (JWT) are used for both authentication and authorization in web development.  When a user logs in, the server authenticates the user's credentials and if they are valid, the server generates a JWT that is sent back to the client. This token contains a payload of data, or claims about the user, which could include their user ID, role, or other identifying information.  For subsequent requests, the client sends this token back to the server in the HTTP Authorization header. The server then verifies the token and if it's valid, allows the request to proceed. This is the authorization process. The server knows that the requester is a legitimate user who has previously authenticated and it can also inspect the token's claims to determine if the user has the necessary permissions to perform the requested operation.
	- [OAuth](https://www.ramotion.com/blog/what-is-oauth-authentification/#:~:text=OAuth%20is%20an%20open%20standard,applications%20without%20compromising%20their%20passwords)
- Maven
  collapsed:: true
	- Dependency Management
		- Maven will find JARs for you
	- Building and Running your project
		- no more build path / classpath issues
	- Standard Directory Structure
	- POM
		- Project metadata
		- dependencies
			- GAV
				- Group ID
				- Artifact ID
				- Version
		- plugins
- Servlet and JSP
  collapsed:: true
	- [Servlet](https://docs.oracle.com/javaee%2F7%2Fapi%2F%2F/javax/servlet/Servlet.html)
		- Programma scritto in Java e residente su un server, in grado di gestire le richieste generate da uno o più client, attraverso uno scambio di messaggi tra il server ed i client stessi che hanno effettuato la richiesta. Tipicamente sono collocate all'interno di Application Server o Web Application Server come, ad esempio, Tomcat.
		- [HttpServlet](https://docs.oracle.com/javaee%2F7%2Fapi%2F%2F/javax/servlet/http/HttpServlet.html)
			- Parameters
				- `req` - an [HttpServletRequest](https://docs.oracle.com/javaee%2F7%2Fapi%2F%2F/javax/servlet/http/HttpServletRequest.html) object that contains the request the client has made of the servlet
				  collapsed:: true
					- [getAttribute](https://docs.oracle.com/javaee%2F7%2Fapi%2F%2F/javax/servlet/ServletRequest.html#getAttribute-java.lang.String-)
					- [setAttribute](https://docs.oracle.com/javaee%2F7%2Fapi%2F%2F/javax/servlet/ServletRequest.html#setAttribute-java.lang.String-java.lang.Object-)
					- [getRequestDispatcher](https://docs.oracle.com/javaee%2F7%2Fapi%2F%2F/javax/servlet/ServletRequest.html#getRequestDispatcher-java.lang.String-)
						- [forward](https://docs.oracle.com/javaee%2F7%2Fapi%2F%2F/javax/servlet/RequestDispatcher.html#forward-javax.servlet.ServletRequest-javax.servlet.ServletResponse-)
				- `resp` - an [HttpServletResponse](https://docs.oracle.com/javaee%2F7%2Fapi%2F%2F/javax/servlet/http/HttpServletResponse.html) object that contains the response the servlet sends to the client
					- [sendRedirect](https://docs.oracle.com/javaee%2F7%2Fapi%2F%2F/javax/servlet/http/HttpServletResponse.html#sendRedirect-java.lang.String-)
			- [doGet](https://docs.oracle.com/javaee%2F7%2Fapi%2F%2F/javax/servlet/http/HttpServlet.html#doGet-javax.servlet.http.HttpServletRequest-javax.servlet.http.HttpServletResponse-)
			  collapsed:: true
				- It's usually used to **preprocess** a request. I.e. doing some business stuff before presenting the HTML output from a JSP, such as gathering data for display in a table.
				- Retrieve a representation of a resource
				  collapsed:: true
				  SAFE - IDEMPOTENT
					- SAFE = without any side effects for which users are held responsible
					- IDEMPOTENT = it can be safely repeated
						- you get exactly the same result everytime you execute the request (leaving authorization/authentication and the time-sensitive nature of the page —search results, last news, etc— outside consideration)
				- Multiple identical requests return the same result
				- Corresponds to READ
				- ```jsp
				  <dl>
				      <dt>ID</dt>
				      <dd>${product.id}</dd>
				      <dt>Name</dt>
				      <dd>${product.name}</dd>
				      <dt>Description</dt>
				      <dd>${product.description}</dd>
				      <dt>Price</dt>
				      <dd>${product.price}</dd>
				      <dt>Image</dt>
				      <dd><img src="productImage?id=${product.id}" /></dd>
				  </dl>
				  ```
				- ```java
				  @WebServlet("/product")
				  public class ProductServlet extends HttpServlet {
				  
				      @EJB
				      private ProductService productService;
				  
				      @Override
				      protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
				          Product product = productService.find(request.getParameter("id"));
				          request.setAttribute("product", product); // Will be available as ${product} in JSP
				          request.getRequestDispatcher("/WEB-INF/product.jsp").forward(request, response);
				      }
				  
				  }
				  ```
			- [doPost](https://docs.oracle.com/javaee%2F7%2Fapi%2F%2F/javax/servlet/http/HttpServlet.html#doPost-javax.servlet.http.HttpServletRequest-javax.servlet.http.HttpServletResponse-)
			  collapsed:: true
				- usually used to **postprocess** a request. I.e. gathering data from a submitted HTML form and doing some business stuff with it (conversion, validation, saving in DB, etcetera). Finally usually the result is presented as HTML from the forwarded JSP page.
				- Used to create new resources
				  NOT SAFE - NOT IDEMPOTENT
				- corresponds to CREATE
				- ```jsp
				  <form action="login" method="post">
				      <input type="text" name="username">
				      <input type="password" name="password">
				      <input type="submit" value="login">
				      <span class="error">${error}</span>
				  </form>
				  ```
				- ```java
				  @WebServlet("/login")
				  public class LoginServlet extends HttpServlet {
				  
				      @EJB
				      private UserService userService;
				  
				      @Override
				      protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
				          String username = request.getParameter("username");
				          String password = request.getParameter("password");
				          User user = userService.find(username, password);
				  
				          if (user != null) {
				              request.getSession().setAttribute("user", user);
				              response.sendRedirect("home");
				          }
				          else {
				              request.setAttribute("error", "Unknown user, please try again");
				              request.getRequestDispatcher("/login.jsp").forward(request, response);
				          }
				      }
				  
				  }
				  ```
			- [doPut](https://docs.oracle.com/javaee%2F7%2Fapi%2F%2F/javax/servlet/http/HttpServlet.html#doPut-javax.servlet.http.HttpServletRequest-javax.servlet.http.HttpServletResponse-)
			  collapsed:: true
				- Update or Create a resource
				  NOT SAFE - IDEMPOTENT
				- Corresponds to UPDATE
				-
			- [doDelete](https://docs.oracle.com/javaee%2F7%2Fapi%2F%2F/javax/servlet/http/HttpServlet.html#doDelete-javax.servlet.http.HttpServletRequest-javax.servlet.http.HttpServletResponse-)
			  collapsed:: true
				- Used to delete a resource
				- corresponds to DELETE
			-
	- Servlets and JSP (JavaServer Pages) are both technologies used in Java for building web applications
	- JavaServer Pages (JSP) is a technology for developing web pages that support dynamic content which helps developers insert java code in HTML pages by making use of special JSP tags, most of which start with <% and end with %>. A JSP page is compiled into a Java servlet the first time it is accessed. After that, the generated servlet is used to service the incoming requests
	-
- [Singleton](https://www.javaboss.it/singleton-design-pattern/)
- [Spring](https://spring.io/)
	- Entity (replaces Bean)
	- JPA
	- Spring Container
		- Object Factory
	- Dependency Injection
		- **Dependency Inversion Principle**
			- The client delegates to another object the responsibility of providing its dependencies
		- **Dependency injection** is a pattern we can use to implement IoC, where the control being inverted is setting an object’s dependencies
			- **Constructor injection**
				- ```java
				  public interface Coach {
				      String getDailyWorkout();
				  }
				  ```
				- ```java
				  @Component
				  public class CricketCoach implements Coach{
				  
				          @Override
				          public String getDailyWorkout() {
				              return "Practice fast bowling for 15 minutes";
				          }
				  }
				  ```
				- By using DI, we can avoid specifying the implementation of the *Coach* that we want 
				  ```java
				  @RestController
				  public class DemoController {
				  
				      private Coach myCoach;
				  
				      @Autowired
				      public DemoController(Coach theCoach) {
				          myCoach = theCoach;
				      }
				  }
				  ```
				- Behind the scenes 
				  ```java
				  Coach theCoach = new CricketCoach;
				  DemoController demoController = new DemoController(theCoach);
				  ```
				- **Autowiring**
					- Injecting a *Coach* implementation
					- Spring will scan for *@Components*
					- Anyone implements the *Coach* interface?
					- If so, let's inject them. For example: *CricketCoach*
			- **Setter Injection**
	- [IoC | Inversion of Control](https://www.baeldung.com/inversion-control-and-dependency-injection-in-spring)
		- The approach of outsourcing the construction and management of objects
		- The control of object creation and lifecycle is transferred to the framework, rather than managed by the application code
	- REST
	  collapsed:: true
		- Controller
			- ```java
			  import org.springframework.web.bind.annotation.GetMapping;
			  import org.springframework.web.bind.annotation.RestController;
			  
			  @RestController
			  public class FunRestController {
			  
			      @GetMapping("/")
			      public String sayHello() {
			          return "Salve Mundi! ";
			      }
			  
			    // new endpoint (:= URI where the RESTful service can be accessed from)
			    // for "workout"
			  
			      @GetMapping("/workout")
			      public String getDailyWorkout() {
			          return "Run a hard 5k!";
			      }
			  }
			  
			  ```
			- The `@RestController` annotation tells Spring that this class will be used to handle HTTP requests. It's a hint to Spring to convert the return values of methods in this class into HTTP response bodies.
			- The `@GetMapping("/")` annotation is a composed annotation that acts as a shortcut for `@RequestMapping(method = RequestMethod.GET)`. It's used to map HTTP GET requests onto specific handler methods. In this case, it's mapping the root URL `("/")` to the `sayHello` method.
- [MVC](https://www.tutorialspoint.com/design_pattern/mvc_pattern.htm)
  collapsed:: true
	- ```java
	  public class MVCPatternDemo {
	     public static void main(String[] args) {
	  
	        //fetch student record based on his roll no from the database
	        Student model  = retriveStudentFromDatabase();
	  
	        //Create a view : to write student details on console
	        StudentView view = new StudentView();
	  
	        StudentController controller = new StudentController(model, view);
	  
	        controller.updateView();
	  
	        //update model data
	        controller.setStudentName("John");
	  
	        controller.updateView();
	     }
	  
	     private static Student retriveStudentFromDatabase(){
	        Student student = new Student();
	        student.setName("Robert");
	        student.setRollNo("10");
	        return student;
	     }
	  }
	  ```
	- **Model** - Model represents an object or POJO carrying data. It can also have logic to update controller if its data changes
	  collapsed:: true
		- ```java
		  public class Student {
		     private String rollNo;
		     private String name;
		     
		     public String getRollNo() {
		        return rollNo;
		     }
		     
		     public void setRollNo(String rollNo) {
		        this.rollNo = rollNo;
		     }
		     
		     public String getName() {
		        return name;
		     }
		     
		     public void setName(String name) {
		        this.name = name;
		     }
		  }
		  ```
	- **View** - View represents the visualization of the data that model contains
	  collapsed:: true
		- ```java
		  public class StudentView {
		     public void printStudentDetails(String studentName, String studentRollNo){
		        System.out.println("Student: ");
		        System.out.println("Name: " + studentName);
		        System.out.println("Roll No: " + studentRollNo);
		     }
		  }
		  ```
		-
	- **Controller** - Controller acts on both model and view. It controls the data flow into model object and updates the view whenever data changes. It keeps view and model separate
	  collapsed:: true
		- ```java
		  public class StudentController {
		     private Student model;
		     private StudentView view;
		  
		     public StudentController(Student model, StudentView view){
		        this.model = model;
		        this.view = view;
		     }
		  
		     public void setStudentName(String name){
		        model.setName(name);		
		     }
		  
		     public String getStudentName(){
		        return model.getName();		
		     }
		  
		     public void setStudentRollNo(String rollNo){
		        model.setRollNo(rollNo);		
		     }
		  
		     public String getStudentRollNo(){
		        return model.getRollNo();		
		     }
		  
		     public void updateView(){				
		        view.printStudentDetails(model.getName(), model.getRollNo());
		     }	
		  }
		  ```