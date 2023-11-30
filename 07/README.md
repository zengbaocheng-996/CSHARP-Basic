```c#
using System;
namespace StaticTest
{
	static void Main(string[] args)
    {
        Car car1 = new Car("Mustang");
        Car car2 = new Car("Corvette");

        Console.ReadKey();
    }
    class Car
    {
        String model;
        public Car(String model)
        {
            this.model = model;
        }
    }
}
```

Field

```c#
using System;
namespace StaticTest
{
	static void Main(string[] args)
    {
        Car car1 = new Car("Mustang");
        Car car2 = new Car("Corvette");
        Car car3 = new Car("Lambo");
        
        Console.WriteLine(Car.numberOfCars);
        Console.ReadKey();
    }
    class Car
    {
        String model;
        public static int numberOfCars;
        public Car(String model)
        {
            this.model = model;
            numberOfCars++;
        }
    }
}
```

Function

```c#
using System;
namespace StaticTest
{
	static void Main(string[] args)
    {
        Car car1 = new Car("Mustang");
        Car car2 = new Car("Corvette");
        Car car3 = new Car("Lambo");
        
        Console.WriteLine(Car.numberOfCars);
        
        Car.StartRace();
        
        Console.ReadKey();
    }
    class Car
    {
        String model;
        public static int numberOfCars;
        public Car(String model)
        {
            this.model = model;
            numberOfCars++;
        }
        public static void StartRace()
        {
            Console.WriteLine("The race has begun!");
        }
    }
}
```

Class

```c#
using System;
namespace StaticTest
{
	static void Main(string[] args)
    {
        /* error
        Car car1 = new Car("Mustang");
        Car car2 = new Car("Corvette");
        Car car3 = new Car("Lambo");
        */
        Console.WriteLine(Car.numberOfCars);
        
        Car.StartRace();
        
        /* error
        Math math1 = new Math();
       	math1.Round(3.14);
        */
        Math.Round();
        
        Console.ReadKey();
    }
    statcclass Car
    {
        String model;
        public static int numberOfCars;
        public Car(String model)
        {
            this.model = model;
            numberOfCars++;
        }
        public static void StartRace()
        {
            Console.WriteLine("The race has begun!");
        }
    }
}
```

