[Classes video](https://youtu.be/Iw9UN8oZ2h8)

```
// use "new" keyword to create new instance
StingBuilder name = new StringBuilder();
// class            object (instance of class)

```

### Creating Classes

```
public class Student {
// classes use Pascal case

	// properties
	
	static int numberOfStudents;

	String firstName;  // creating blueprint, don't assign value
	String lastName;
	String phoneNumber;
	int gradeLevel;

	// methods

	public void introduce() {
		System.out.println("Hello, my name is " + firstName + " " + lastName);
		System.out.println("I am in grade " + gradeLevel);
		System.out.println("My phone number is " + phoneNumber);
	}
}

public class Classes {
	
	public static void(String[] args) {

		Student student1 = new Student();
		student1.firstName = "Tom";
		student1.lastName = "Smith";
		student1.gradeLevel = 12;
		student1.phoneNumber = "555-555-5555";

		student1.introduce();
		// prints:
		// Hello, my name is Tom Smith
		// I am in grade 12
		// My phone number is 555-555-5555

		// create student using custructor methods (shown below)

		Student student2 = new Student("Sammy", "Jones");
		student2.introduce();
		// prints:
		// Hello, my name is Sammy Jones
		// I am in grade 0
		// My phone number is null

		Student student3 = new Student("Tom", "Riddle", "555-555-5555", 11);
		student3.introduce();
		// prints:
		// Hello, my name is Tom Riddle
		// I am in grade 11
		// My phone number is 555-555-5555

	}
}
```

### Using dot notation can become cumbersome, so classes have constructor methods.

```
// To create a constructor in the class:

public Student() {} // overloaded version makes this available instead of Java's default

public Student(String firstName, String lastName) {
	this.firstName = firstName;
	this.lastName = lastName;
}

public Student(String firstName, String lastName, String phoneNumber, int gradeLevel) {
	this.firstName = firstName; // 'this' inside a class represents the specific instance
	this.lastName = lastName;
	this.phoneNumber = phoneNumber;
	this.gradeLevel = gradeLevel;
}
```
