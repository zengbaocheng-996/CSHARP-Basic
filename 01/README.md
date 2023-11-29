```c#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace CS_Basics
{
    class Program
    {
        // Enums
        /*
        enum PlayerState
        {
            Idle,
            Attacking
        }
        static PlayerState playerState;
        */
        
        // Scope
        static int i;
        static void Main(string[] args)
        {       
            // Enums
        	/*
            switch(playerState)
            {
                case PlayerState.Idle:
                    break;
                case PlayerState.Attacking:
                    break;
            }
            */
            
            // Variables Functions
            /*
            int i = 56;
            Console.WriteLine("Hello World!" + i);
            TestFunction();
            bool b = SecondTestFunction(50);
            */        
            
            // Conditions 1
            /*
            int i = 5;
            if(i < 10)
            {
                Console.WriteLine("True!");
            }
            else
            {
                Console.WriteLine("False!");
            }
            */
           
            // Conditions 2
            /*
            int i = 5;
            switch(i)
            {
                default:
                case 1:
                    Console.WriteLine("First case!");
                	break;
                case 5:
                    break;
            }
            */
                       
            // Collections 1
            /*
            int[] intArray = new int[5];
            int[] intArray = new int[]{1, 2, 3, 4, 5};*/
            
            // Collections 2
            /*List<int> intList = new List<int>(){1, 2, 3};
            intList.Add(5);
            intList.Remove(1);
            */
            
            // Loops 1
            /*
            int[] intArray = new int[]{1, 2, 3, 4, 5};
            foreach(int i in intArray)
            {
                Console.WriteLine(i);
            }
            List<int> intList = new List<int>(){1, 2, 3};
            foreach(int i in intList)
            {
                Console.WriteLine(i);
            }
            */
            
            // Loops 2
            /*
            List<int> intList = new List<int>(){1, 2, 3};
            for(int i = 0; i < intList.Count; i++)
            {
                Console.WriteLine(i + " " + intList[i]);
            }
            */
            
            // Loops 3
            /*
            int i = 0;
            while(i < 5)
            {
            	i++;
            }
            */
            
            // Loops 4
            /*
            int i = 0;
            do
            {
            	i++;
            } while(i < 5);
            */
            
            // Comments      
            // This is a comment
            /*
            *
            * Multi line comment!
            * I can write anything here!
            *
            */
            
            // Classes Accessors
            /*
            MyClass myClass = new MyClass();
			*/
            
            // Scope
            /*
            int i = 10;
            TestFunction();
            Console.ReadKey();
        	*/
        }
        
        // Scope
        /*
        static void TestFunction()
        {
            i++;
        }
        */
        
        // Classes Accessors
        /*
        class MyClass
        {
            private float myFloat;
            private int myInt;
            
            public MyClass()
            {
                // Custom constructor
            }
            private void TestFunction()
            {
                // Do something
            }
        }
        */
        
        // Variables Functions
        /*
        static void TestFunction()
        {
            
        }
        static bool SecondTestFunction(int i)
        {
            return i < 100;
        }
        */   
    }
}
```

