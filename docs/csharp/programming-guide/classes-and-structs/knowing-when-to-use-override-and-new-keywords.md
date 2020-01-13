---
title: Руководство по программированию на C#. Использование ключевых слов Override и New
ms.date: 07/20/2015
helpviewer_keywords:
- override keyword [C#]
- new keyword [C#]
- polymorphism [C#], using override and new [C#]
ms.assetid: 323db184-b136-46fc-8839-007886e7e8b0
ms.openlocfilehash: 0a209b9522202649765654013fdc3a468913c6b1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714781"
---
# <a name="knowing-when-to-use-override-and-new-keywords-c-programming-guide"></a>Использование ключевых слов "Override" и "New" (Руководство по программированию в C#)

В C# метод в производном классе может иметь то же имя, что и метод в базовом классе. Можно задать способ взаимодействия методов, воспользовавшись ключевыми словами [new](../../language-reference/keywords/new-modifier.md) и [override](../../language-reference/keywords/override.md). Модификатор `override`*расширяет* метод `virtual` базового класса, а модификатор `new`*скрывает* доступный метод базового класса. Эта разница показана в примере в этой статье.  
  
 В консольном приложении объявите два класса — `BaseClass` и `DerivedClass`. Тип`DerivedClass` наследуется от типа `BaseClass`.  
  
```csharp  
class BaseClass  
{  
    public void Method1()  
    {  
        Console.WriteLine("Base - Method1");  
    }  
}  
  
class DerivedClass : BaseClass  
{  
    public void Method2()  
    {  
        Console.WriteLine("Derived - Method2");  
    }  
}  
```  
  
 В методе `Main` объявите переменные `bc`, `dc` и `bcdc`.  
  
- Параметр `bc` имеет тип `BaseClass` и его значение — тип `BaseClass`.  
  
- Параметр `dc` имеет тип `DerivedClass` и его значение — тип `DerivedClass`.  
  
- Параметр `bcdc` имеет тип `BaseClass` и его значение — тип `DerivedClass`. Это переменная, на которую следует обратить внимание.  
  
 Поскольку `bc` и `bcdc` имеют тип `BaseClass`, они могут только напрямую обращаться к методу `Method1` (если не используется приведение). Переменная `dc` может обращаться к `Method1` и `Method2`. Эти связи показаны в следующем коде.  
  
```csharp  
class Program  
{  
    static void Main(string[] args)  
    {  
        BaseClass bc = new BaseClass();  
        DerivedClass dc = new DerivedClass();  
        BaseClass bcdc = new DerivedClass();  
  
        bc.Method1();  
        dc.Method1();  
        dc.Method2();  
        bcdc.Method1();  
    }  
    // Output:  
    // Base - Method1  
    // Base - Method1  
    // Derived - Method2  
    // Base - Method1  
}  
```  
  
 Далее добавьте следующий метод `Method2` в класс `BaseClass`. Сигнатура этого метода соответствует сигнатуре метода `Method2` в `DerivedClass`.  
  
```csharp  
public void Method2()  
{  
    Console.WriteLine("Base - Method2");  
}  
```  
  
 Поскольку `BaseClass` теперь имеет метод `Method2`, можно добавить второй оператор вызова для переменных `bc` и `bcdc` класса `BaseClass`, как показано в следующем коде.  
  
```csharp  
bc.Method1();  
bc.Method2();  
dc.Method1();  
dc.Method2();  
bcdc.Method1();  
bcdc.Method2();  
```  
  
 При построении проекта видно, что добавление метода `Method2` в `BaseClass` вызывает предупреждение. Предупреждение говорит, что метод `Method2` в `DerivedClass` скрывает метод `Method2` в `BaseClass`. Рекомендуется использовать ключевое слово `new` в определении `Method2`, если требуется получить такой результат. Другой вариант — переименовать один из методов `Method2` для разрешения предупреждения, но это не всегда целесообразно.  
  
 Прежде чем добавлять `new`, запустите программу, чтобы увидеть выходные данные дополнительных операторов вызова. Отобразятся следующие результаты.  
  
```csharp  
// Output:  
// Base - Method1  
// Base - Method2  
// Base - Method1  
// Derived - Method2  
// Base - Method1  
// Base - Method2  
```  
  
 Ключевое слово `new` сохраняет связи, дающие этот результат, однако подавляет предупреждение. Переменные, имеющие тип `BaseClass`, продолжают обращаться к элементам класса `BaseClass`, а переменная, имеющая тип `DerivedClass`, продолжает обращаться к элементам класса `DerivedClass` в первую очередь, а затем к элементам, унаследованным от `BaseClass`.  
  
 Чтобы подавить предупреждение, добавьте модификатор `new` в определение `Method2` в классе `DerivedClass`, как показано в следующем коде. Модификатор можно добавить перед или после `public`.  
  
```csharp  
public new void Method2()  
{  
    Console.WriteLine("Derived - Method2");  
}  
```  
  
 Запустите программу еще раз, чтобы убедиться, что выходные данные не изменились. Также убедитесь, что предупреждение больше не появляется. Используя ключевое слово `new`, вы утверждаете, что вам известно, что модифицируемый им член скрывается членом, который наследуется от базового класса. Дополнительные сведения о скрытии имен через наследование см. в разделе [Модификатор new](../../language-reference/keywords/new-modifier.md).  
  
 Чтобы противопоставить это поведение эффекту использования `override`, добавьте в `DerivedClass` следующий метод. Модификатор `override` можно добавить перед или после `public`.  
  
```csharp  
public override void Method1()  
{  
    Console.WriteLine("Derived - Method1");  
}  
```  
  
 Добавьте модификатор `virtual` в определение `Method1` в `BaseClass`. Модификатор `virtual` можно добавить перед или после `public`.  
  
```csharp  
public virtual void Method1()  
{  
    Console.WriteLine("Base - Method1");  
}  
```  
  
 Снова запустите проект. Обратите особое внимание на последние две строки следующих выходных данных.  
  
```csharp  
// Output:  
// Base - Method1  
// Base - Method2  
// Derived - Method1  
// Derived - Method2  
// Derived - Method1  
// Base - Method2  
```  
  
 Использование модификатора `override` позволяет `bcdc` осуществлять доступ к методу `Method1`, который определен в `DerivedClass`. Как правило, это требуемое поведение в иерархиях наследования. Требуется, чтобы объекты со значениями, созданными из производного класса, использовали определенные в производном классе методы. Это поведение достигается с использованием `override` для расширения метода базового класса.  
  
 Следующий код содержит полный пример.  
  
```csharp  
using System;  
using System.Text;  
  
namespace OverrideAndNew  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            BaseClass bc = new BaseClass();  
            DerivedClass dc = new DerivedClass();  
            BaseClass bcdc = new DerivedClass();  
  
            // The following two calls do what you would expect. They call  
            // the methods that are defined in BaseClass.  
            bc.Method1();  
            bc.Method2();  
            // Output:  
            // Base - Method1  
            // Base - Method2  
  
            // The following two calls do what you would expect. They call  
            // the methods that are defined in DerivedClass.  
            dc.Method1();  
            dc.Method2();  
            // Output:  
            // Derived - Method1  
            // Derived - Method2  
  
            // The following two calls produce different results, depending   
            // on whether override (Method1) or new (Method2) is used.  
            bcdc.Method1();  
            bcdc.Method2();  
            // Output:  
            // Derived - Method1  
            // Base - Method2  
        }  
    }  
  
    class BaseClass  
    {  
        public virtual void Method1()  
        {  
            Console.WriteLine("Base - Method1");  
        }  
  
        public virtual void Method2()  
        {  
            Console.WriteLine("Base - Method2");  
        }  
    }  
  
    class DerivedClass : BaseClass  
    {  
        public override void Method1()  
        {  
            Console.WriteLine("Derived - Method1");  
        }  
  
        public new void Method2()  
        {  
            Console.WriteLine("Derived - Method2");  
        }  
    }  
}  
```  
  
 В следующем примере показано подобное поведение в другом контексте. В примере определяются три класса: базовый класс `Car` и два класса, производных от него: `ConvertibleCar` и `Minivan`. Базовый класс содержит метод `DescribeCar`. Этот метод отображает общее описание автомобиля, а затем вызывает `ShowDetails` для предоставления дополнительных сведений. Каждый из трех классов определяет метод `ShowDetails`. Для определения метода `ShowDetails` в классе `ConvertibleCar` используется модификатор `new`. Для определения метода `ShowDetails` в классе `Minivan` используется модификатор `override`.  
  
```csharp  
// Define the base class, Car. The class defines two methods,  
// DescribeCar and ShowDetails. DescribeCar calls ShowDetails, and each derived  
// class also defines a ShowDetails method. The example tests which version of  
// ShowDetails is selected, the base class method or the derived class method.  
class Car  
{  
    public void DescribeCar()  
    {  
        System.Console.WriteLine("Four wheels and an engine.");  
        ShowDetails();  
    }  
  
    public virtual void ShowDetails()  
    {  
        System.Console.WriteLine("Standard transportation.");  
    }  
}  
  
// Define the derived classes.  
  
// Class ConvertibleCar uses the new modifier to acknowledge that ShowDetails  
// hides the base class method.  
class ConvertibleCar : Car  
{  
    public new void ShowDetails()  
    {  
        System.Console.WriteLine("A roof that opens up.");  
    }  
}  
  
// Class Minivan uses the override modifier to specify that ShowDetails  
// extends the base class method.  
class Minivan : Car  
{  
    public override void ShowDetails()  
    {  
        System.Console.WriteLine("Carries seven people.");  
    }  
}  
```  
  
 В примере проверяется версия вызванного `ShowDetails`. Следующий метод, `TestCars1`, объявляет экземпляр каждого класса, а затем вызывает `DescribeCar` на каждом экземпляре.  
  
```csharp  
public static void TestCars1()  
{  
    System.Console.WriteLine("\nTestCars1");  
    System.Console.WriteLine("----------");  
  
    Car car1 = new Car();  
    car1.DescribeCar();  
    System.Console.WriteLine("----------");  
  
    // Notice the output from this test case. The new modifier is  
    // used in the definition of ShowDetails in the ConvertibleCar  
    // class.    
  
    ConvertibleCar car2 = new ConvertibleCar();  
    car2.DescribeCar();  
    System.Console.WriteLine("----------");  
  
    Minivan car3 = new Minivan();  
    car3.DescribeCar();  
    System.Console.WriteLine("----------");  
}  
```  
  
 `TestCars1` формирует следующие выходные данные. Обратите особое внимание на результаты для `car2`, который, вероятно, не соответствует ожидаемым. Тип объекта — `ConvertibleCar`, но `DescribeCar` не получает доступа к версии `ShowDetails`, определенной в классе `ConvertibleCar`, так как этот метод объявлен с модификатором `new`, а не `override`. В результате объект `ConvertibleCar` отображает то же описание, что и объект `Car`. Сравните результаты для `car3`, который является объектом `Minivan`. В этом случае метод `ShowDetails`, объявленный в классе `Minivan`, переопределяет метод `ShowDetails`, объявленный в классе `Car`, и отображается описание микроавтобуса.  
  
```csharp  
// TestCars1  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Carries seven people.  
// ----------  
```  
  
 `TestCars2` создает список объектов, имеющих тип `Car`. Значения объектов создаются из классов`Car`, `ConvertibleCar` и `Minivan`. `DescribeCar` вызывается для каждого элемента списка. В следующем коде показано определение `TestCars2`.  
  
```csharp  
public static void TestCars2()  
{  
    System.Console.WriteLine("\nTestCars2");  
    System.Console.WriteLine("----------");  
  
    var cars = new List<Car> { new Car(), new ConvertibleCar(),   
        new Minivan() };  
  
    foreach (var car in cars)  
    {  
        car.DescribeCar();  
        System.Console.WriteLine("----------");  
    }  
}  
```  
  
 Выводится следующий результат. Обратите внимание, что он совпадает с выходными данными, отображаемыми `TestCars1`. Метод `ShowDetails` класса `ConvertibleCar` не вызывается, независимо от того, является ли тип объекта `ConvertibleCar`, как в `TestCars1`, или `Car`, как в `TestCars2`. И наоборот, `car3` вызывает метод `ShowDetails` класса `Minivan` в обоих случаях, независимо от того, какого они типа — `Minivan` или `Car`.  
  
```csharp  
// TestCars2  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Carries seven people.  
// ----------  
```  
  
 Методы `TestCars3` и `TestCars4` завершают пример. Эти методы вызывают `ShowDetails` напрямую: сначала из объектов, объявленных с типом `ConvertibleCar` и `Minivan` (`TestCars3`), а затем из объектов, объявленных с типом `Car` (`TestCars4`). Следующий код определяет эти два метода.  
  
```csharp  
public static void TestCars3()  
{  
    System.Console.WriteLine("\nTestCars3");  
    System.Console.WriteLine("----------");  
    ConvertibleCar car2 = new ConvertibleCar();  
    Minivan car3 = new Minivan();  
    car2.ShowDetails();  
    car3.ShowDetails();  
}  
  
public static void TestCars4()  
{  
    System.Console.WriteLine("\nTestCars4");  
    System.Console.WriteLine("----------");  
    Car car2 = new ConvertibleCar();  
    Car car3 = new Minivan();  
    car2.ShowDetails();  
    car3.ShowDetails();  
}  
```  
  
 Методы производят следующий результат, который соответствует результатам из первого примера в этой теме.  
  
```csharp  
// TestCars3  
// ----------  
// A roof that opens up.  
// Carries seven people.  
  
// TestCars4  
// ----------  
// Standard transportation.  
// Carries seven people.  
```  
  
 В следующем коде приведен полный проект и его результат.  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
namespace OverrideAndNew2  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Declare objects of the derived classes and test which version  
            // of ShowDetails is run, base or derived.  
            TestCars1();  
  
            // Declare objects of the base class, instantiated with the  
            // derived classes, and repeat the tests.  
            TestCars2();  
  
            // Declare objects of the derived classes and call ShowDetails  
            // directly.  
            TestCars3();  
  
            // Declare objects of the base class, instantiated with the  
            // derived classes, and repeat the tests.  
            TestCars4();  
        }  
  
        public static void TestCars1()  
        {  
            System.Console.WriteLine("\nTestCars1");  
            System.Console.WriteLine("----------");  
  
            Car car1 = new Car();  
            car1.DescribeCar();  
            System.Console.WriteLine("----------");  
  
            // Notice the output from this test case. The new modifier is  
            // used in the definition of ShowDetails in the ConvertibleCar  
            // class.    
            ConvertibleCar car2 = new ConvertibleCar();  
            car2.DescribeCar();  
            System.Console.WriteLine("----------");  
  
            Minivan car3 = new Minivan();  
            car3.DescribeCar();  
            System.Console.WriteLine("----------");  
        }  
        // Output:  
        // TestCars1  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Carries seven people.  
        // ----------  
  
        public static void TestCars2()  
        {  
            System.Console.WriteLine("\nTestCars2");  
            System.Console.WriteLine("----------");  
  
            var cars = new List<Car> { new Car(), new ConvertibleCar(),   
                new Minivan() };  
  
            foreach (var car in cars)  
            {  
                car.DescribeCar();  
                System.Console.WriteLine("----------");  
            }  
        }  
        // Output:  
        // TestCars2  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Carries seven people.  
        // ----------  
  
        public static void TestCars3()  
        {  
            System.Console.WriteLine("\nTestCars3");  
            System.Console.WriteLine("----------");  
            ConvertibleCar car2 = new ConvertibleCar();  
            Minivan car3 = new Minivan();  
            car2.ShowDetails();  
            car3.ShowDetails();  
        }  
        // Output:  
        // TestCars3  
        // ----------  
        // A roof that opens up.  
        // Carries seven people.  
  
        public static void TestCars4()  
        {  
            System.Console.WriteLine("\nTestCars4");  
            System.Console.WriteLine("----------");  
            Car car2 = new ConvertibleCar();  
            Car car3 = new Minivan();  
            car2.ShowDetails();  
            car3.ShowDetails();  
        }  
        // Output:  
        // TestCars4  
        // ----------  
        // Standard transportation.  
        // Carries seven people.  
    }  
  
    // Define the base class, Car. The class defines two virtual methods,  
    // DescribeCar and ShowDetails. DescribeCar calls ShowDetails, and each derived  
    // class also defines a ShowDetails method. The example tests which version of  
    // ShowDetails is used, the base class method or the derived class method.  
    class Car  
    {  
        public virtual void DescribeCar()  
        {  
            System.Console.WriteLine("Four wheels and an engine.");  
            ShowDetails();  
        }  
  
        public virtual void ShowDetails()  
        {  
            System.Console.WriteLine("Standard transportation.");  
        }  
    }  
  
    // Define the derived classes.  
  
    // Class ConvertibleCar uses the new modifier to acknowledge that ShowDetails  
    // hides the base class method.  
    class ConvertibleCar : Car  
    {  
        public new void ShowDetails()  
        {  
            System.Console.WriteLine("A roof that opens up.");  
        }  
    }  
  
    // Class Minivan uses the override modifier to specify that ShowDetails  
    // extends the base class method.  
    class Minivan : Car  
    {  
        public override void ShowDetails()  
        {  
            System.Console.WriteLine("Carries seven people.");  
        }  
    }  
  
}  
```  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Классы и структуры](./index.md)
- [Управление версиями с помощью ключевых слов Override и New](./versioning-with-the-override-and-new-keywords.md)
- [base](../../language-reference/keywords/base.md)
- [abstract](../../language-reference/keywords/abstract.md)
