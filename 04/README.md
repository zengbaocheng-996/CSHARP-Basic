```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Testing : MonoBehaviour
{
    private void Start()
    {
        MyClass myClass = new MyClass();
        TestInterface(myClass);
        
        MySecondClass mySecondClass = new MySecondClass();
        TestInterface(mySecondClass);
    }
    
    private void TestInterface(IMyInterface myInterface)
    {
        myInterface.TestFunction();
    }
}

public interface IMyInterface
{
    // event EventHandler OnMyEvent;
    // int MyInt { get; set; }
    void TestFunction();
}

/*public interface IMyInterface : IMySecondInterface
{
    void TestFunction();
}*/

public interface IMySecondInterface
{
    void SecondInterfaceFunction(int i);
}

public class MyClass : IMyInterface, IMySecondInterface
{
    public void SecondInterfaceFunction(int i)
    {
        
    }
    public void TestFunction()
    {
        Debug.Log("MyClass.TestFunction()");
    }
}

public class MySecondClass : IMyInterface
{
    public void TestFunction()
    {
        Debug.Log("MySecondClass");
    }
}
```

