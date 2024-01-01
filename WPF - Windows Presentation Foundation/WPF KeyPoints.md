### C# Key differences with Java
* A solution can have mutiple project inside it.  
*  By default project and solution name is same, while creating project.
*  Default namespace in a project is same name as project name.  
For example, if you create a new console application named "MyConsoleApp," the default namespace for the Program class would be: MyConsoleApp
*  To classified classes in different names spaces Visual Studio doesn't automatically create a folder structure that mirrors the namespace. You have to create folders manually and organize your files within them.
*  Main method M must be capital.
*  String s is small in main method definition.
* Namespace name,class name,method name ,property name, event names - all must be in pascal case letters.  
*  Field (variables) names, method arguaments are in camel case letters.     
*  We have var keyword in C#.    
-- We don't use var to declear simple variables because then its difficult to recognize the type of variable.   
-- we use when its difficult to guess what is coming from right side expression.(because var does implicit type casting of variable as per the type of value recieving from right side.)





