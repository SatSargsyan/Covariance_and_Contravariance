# Covariance and Contravariance

In C#,<a href=https://msdn.microsoft.com/en-us/library/mt654055.aspx> covariance and contravariance</a> enable implicit reference conversion for array types, delegate types, and generic type arguments. Covariance preserves assignment compatibility and contravariance reverses it.
The following code demonstrates the difference between assignment compatibility, covariance, and contravariance
```C#
// Assignment compatibility.   
string str = "test";  
// An object of a more derived type is assigned to an object of a less derived type.   
object obj = str;  
  
// Covariance.   
IEnumerable<string> strings = new List<string>();  
// An object that is instantiated with a more derived type argument   
// is assigned to an object instantiated with a less derived type argument.   
// Assignment compatibility is preserved.   
IEnumerable<object> objects = strings;  
  
// Contravariance.             
// Assume that the following method is in the class:   
// static void SetObject(object o) { }   
Action<object> actObject = SetObject;  
// An object that is instantiated with a less derived type argument   
// is assigned to an object instantiated with a more derived type argument.   
// Assignment compatibility is reversed.   
Action<string> actString = actObject;  
```


###Covariance and Contravariance in Generics

<a href=https://msdn.microsoft.com/en-us/library/dd799517(v=vs.110).aspx>Covariance and contravariance </a>are terms that refer to the ability to use a less derived (less specific) or more derived type (more specific) than originally specified. Generic type parameters support covariance and contravariance to provide greater flexibility in assigning and using generic types. When you are referring to a type system, covariance, contravariance, and invariance have the following definitions. The examples assume a base class named Base and a derived class named Derived.
<ul>
<li>Covariance
Enables you to use a more derived type than originally specified.
You can assign an instance of IEnumerable`<Derived>` (IEnumerable(Of Derived) in Visual Basic) to a variable of type IEnumerable`<Base>`.
<li>Contravariance
Enables you to use a more generic (less derived) type than originally specified.
You can assign an instance of IEnumerable`<Base> (IEnumerable(Of Base) in Visual Basic) to a variable of type IEnumerable`<Derived>`.
<li>Invariance
Means that you can use only the type originally specified; so an invariant generic type parameter is neither covariant nor contravariant.
You cannot assign an instance of IEnumerable `<Base>`(IEnumerable(Of Base) in Visual Basic) to a variable of type IEnumerable`<Derived>` or vice versa.
</ul>

####Covariant type parameters enable you to make assignments that look much like ordinary Polymorphism, as shown in the following code.

```C#

```
