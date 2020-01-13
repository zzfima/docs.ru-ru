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
# <a name="knowing-when-to-use-override-and-new-keywords-c-programming-guide"></a><span data-ttu-id="4d3d3-102">Использование ключевых слов "Override" и "New" (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="4d3d3-102">Knowing When to Use Override and New Keywords (C# Programming Guide)</span></span>

<span data-ttu-id="4d3d3-103">В C# метод в производном классе может иметь то же имя, что и метод в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-103">In C#, a method in a derived class can have the same name as a method in the base class.</span></span> <span data-ttu-id="4d3d3-104">Можно задать способ взаимодействия методов, воспользовавшись ключевыми словами [new](../../language-reference/keywords/new-modifier.md) и [override](../../language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="4d3d3-104">You can specify how the methods interact by using the [new](../../language-reference/keywords/new-modifier.md) and [override](../../language-reference/keywords/override.md) keywords.</span></span> <span data-ttu-id="4d3d3-105">Модификатор `override`*расширяет* метод `virtual` базового класса, а модификатор `new`*скрывает* доступный метод базового класса.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-105">The `override` modifier *extends* the base class `virtual` method, and the `new` modifier *hides* an accessible base class method.</span></span> <span data-ttu-id="4d3d3-106">Эта разница показана в примере в этой статье.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-106">The difference is illustrated in the examples in this topic.</span></span>  
  
 <span data-ttu-id="4d3d3-107">В консольном приложении объявите два класса — `BaseClass` и `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-107">In a console application, declare the following two classes, `BaseClass` and `DerivedClass`.</span></span> <span data-ttu-id="4d3d3-108">Тип`DerivedClass` наследуется от типа `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-108">`DerivedClass` inherits from `BaseClass`.</span></span>  
  
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
  
 <span data-ttu-id="4d3d3-109">В методе `Main` объявите переменные `bc`, `dc` и `bcdc`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-109">In the `Main` method, declare variables `bc`, `dc`, and `bcdc`.</span></span>  
  
- <span data-ttu-id="4d3d3-110">Параметр `bc` имеет тип `BaseClass` и его значение — тип `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-110">`bc` is of type `BaseClass`, and its value is of type `BaseClass`.</span></span>  
  
- <span data-ttu-id="4d3d3-111">Параметр `dc` имеет тип `DerivedClass` и его значение — тип `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-111">`dc` is of type `DerivedClass`, and its value is of type `DerivedClass`.</span></span>  
  
- <span data-ttu-id="4d3d3-112">Параметр `bcdc` имеет тип `BaseClass` и его значение — тип `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-112">`bcdc` is of type `BaseClass`, and its value is of type `DerivedClass`.</span></span> <span data-ttu-id="4d3d3-113">Это переменная, на которую следует обратить внимание.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-113">This is the variable to pay attention to.</span></span>  
  
 <span data-ttu-id="4d3d3-114">Поскольку `bc` и `bcdc` имеют тип `BaseClass`, они могут только напрямую обращаться к методу `Method1` (если не используется приведение).</span><span class="sxs-lookup"><span data-stu-id="4d3d3-114">Because `bc` and `bcdc` have type `BaseClass`, they can only directly access `Method1`, unless you use casting.</span></span> <span data-ttu-id="4d3d3-115">Переменная `dc` может обращаться к `Method1` и `Method2`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-115">Variable `dc` can access both `Method1` and `Method2`.</span></span> <span data-ttu-id="4d3d3-116">Эти связи показаны в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-116">These relationships are shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="4d3d3-117">Далее добавьте следующий метод `Method2` в класс `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-117">Next, add the following `Method2` method to `BaseClass`.</span></span> <span data-ttu-id="4d3d3-118">Сигнатура этого метода соответствует сигнатуре метода `Method2` в `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-118">The signature of this method matches the signature of the `Method2` method in `DerivedClass`.</span></span>  
  
```csharp  
public void Method2()  
{  
    Console.WriteLine("Base - Method2");  
}  
```  
  
 <span data-ttu-id="4d3d3-119">Поскольку `BaseClass` теперь имеет метод `Method2`, можно добавить второй оператор вызова для переменных `bc` и `bcdc` класса `BaseClass`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-119">Because `BaseClass` now has a `Method2` method, a second calling statement can be added for `BaseClass` variables `bc` and `bcdc`, as shown in the following code.</span></span>  
  
```csharp  
bc.Method1();  
bc.Method2();  
dc.Method1();  
dc.Method2();  
bcdc.Method1();  
bcdc.Method2();  
```  
  
 <span data-ttu-id="4d3d3-120">При построении проекта видно, что добавление метода `Method2` в `BaseClass` вызывает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-120">When you build the project, you see that the addition of the `Method2` method in `BaseClass` causes a warning.</span></span> <span data-ttu-id="4d3d3-121">Предупреждение говорит, что метод `Method2` в `DerivedClass` скрывает метод `Method2` в `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-121">The warning says that the `Method2` method in `DerivedClass` hides the `Method2` method in `BaseClass`.</span></span> <span data-ttu-id="4d3d3-122">Рекомендуется использовать ключевое слово `new` в определении `Method2`, если требуется получить такой результат.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-122">You are advised to use the `new` keyword in the `Method2` definition if you intend to cause that result.</span></span> <span data-ttu-id="4d3d3-123">Другой вариант — переименовать один из методов `Method2` для разрешения предупреждения, но это не всегда целесообразно.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-123">Alternatively, you could rename one of the `Method2` methods to resolve the warning, but that is not always practical.</span></span>  
  
 <span data-ttu-id="4d3d3-124">Прежде чем добавлять `new`, запустите программу, чтобы увидеть выходные данные дополнительных операторов вызова.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-124">Before adding `new`, run the program to see the output produced by the additional calling statements.</span></span> <span data-ttu-id="4d3d3-125">Отобразятся следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-125">The following results are displayed.</span></span>  
  
```csharp  
// Output:  
// Base - Method1  
// Base - Method2  
// Base - Method1  
// Derived - Method2  
// Base - Method1  
// Base - Method2  
```  
  
 <span data-ttu-id="4d3d3-126">Ключевое слово `new` сохраняет связи, дающие этот результат, однако подавляет предупреждение.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-126">The `new` keyword preserves the relationships that produce that output, but it suppresses the warning.</span></span> <span data-ttu-id="4d3d3-127">Переменные, имеющие тип `BaseClass`, продолжают обращаться к элементам класса `BaseClass`, а переменная, имеющая тип `DerivedClass`, продолжает обращаться к элементам класса `DerivedClass` в первую очередь, а затем к элементам, унаследованным от `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-127">The variables that have type `BaseClass` continue to access the members of `BaseClass`, and the variable that has type `DerivedClass` continues to access members in `DerivedClass` first, and then to consider members inherited from `BaseClass`.</span></span>  
  
 <span data-ttu-id="4d3d3-128">Чтобы подавить предупреждение, добавьте модификатор `new` в определение `Method2` в классе `DerivedClass`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-128">To suppress the warning, add the `new` modifier to the definition of `Method2` in `DerivedClass`, as shown in the following code.</span></span> <span data-ttu-id="4d3d3-129">Модификатор можно добавить перед или после `public`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-129">The modifier can be added before or after `public`.</span></span>  
  
```csharp  
public new void Method2()  
{  
    Console.WriteLine("Derived - Method2");  
}  
```  
  
 <span data-ttu-id="4d3d3-130">Запустите программу еще раз, чтобы убедиться, что выходные данные не изменились.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-130">Run the program again to verify that the output has not changed.</span></span> <span data-ttu-id="4d3d3-131">Также убедитесь, что предупреждение больше не появляется.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-131">Also verify that the warning no longer appears.</span></span> <span data-ttu-id="4d3d3-132">Используя ключевое слово `new`, вы утверждаете, что вам известно, что модифицируемый им член скрывается членом, который наследуется от базового класса.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-132">By using `new`, you are asserting that you are aware that the member that it modifies hides a member that is inherited from the base class.</span></span> <span data-ttu-id="4d3d3-133">Дополнительные сведения о скрытии имен через наследование см. в разделе [Модификатор new](../../language-reference/keywords/new-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="4d3d3-133">For more information about name hiding through inheritance, see [new Modifier](../../language-reference/keywords/new-modifier.md).</span></span>  
  
 <span data-ttu-id="4d3d3-134">Чтобы противопоставить это поведение эффекту использования `override`, добавьте в `DerivedClass` следующий метод.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-134">To contrast this behavior to the effects of using `override`, add the following method to `DerivedClass`.</span></span> <span data-ttu-id="4d3d3-135">Модификатор `override` можно добавить перед или после `public`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-135">The `override` modifier can be added before or after `public`.</span></span>  
  
```csharp  
public override void Method1()  
{  
    Console.WriteLine("Derived - Method1");  
}  
```  
  
 <span data-ttu-id="4d3d3-136">Добавьте модификатор `virtual` в определение `Method1` в `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-136">Add the `virtual` modifier to the definition of `Method1` in `BaseClass`.</span></span> <span data-ttu-id="4d3d3-137">Модификатор `virtual` можно добавить перед или после `public`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-137">The `virtual` modifier can be added before or after `public`.</span></span>  
  
```csharp  
public virtual void Method1()  
{  
    Console.WriteLine("Base - Method1");  
}  
```  
  
 <span data-ttu-id="4d3d3-138">Снова запустите проект.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-138">Run the project again.</span></span> <span data-ttu-id="4d3d3-139">Обратите особое внимание на последние две строки следующих выходных данных.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-139">Notice especially the last two lines of the following output.</span></span>  
  
```csharp  
// Output:  
// Base - Method1  
// Base - Method2  
// Derived - Method1  
// Derived - Method2  
// Derived - Method1  
// Base - Method2  
```  
  
 <span data-ttu-id="4d3d3-140">Использование модификатора `override` позволяет `bcdc` осуществлять доступ к методу `Method1`, который определен в `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-140">The use of the `override` modifier enables `bcdc` to access the `Method1` method that is defined in `DerivedClass`.</span></span> <span data-ttu-id="4d3d3-141">Как правило, это требуемое поведение в иерархиях наследования.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-141">Typically, that is the desired behavior in inheritance hierarchies.</span></span> <span data-ttu-id="4d3d3-142">Требуется, чтобы объекты со значениями, созданными из производного класса, использовали определенные в производном классе методы.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-142">You want objects that have values that are created from the derived class to use the methods that are defined in the derived class.</span></span> <span data-ttu-id="4d3d3-143">Это поведение достигается с использованием `override` для расширения метода базового класса.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-143">You achieve that behavior by using `override` to extend the base class method.</span></span>  
  
 <span data-ttu-id="4d3d3-144">Следующий код содержит полный пример.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-144">The following code contains the full example.</span></span>  
  
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
  
 <span data-ttu-id="4d3d3-145">В следующем примере показано подобное поведение в другом контексте.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-145">The following example illustrates similar behavior in a different context.</span></span> <span data-ttu-id="4d3d3-146">В примере определяются три класса: базовый класс `Car` и два класса, производных от него: `ConvertibleCar` и `Minivan`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-146">The example defines three classes: a base class named `Car` and two classes that are derived from it, `ConvertibleCar` and `Minivan`.</span></span> <span data-ttu-id="4d3d3-147">Базовый класс содержит метод `DescribeCar`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-147">The base class contains a `DescribeCar` method.</span></span> <span data-ttu-id="4d3d3-148">Этот метод отображает общее описание автомобиля, а затем вызывает `ShowDetails` для предоставления дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-148">The method displays a basic description of a car, and then calls `ShowDetails` to provide additional information.</span></span> <span data-ttu-id="4d3d3-149">Каждый из трех классов определяет метод `ShowDetails`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-149">Each of the three classes defines a `ShowDetails` method.</span></span> <span data-ttu-id="4d3d3-150">Для определения метода `ShowDetails` в классе `ConvertibleCar` используется модификатор `new`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-150">The `new` modifier is used to define `ShowDetails` in the `ConvertibleCar` class.</span></span> <span data-ttu-id="4d3d3-151">Для определения метода `ShowDetails` в классе `Minivan` используется модификатор `override`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-151">The `override` modifier is used to define `ShowDetails` in the `Minivan` class.</span></span>  
  
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
  
 <span data-ttu-id="4d3d3-152">В примере проверяется версия вызванного `ShowDetails`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-152">The example tests which version of `ShowDetails` is called.</span></span> <span data-ttu-id="4d3d3-153">Следующий метод, `TestCars1`, объявляет экземпляр каждого класса, а затем вызывает `DescribeCar` на каждом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-153">The following method, `TestCars1`, declares an instance of each class, and then calls `DescribeCar` on each instance.</span></span>  
  
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
  
 <span data-ttu-id="4d3d3-154">`TestCars1` формирует следующие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-154">`TestCars1` produces the following output.</span></span> <span data-ttu-id="4d3d3-155">Обратите особое внимание на результаты для `car2`, который, вероятно, не соответствует ожидаемым.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-155">Notice especially the results for `car2`, which probably are not what you expected.</span></span> <span data-ttu-id="4d3d3-156">Тип объекта — `ConvertibleCar`, но `DescribeCar` не получает доступа к версии `ShowDetails`, определенной в классе `ConvertibleCar`, так как этот метод объявлен с модификатором `new`, а не `override`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-156">The type of the object is `ConvertibleCar`, but `DescribeCar` does not access the version of `ShowDetails` that is defined in the `ConvertibleCar` class because that method is declared with the `new` modifier, not the `override` modifier.</span></span> <span data-ttu-id="4d3d3-157">В результате объект `ConvertibleCar` отображает то же описание, что и объект `Car`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-157">As a result, a `ConvertibleCar` object displays the same description as a `Car` object.</span></span> <span data-ttu-id="4d3d3-158">Сравните результаты для `car3`, который является объектом `Minivan`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-158">Contrast the results for `car3`, which is a `Minivan` object.</span></span> <span data-ttu-id="4d3d3-159">В этом случае метод `ShowDetails`, объявленный в классе `Minivan`, переопределяет метод `ShowDetails`, объявленный в классе `Car`, и отображается описание микроавтобуса.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-159">In this case, the `ShowDetails` method that is declared in the `Minivan` class overrides the `ShowDetails` method that is declared in the `Car` class, and the description that is displayed describes a minivan.</span></span>  
  
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
  
 <span data-ttu-id="4d3d3-160">`TestCars2` создает список объектов, имеющих тип `Car`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-160">`TestCars2` creates a list of objects that have type `Car`.</span></span> <span data-ttu-id="4d3d3-161">Значения объектов создаются из классов`Car`, `ConvertibleCar` и `Minivan`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-161">The values of the objects are instantiated from the `Car`, `ConvertibleCar`, and `Minivan` classes.</span></span> <span data-ttu-id="4d3d3-162">`DescribeCar` вызывается для каждого элемента списка.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-162">`DescribeCar` is called on each element of the list.</span></span> <span data-ttu-id="4d3d3-163">В следующем коде показано определение `TestCars2`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-163">The following code shows the definition of `TestCars2`.</span></span>  
  
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
  
 <span data-ttu-id="4d3d3-164">Выводится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-164">The following output is displayed.</span></span> <span data-ttu-id="4d3d3-165">Обратите внимание, что он совпадает с выходными данными, отображаемыми `TestCars1`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-165">Notice that it is the same as the output that is displayed by `TestCars1`.</span></span> <span data-ttu-id="4d3d3-166">Метод `ShowDetails` класса `ConvertibleCar` не вызывается, независимо от того, является ли тип объекта `ConvertibleCar`, как в `TestCars1`, или `Car`, как в `TestCars2`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-166">The `ShowDetails` method of the `ConvertibleCar` class is not called, regardless of whether the type of the object is `ConvertibleCar`, as in `TestCars1`, or `Car`, as in `TestCars2`.</span></span> <span data-ttu-id="4d3d3-167">И наоборот, `car3` вызывает метод `ShowDetails` класса `Minivan` в обоих случаях, независимо от того, какого они типа — `Minivan` или `Car`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-167">Conversely, `car3` calls the `ShowDetails` method from the `Minivan` class in both cases, whether it has type `Minivan` or type `Car`.</span></span>  
  
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
  
 <span data-ttu-id="4d3d3-168">Методы `TestCars3` и `TestCars4` завершают пример.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-168">Methods `TestCars3` and `TestCars4` complete the example.</span></span> <span data-ttu-id="4d3d3-169">Эти методы вызывают `ShowDetails` напрямую: сначала из объектов, объявленных с типом `ConvertibleCar` и `Minivan` (`TestCars3`), а затем из объектов, объявленных с типом `Car` (`TestCars4`).</span><span class="sxs-lookup"><span data-stu-id="4d3d3-169">These methods call `ShowDetails` directly, first from objects declared to have type `ConvertibleCar` and `Minivan` (`TestCars3`), then from objects declared to have type `Car` (`TestCars4`).</span></span> <span data-ttu-id="4d3d3-170">Следующий код определяет эти два метода.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-170">The following code defines these two methods.</span></span>  
  
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
  
 <span data-ttu-id="4d3d3-171">Методы производят следующий результат, который соответствует результатам из первого примера в этой теме.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-171">The methods produce the following output, which corresponds to the results from the first example in this topic.</span></span>  
  
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
  
 <span data-ttu-id="4d3d3-172">В следующем коде приведен полный проект и его результат.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-172">The following code shows the complete project and its output.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4d3d3-173">См. также</span><span class="sxs-lookup"><span data-stu-id="4d3d3-173">See also</span></span>

- [<span data-ttu-id="4d3d3-174">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4d3d3-174">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4d3d3-175">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="4d3d3-175">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="4d3d3-176">Управление версиями с помощью ключевых слов Override и New</span><span class="sxs-lookup"><span data-stu-id="4d3d3-176">Versioning with the Override and New Keywords</span></span>](./versioning-with-the-override-and-new-keywords.md)
- [<span data-ttu-id="4d3d3-177">base</span><span class="sxs-lookup"><span data-stu-id="4d3d3-177">base</span></span>](../../language-reference/keywords/base.md)
- [<span data-ttu-id="4d3d3-178">abstract</span><span class="sxs-lookup"><span data-stu-id="4d3d3-178">abstract</span></span>](../../language-reference/keywords/abstract.md)
