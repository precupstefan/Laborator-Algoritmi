## DOCUMENTATION

- [Abstract classes - W3Schools](https://www.w3schools.com/java/java_abstract.asp)
- [Abstract classes - GeeksForGeeks](https://www.geeksforgeeks.org/abstract-classes-in-java/)
- [Interfaces](https://www.geeksforgeeks.org/interfaces-in-java/)
- [When to use abstract class and interface](https://dzone.com/articles/when-to-use-abstract-class-and-intreface)
- [Coupling in Java](https://www.geeksforgeeks.org/coupling-in-java/)
- [Java interfaces explained with examples](https://www.freecodecamp.org/news/java-interfaces-explained-with-examples/)
- [More on interfaces](http://www.corejavaguru.com/java/oop/interface)
- [Builder pattern - good example on when to use interfaces and abstract classes](https://www.tutorialspoint.com/design_pattern/builder_pattern.htm)
- [Serialization - C#](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/serialization/)


# EXERCISES

>Definiți clasa Person cu câmpurile name, address și age. Definiți clasa Student derivată din clasa Person având câmpul suplimentar grade (medie). Introduceți dintr-un fișier student.txt numărul de studenți din semigrupă urmat de datele lor, într-un tablou. Sortați și afișați studenții în ordinea crescătoare a mediei.
```
// Person.java
public class Person {
    private String name;
    private String address;
    private int age;

    public Person(String name, String address, int age) {
        this.name = name;
        this.address = address;
        this.age = age;
    }

    public Person() {}

    public String getName() {
        return name;
    }

    public String getAddress() {
        return address;
    }

    public int getAge() {
        return age;
    }
}


// Student.java
import java.util.Comparator;

public class Student extends Person implements Comparator<Student> {
    double grade;

    public Student(String name, String address, int age, double grade) {
        super(name, address, age);
        this.grade = grade;
    }

    public Student() {}

    public double getGrade() {
        return grade;
    }

    @Override
    public int compare(Student o1, Student o2) {
        return Double.compare(o1.getGrade(), o2.getGrade());
    }
}

// main.java
		Student[] s = new Student[4];

        s[0] = new Student("John", "Some address 1", 15, 9.5);
        s[1] = new Student("Doe", "Some address 2", 14, 8.6);
        s[2] = new Student("Name", "Some address 3", 16, 4.2);
        s[3] = new Student("Eman", "Some address 4", 14, 5);

        System.out.println("Before sort:");
        for (Student stud : s) {
            System.out.println(stud.getName() + " " + stud.getGrade());
        }
        System.out.println();

        Arrays.sort(s, new Student());

        System.out.println("After sort:");
        for (Student stud : s) {
            System.out.println(stud.getName() + " " + stud.getGrade());
        }
        System.out.println();
```
>Definiți clasa Person cu câmpurile name, address și age. Definiți clasa Student derivată din clasa Person având câmpul suplimentar grade (medie). Introduceți dintr-un fișier student.txt numărul de studenți din semigrupă urmat de datele lor, într-un tablou. Sortați și afișați studenții în ordinea crescătoare a mediei.
```
// Person.java
public class Person {
    String name ;
    String adress ;
    int age;
    public  Person(String name, String adress, int age) {
        this.name = name;
        this.adress = adress;
        this.age = age;
    }
}

// Teacher.java
public class Teacher extends Person implements Comparable{
    public int courses;

	public Teacher(String name, String adress, int age, int courses) {
		super(name, adress, age);
		this.courses = courses;
    }

	@Override
	public String toString() {
		return "Teacher [courses=" + courses + "]";
	}
	
    public int compareTo(Object o){
        return courses-((Teacher)o).courses;
    }
}

// main()
	Teacher teacher1 = new Teacher("Silviu","Sibiu", 21, 4);
    Teacher teacher2 = new Teacher("Marius","Timisoara", 26, 3);
    Teacher teacher3 = new Teacher("Matei","Bucuresti", 30, 6);
    Teacher[] teachers = {teacher1,teacher2,teacher3};
    Arrays.sort(teachers);
    for (Teacher teacher : teachers) {
	    System.out.println(teacher);
    }
```
>Definiți clasa Product cu câmpul price (preț). Definiți clasa Book (carte) derivată din clasa Product având câmpurile suplimentare title, author și publisher (editor). Introduceți dintr-un fișier book.txt numărul de cărți urmat de datele lor, într-un tablou. Sortați și afișați cărțile în ordinea crescătoare a prețului.
```
// Product.java
public class Product implements Comparable{
    int price;

    public Product(int price) {
        this.price = price;
    }

    public int compareTo(Object o){
        return price-((Product)o).price;
    }
}

// Book.java
public class Book extends Product{
    String title, author, publisher;

    public Book(String title, String author, String publisher,int price) {
        super(price);
        this.title = title;
        this.author = author;
        this.publisher = publisher;
    }

    @Override
    public String toString() {
        return "Book{" +
                "title='" + title + '\'' +
                ", author='" + author + '\'' +
                ", publisher='" + publisher + '\'' +
                ", price=" + price +
                '}';
    }
}

// main()
        Book B1 = new Book("Abc","a","Def",150);
        Book B2 = new Book("ABc","b","Def",100);
        Book B3 = new Book("ABC","c","Def", 125);
        Book books[] = {B1,B2,B3};
        
        java.util.Arrays.sort(books);
        for (int i=0; i<books.length; i++){
            System.out.println(books[i]);
        }
```
> Definiți clasa Book (carte) cu câmpurile title, author și publisher (editor). Definiți clasa LibraryCard (fișă de bibliotecă) derivată din clasa Book având câmpul suplimentar copies (nr. exemplare). Introduceți dintr-un fișier librarycard.txt numărul de fișe urmat de datele acestora, într-un tablou. Sortați și afișați cărțile în ordinea crescătoare a numărului de exemplare disponibile.

```
// Book.java
public  class Book {
    String title;
    String author;
    String publisher;

    Book (String title, String author, String publisher){
      this.title=title;
      this.author=author;
      this.publisher=publisher;
  }

  @Override
  public String toString() {
      return "Book [author=" + author + ", publisher=" + publisher + ", title=" + title + "]";
  }
  
}

//LibraryCard.java
public class LibraryCard extends Book implements Comparable  {

   Integer copies;

   public LibraryCard(String title, String author, String publisher, Integer copies) {
       super(title, author, publisher);
       this.copies = copies;
   }
  
	@Override
	public int compareTo(Object o) {
	    return copies-((LibraryCard)o).copies;	
	}
}


// main()
        LibraryCard V1=new LibraryCard("Morometii", "Marin Preda", "Delphi",100);
        LibraryCard V2=new LibraryCard("Enigma Otiliei","George Calinescu","Delphi",60);
        LibraryCard V3=new LibraryCard("Baltagul","Sadoveanu", "delphi", 1000);
        LibraryCard V4=new LibraryCard("Iona","Sorescu","delphi", 20);
      
        LibraryCard libraryCards[]={V1,V2,V3,V4};
        Arrays.sort(libraryCards);
        for(int i=0;i<libraryCards.length;i++){
		    System.out.println(libraryCards[i]);
	    }
```
>Definiți clasa Vehicle cu câmpul manufacturer (fabricant). Definiți clasa Car derivată din clasa Vehicle având câmpurile suplimentare model, length (lungime), maxSpeed (viteză maximă), price (preț). Introduceți dintr-un fișier
car.txt numărul de mașini, urmat de datele lor, într-un tablou. Sortați și afișați mașinile în ordinea crescătoare a prețului.
```
// Vehicle.java
public class Vehicle {
    String manufacturer;

    public Vehicle(String manufacturer) {
        this.manufacturer = manufacturer;
    }

    public Vehicle() {}

    public String getManufacturer() {
        return manufacturer;
    }
}

// Car.java
import java.util.Comparator;

public class Car extends Vehicle implements Comparator<Car> {
    String model;
    double length;
    double maxSpeed;
    double price;

    public Car(String manufacturer, String model, double length, double maxSpeed, double price) {
        super(manufacturer);
        this.model = model;
        this.length = length;
        this.maxSpeed = maxSpeed;
        this.price = price;
    }

    public Car() {
        super();
    }

    public String getModel() {
        return model;
    }

    public double getPrice() {
        return price;
    }

    @Override
    public int compare(Car o1, Car o2) {
        return Double.compare(o1.getPrice(), o2.getPrice());
    }
}

// main()
		Car[] c = new Car[4];

        c[0] = new Car("Volvo", "123", 15, 9.5, 5620);
        c[1] = new Car("Volkswagen", "321", 14, 8.6, 4000);
        c[2] = new Car("BMW", "asd", 16, 4.2, 2300);
        c[3] = new Car("Mercedes", "dsa4", 14, 5, 1250);

        System.out.println("Before sort:");
        for (Car car : c) {
            System.out.println(car.getManufacturer() + " " + car.getModel() + " " + car.getPrice());
        }
        System.out.println();

        Arrays.sort(c, new Car());

        System.out.println("After sort:");
        for (Car car : c) {
            System.out.println(car.getManufacturer() + " " + car.getModel() + " " + car.getPrice());
        }
        System.out.println();
```