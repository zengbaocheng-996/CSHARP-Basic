Publishers

```c#
using System;
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
// Events 4
using UnityEngine.Events;

public class TestingEvents : MonoBehaviour
{
    // Events 1
    public event EventHandler<OnSpacePressedEventArgs> OnSpacePressed;
    public class OnSpacePressedEventArgs : EventArgs
    {
        public int spaceCount;       
    }
    // Events 2
    public event TestEventDelegate OnFloatEvent;
    public delegate void TestEventDelegate(float f);
    // Events 3
    public event Action<bool, int> OnActionEvent;
    // Events 4
    public UnityEvent OnUnityEvent;
    
    private int spaceCount;
    
    /*
    private void Start()
    {
        OnSpacePressed += Testing_OnSpacePressed;
    }
    
    private void Testing_OnSpacePressed(object sender, EventArgs e)
    {
        Debug.Log("Space!");
    }
    */
    
    private void Update()
    {
        if(Input.GetKeyDown(KeyCode.Space))
        {
            // Space pressed!
            // if(OnSpacePressed != null) OnSpacePressed(this, EventArgs.Empty);
            // OnSpacePressed?.Invoke(this, EventArgs.Empty);
            spaceCount++;
            // Events 1
            OnSpacePressed?.Invoke(this, new OnSpacePressedEventArgs{ spaceCount = spaceCount });
            // Events 2
            OnFloatEvent?.Invoke(5.5f);
            // Events 3
            OnActionEvent?.Invoke(true, 56);
            // Events 4
            OnUnityEvent?.Invoke();
        }
    }
}
```

Subscribers

```c#
using System;
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class TestingEventSubscriber : MonoBehaviour
{
    private void Start()
    {
        TestingEvents testingEvents = GetComponent<TestingEvents>();
        // Events 1
        testingEvents.OnSpacePressed += TestingEvents_OnSpacePressed;
        // Events 2
        testingEvents.OnFloatEvent += TestingEvents_OnFloatEvent;
        // Events 3
        testingEvents.OnActionEvent += TestingEvents_OnActionEvent;
    }
    // Events 1
    private void TestingEvents_OnSpacePressed(object sender, TestingEvents.OnSpacePressedEventArgs e)
    {
        Debug.Log("Space! " + e.spaceCount);
        // TestingEvents testingEvents = GetComponent<TestingEvents>();
        // testingEvents.OnSpacePressed -= TestingEvents_OnSpacePressed;
    }
    // Events 2
    private void TestingEvents_OnFloatEvent(float f)
    {
        Debug.Log("Float: " + f);
    }
    // Events 3
    private void TestingEvents_OnActionEvent(bool arg1, int arg2)
    {
        Debug.Log(arg1 + " " + arg2);
    }
    // Events 4
    public void Testing UnityEvents()
    {
        Debug.Log("TestingUnityEvent");
    }
}
```

