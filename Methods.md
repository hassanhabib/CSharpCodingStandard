## 1 Methods

### 1.0 Naming
Method names should be a summary of what the method is doing, it needs to stay percise and short and representative of the operation with respect to synchrony.

#### 1.0.0 Verbs
Method names must contain verbs in them to represent the action it performs.
##### Do
```cs
public List<Student> GetStudents()
{
	...
}

```
##### Don't
```cs
public List<Student> Students()
{
	...
}
```
<br />

#### 1.0.1 Asynchronousy
Asynchronous methods should be postfixed by the term ```Async``` such as methods returning ```Task``` or ```ValueTask``` in general.
##### Do
```cs
public async ValueTask<List<Student> GetStudentsAsync()
{
	...
}
```
##### Don't
```cs
public async ValueTask<List<Student> GetStudents()
{
	...
}
```
<br />

#### 1.0.2 Input Parameters
Input parameters should be explicit about what property of an object they will be assigned to, or will be used for any action such as search.
##### Do
```cs
public async ValueTask<Student> GetStudentByNameAsync(string studentName)
{
	...
}
```
##### Don't
```cs
public async ValueTask<Student> GetStudentByNameAsync(string text)
{
	...
}
```
##### Also, Don't
```cs
public async ValueTask<Student> GetStudentByNameAsync(string name)
{
	...
}
```
<br />

#### 1.0.3 Action Parameters
If your method is performing an action with a particular parameter specify it.
##### Do
```cs
public async ValueTask<Student> GetStudentByIdAsync(Guid studentId)
{
	...
}

```
##### Don't
```cs
public async ValueTask<Student> GetStudentAsync(Guid studentId)
{
	...
}
```
<br /><br />

### 1.1 Organization
In general encapsulate multiple lines of the same logic into their own method, and keep your method at level 0 of details at all times.

#### 1.1.0 One-Liners
Any method that contains only one line of code should use fat arrows
##### Do
```cs
public List<Student> GetStudents() => this.storageBroker.GetStudents();

```
##### Don't
```cs
public List<Student> Students()
{
	return this.storageBroker.GetStudents();
}
```

If a one-liner method exceeds the length of 120 characters then break after the fat arrow with an extra tab for the new line.

##### Do
```cs
public async ValueTask<List<Student>> GetAllWashingtonSchoolsStudentsAsync() => 
	await this.storageBroker.GetStudentsAsync();
```

##### Don't
```cs
public async ValueTask<List<Student>> GetAllWashingtonSchoolsStudentsAsync() => await this.storageBroker.GetStudentsAsync();
```
<br />

#### 1.1.1 Returns
For multi-liner methods, take a new line between the method logic and the final return line (if any).
##### Do
```cs
public List<Student> GetStudents(){
	StudentsClient studentsApiClient = InitializeStudentApiClient();

	return studetnsApiClient.GetStudents();
}
```

##### Don't
```cs
public List<Student> GetStudents(){
	StudentsClient studentsApiClient = InitializeStudentApiClient();
	return studetnsApiClient.GetStudents();
}
```