# The Standard

## 0. Variables
Variable names should be concise and representative of nature and the quantity of the value it holds or will potentially hold.

#### 0.0 Names
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

#### 0.1 Plurals 
##### Do
```cs
var students = new List<Student>();
```
##### Don't
```cs
var studentList = new List<Student>();
```
<br />

#### 0.2 Names with Types

##### Do
```cs
var student = new Student();
```
##### Don't
```cs
var studentModel = new Student();
```


