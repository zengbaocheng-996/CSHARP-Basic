| VALUE TYPES                                    | REFERENCE TYPES                          |
| ---------------------------------------------- | ---------------------------------------- |
| int<br />float<br />enum<br />bool<br />struct | class<br />object<br />array<br />string |

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class TestingValueRefTypes : MonoBehaviour
{
    private void Start()
    {
        int a = 7;
        int b = a;
        b = 5;
        Debug.Log(a);
        
        MyClass first = new MyClass(7);
        MyClass second = first;
        second.value = 5;
        Debug.Log("Class: " + first.value);
        
        MyStruct firstStruct = new MyStruct(7);
        MyStruct secondStruct = firstStruct;
        second.value = 5;
        Debug.Log("Struct: " + firstStruct.value);
    }
}

public class MyClass
{
    public int value;
    
    public MyClass(int value)
    {
        this.value = value;
    }
}

public struct MyStruct
{
    public int value;
    
    public MyStruct(int value)
    {
        this.value = value;
    }
}
```

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

using Unity.Jobs;
using Unity.Build;
using Unity.Burst;

public class TestingValueRefTypes : MonoBehaviour
{
    private void Start()
    {
        NativeArray<MyStruct> testNativeArray = new NativeArray<MyStruct>(new MyStruct[]{
            new MyStruct(1),
            new MyStruct(2),
            new MyStruct(3)
        }, Allocator.Temp);
        
        TestJob testJob = new TestJob{ testNativeArray = testNativeArray };
        testJob.Run();
        
        for(int i = 0; i < testNativeArray.Length; i++)
        {
            Debug.Log(testNativeArray[i]);
        }
        
        testNativeArray.Dispose();
    }
}

public class MyClass
{
    public int value;
    
    public MyClass(int value)
    {
        this.value = value;
    }
}

public struct MyStruct
{
    public int value;
    
    public MyStruct(int value)
    {
        this.value = value;
    }
}

public struct TestJob : IJob
{
    /* error
    public NativeArray<MyClass> testNativeArray;
    */
    public NativeArray<MyStruct> testNativeArray;
    public void Execute()
    {
        for(int i = 0; i < testNativeArray.Length; i++)
        {
            MyStruct myStruct = testNativeArray[i];
            myStruct.value++;
            //
            testNativeArray[i] = myStruct;
        }
    }
}
```

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class TestingValueRefTypes : MonoBehaviour
{
    private void Start()
    {
        /* error
        int i = null;
        */
        int? i = null;
        Nullable<int> i = null;
        
        int i = 5;
        Increment(i);
        Debug.Log(i);
        
        Increment(ref i);
        Debug.Log(i);
    }
}

public void Increment(int i)
{
    i++;
}

public void Increment(ref int i)
{
    i++;
}
```

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class TestingValueRefTypes : MonoBehaviour
{
    private void Start()
    {
        WeaponTypes? playerHoldingWeaponType = null;
    }
    
    public enum WeaponTypes
    {
        Sword,
        Pistol,
    }
}
```

