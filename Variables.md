# The Standard

## 0. Variables

### 0.0 Naming
Variable names should be concise and representative of nature and the quantity of the value it holds or will potentially hold.

#### 0.0.0 Names
##### Do
```cs
var student = new Student();
```
##### Don't
```cs
var s = new Student();
```

The same applies to lambda expressions:
##### Do
```cs
students.Where(student => student ... );
```
##### Don't
```cs
studetns.Where(s => s ... );
```
<br />

#### 0.0.1 Plurals 
##### Do
```cs
var students = new List<Student>();
```
##### Don't
```cs
var studentList = new List<Student>();
```
<br />

#### 0.0.2 Names with Types

##### Do
```cs
var student = new Student();
```
##### Don't
```cs
var studentModel = new Student();
```
<br /> <br />
### 0.1 Declarations
Declaring a variable and instantiating it should indicate the immediate type of the variable, even if the value is to be determined later.
#### 0.1.0 Clear Types
If the right side type is clear, then use ```var``` to declare your variable
##### Do
```cs
var student = new Student();
```
##### Don't
```cs
Student student = new Student();
````

<br />

#### 0.1.1 Semi-Clear Types
If the right side isn't clear (but known) of the returned value type, then you must explicitly declare your variable with it's type.
##### Do
```cs
Student student = GetStudent();
```
##### Don't
```cs
var student = GetStudent();
```

<br />

#### 0.1.2 Unclear Types 
If the right side isn't clear and unknown (such as an API call) of the returned value type, you may use ```var``` as your variable type.
##### Do
```cs
var student = await GetStudentAsync();
```

#### Don't
```cs
HttpResponseMessage student = await httpClient.GetAsync("https:// ... ");
``` 