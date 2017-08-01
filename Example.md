#
### [Example](http://www.csharpstar.com/covariance-csharp-interface/)
```C#
class Animal { public string Name; }
class Dog: Animal{ };
interface IMyInterfacecovariance<out T>//Out Keyword for covariance
{
    T GetFirst();
}
class SimpleReturn<T> : IMyInterfacecovariance<T>
{
    public T[] items = new T[2];
    public T GetFirst() { return items[0]; }
}
class Program
{
    static void DoSomething(IMyInterfacecovariance<Animal> returner)
    {
        Console.WriteLine(returner.GetFirst().Name);
    }
    static void Main()
    {
        SimpleReturn<Dog> dogReturner = new SimpleReturn<Dog>();
        dogReturner.items[0] = new Dog() { Name = "Tommy" };
        IMyInterfacecovariance<Animal> animalReturner = dogReturner;
        DoSomething(dogReturner);
    }
}
```
