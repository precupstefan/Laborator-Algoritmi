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


