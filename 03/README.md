```c#
using System;
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Testing : MonoBehaviour
{
    // Delegates 1
    public delegate void TestDelegate();
    public delegate bool TestBoolDelegate(int i);
    
    private TestDelegate testDelegateFunction;
    private TestBoolDelegate testBoolDelegateFunction;
    // Delegates 2
    private Action testAction;
    private Action<int, float> testIntFloatAction;
    // Delegates 3
    private Func<bool> testFunc;
    private Func<int, bool> testIntBoolFunc;
    private void Start()
    {
        // Delegates 1
        // testDelegateFunction = new TestDelegate(MyTestDelegateFunction);
        testDelegateFunction = MyTestDelegateFunction;
        testDelegateFunction();
        
        testDelegateFunction = MySecondTestDelegateFunction;
        testDelegateFunction();
        
        testDelegateFunction += MyTestDelegateFunction;
        testDelegateFunction += MySecondTestDelegateFunction;
        testDelegateFunction();
        
        testDelegateFunction -= MySecondTestDelegateFunction;
        testDelegateFunction();
        
        testBoolDelegateFunction = MyTestBoolDelegateFunction;
        Debug.Log(testBoolDelegateFunction(1));
        
        testDelegateFunction = delegate () { Debug.Log("Anonymous method"); };
        testDelegateFunction();
        
        testDelegateFunction = () => { Debug.Log("Lambda expression"); };
        testDelegateFunction();
        
        // testBoolDelegateFunction = (int i) => { return i < 5; };
        testBoolDelegateFunction = (int i) => i < 5;
        Debug.Log(testBoolDelegateFunction(1));
        
        testDelegateFunction += () => { Debug.Log("Lambda expression"); };
        testDelegateFunction += () => { Debug.Log("Second Lambda expression"); };
        testDelegateFunction();
        // Delegates 2
        testIntFloatAction = (int i, float f) => { Debug.Log("Test int float action!")};
        
        // Delegates 3
        testFunc = () => false;
        testIntBoolFunc = (int i) => i < 5;
    };
	
    private void MyTestDelegateFunction()
    {
        Debug.Log("MyTestDelegateFunction");
    }
    
    private void MySecondTestDelegateFunction
    {
        Debug.Log("MySecondTestDelegateFunction");
    }
    
    private bool MyTestBoolDelegateFunction(int i)
    {
        return i < 5;
    }
}
```

