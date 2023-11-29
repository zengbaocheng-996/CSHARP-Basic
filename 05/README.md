```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class TestingGenerics : MonoBehaviour
{
    private void Start()
    {
        int [] intArray = CreateArray(5, 6);
        Debug.Log(intArray.Length + " " + intArray[0] + " " + intArray[1]);
        CreateArray("a", "b");
    }
    
    private int[] CreateArray(int firstElement, int secondElement)
    {
        return new int[] { firstElement, secondElement };
    }
    
    private string[] CreateArray(string firstElement, string secondElement)
    {
        return new string[] { firstElement, secondElement };
    }
}
```

```c#
using System;
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class TestingGenerics : MonoBehaviour
{
    private delegate void MyActionDelegate<T1, T2>(T1 t1, T2 t2);
    private Action<int, string> action;
    
    private delegate TResult MyFuncDelegate<T1, TResult>(T1 t1);
    private Func<int, bool> func;
    
    private void Start()
    {
        // int [] intArray = CreateArray<int>(5, 6);
        int [] intArray = CreateArray(5, 6);
        Debug.Log(intArray.Length + " " + intArray[0] + " " + intArray[1]);
        Debug.Log(intArray.GetType());
        // Debug.Log(CreateArray<string>("a", "b").GetType());
        Debug.Log(CreateArray("a", "b").GetType());
        
        CreateArray(5, 6);
        
        TestMultiGenerics<int, string>(56, "asdf");
        
        MyClass<EnemyMinion> myClass = new Class<EnemyMinion>();
        MyClass<EnemyArcher> myClassArcher = new Class<EnemyArcher>();
    }
    
    private T[] CreateArray<T>(T firstElement, T secondElement)
    {
        return new T[] { firstElement, secondElement };
    }
    
    private void TestMultiGenerics<T1, T2>(T1 t1, T2 t2)
    {
        Debug.Log(t1.GetType());
        Debug.Log(t2.GetType());
    }
}

// IEnemy struct class new()
public class MyClass<T> where T : class, IEnemy<int>, new()
{
    public T value;
    
    public MyClass(T value)
    {
        value.Damage(0);
    }
    
    private T[] CreateArray(T firstElement, T secondElement)
    {
        return new T[] { firstElement, secondElement };
    }
}

public interface IEnemy<T>
{
    void Damage(T t);
}

public class EnemyMinion : IEnemy<int>
{
    public void Damage(int i)
    {
        Debug.Log("EnemyMinion.Damage()");
    }
}

public class EnemyArcher : IEnemy<int>
{
    public void Damage(int i)
    {
        Debug.Log("EnemyArcher.Damage()");
    }
}
```

