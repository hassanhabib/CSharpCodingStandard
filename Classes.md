## 4 Classes

### 4.0 Naming
Classes that represent services or brokers in an MBSCV architecture should represent the type of class in their naming convention, however that doesn't apply to models.

#### 4.0.0 Models
##### Do
```cs
class Student {
	...
}
```
##### Don't
```cs
class StudentModel {

}
```
<br />

#### 4.0.1 Services
In a singular fashion, for any class that contains business logic.
##### Do
```cs
class StudentService {
	....
}
```
##### Don't
```cs
class StudentsService{
	...
}
```
##### Also, Don't
```cs 
class StudetnBusinessLogic {
	...
}
```
##### Also, Don't
```cs
class StudentBL {
	...
}
```
<br />

#### 4.0.2 Brokers
In a singular fashion, for any class that is a shim between your services and external resources.
##### Do
```cs
class StudentBroker {
	....
}
```
##### Don't
```cs
class StudentsBroker {
	...
}
```
<br />

#### 4.0.3 Controllers
In a plural fashion, to reflect endpoints such as ```/api/students``` to expose your logic via RESTful operations.
##### Do
```cs
class StudentsController {
	....
}
```
##### Don't
```cs
class StudentController {
	...
}
```

<br /> <br />
### 4.1 Fields
A field is a variable of any type that is declared directly in a class or struct. Fields are members of their containing type.

#### 4.1.0 Naming
Class fields are named in a camel cased fashion.
##### Do
```cs
class StudentsController {
	private readonly string studentName;
}
```
##### Don't
```cs
class StudentController {
	private readonly string StudentName;
}
```
##### Also, Don't
```cs
class StudentController {
	private readonly string _studentName;
}
```
Should follow the same rules for naming as mentioned in the Variables sections.

<br />

#### 4.1.1 Referencing
When referencing a class private field, use ```this``` keyword to distinguish private class member from a scoped method or constructor level variable.
##### Do
```cs
class StudentsController {
	private readonly string studentName;
	
	public StudentsController(string studentName) {
		this.studentName = studentName;
	}
}
```
##### Don't
```cs
class StudentController {
	private readonly string _studentName;

	public StudentsController(string studentName) {
		_studentName = studentName;
	}
}
```


