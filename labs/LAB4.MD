## DOCUMENTATION

- [Classes and Objects](https://www.geeksforgeeks.org/classes-objects-java/)
- [Constructors](https://www.w3schools.com/java/java_constructors.asp)
- [Access modifiers (public, private protected)](https://www.tutorialspoint.com/java/java_access_modifiers.htm)
- [Static vs Instance Methods](https://www.geeksforgeeks.org/static-methods-vs-instance-methods-java/)
- [Static and Instance Variables](https://stackoverflow.com/questions/21204589/static-vs-instance-variables-difference)


# EXERCISES

> Assign and print the  phone number and address of two students having names "Sam" and "John" respectively by creating two objects of class 'Student'

```
// Student.java
public class Student {
	Integer phoneNumber;
	String address;
	String name;
	public Student(Integer v1, String v2, String v3){
		this.phoneNumber=v1;
		this.address=v2;
		this.name=v3;
	}
	public String toString() {
		return this.phoneNumber + " " + this.name + " " + this.address;
		}
}

// main()
	Student s1= new Student(123456,"Sibiu","Sam");
	System.out.println(s1);
	Student s2= new Student(9876,"Bucuresti","John");
	System.out.println(s2);
```

> Același lucru ca mai sus, doar ca se foloseste de class Address pentru a stoca adresa

```  
// Student.java
public class Student {
    private String name;
    private Address address;
    private Integer age;

    public Student(String name, Address address, Integer age) {
        this.name = name;
        this.address = address;
        this.age = age;
    }

    @Override
    public String toString() {
        return "Student{" +
                "name='" + name + '\'' +
                ", address=" + address +
                ", age=" + age +
                '}';
    }
}

// Address.java
public class Address {
    String city;
    String street;
    String number;

    public Address(String city, String street, String number) {
        this.city = city;
        this.street = street;
        this.number = number;
    }

    @Override
    public String toString() {
        return "Address{" +
                "city='" + city + '\'' +
                ", street='" + street + '\'' +
                ", number='" + number + '\'' +
                '}';
    }
}

// main()
	Address a1 = new Address("Sibiu", "Mihai Viteazu", "11");
	Student s1 = new Student("Jhon", a1,22);
	Student s2 = new Student("Sammy", a1, 23);
	System.out.println(s1);
	System.out.println(s2);
```

> Write a program to print the area and perimeter of a triangle having sides of 3, 4 and 5 units by creating a class named 'Triangle' without any parameter in its constructor.
```
// Triangle.java
public class Triangle {
    static int perimetru(int a, int b, int c){
        int p=a+b+c;
        return p;
    }
}

// main()
	int p= Triangle.perimetru(3,4,5);
	System.out.println(p);	
```

# EXTRA
>  Write a program that would print the information (name, year of joining, salary, address) of three employees by creating a class named 'Employee'. The output should be as follows:  

| Name  | Year of joining   | Address | Salary|
|-|--|--|--|
|Robert |1994| 64C- WallsStreat | 3200|
|Sam |2000 | 68D- WallsStreat  | 700|
|John |1999 | 26B- WallsStreat | 4400|

```
// Employee.java
public class Employee {
    String name;
    float salary;
    String address;
    int year_of_joinning;
    public Employee(String name,int year_of_joinning, String address,float  salary){
        this.name=name;
        this.salary=salary;
        this.address=address;
        this.year_of_joinning=year_of_joinning;
    }
    void p_Parameters(){
      System.out.println(name+","+year_of_joinning+","+address+","+salary);
    }
}

// main()
	System.out.println("Name,"+"Year of joinning,"+"Address,"+"Salary:");
	Employee one=new Employee("Robert",1994,"64C-WallsStreat",3200);
	Employee two=new Employee("Sam",2000,"68B-WallsStreat",700);
	Employee three=new Employee("John",1999,"26B-WallsStreat",4200);
	one.p_Parameters();
	two.p_Parameters();
	three.p_Parameters();
```
> Write a program to print the area of a rectangle by creating a class named 'Area' taking the values of its length and breadth as parameters of its constructor and having a method named 'returnArea' which returns the area of the rectangle. Length and breadth of rectangle are entered through keyboard.
```
// Area.java
public class Area {
    private double length, width;

    public Area (double length, double width) {
        this.length = length;
        this.width = width;
    }

    public double returnArea () {
        return this.length * this.width;
    }
}

// main()
Scanner sc = new Scanner(System.in);
	double length, width;

	System.out.println("Introduceti marimile unui dreptunghi:");
	System.out.print("Length: ");
	length = sc.nextDouble();
	System.out.print("Width: ");
	width = sc.nextDouble();

	Area area = new Area(length, width);
	System.out.println("Area dreptunghilui este: " + area.returnArea());
```