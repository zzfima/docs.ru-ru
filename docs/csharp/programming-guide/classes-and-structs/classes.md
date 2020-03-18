---
title: Руководство по программированию на C#. Классы
description: Сведения о типах классов и их создании
ms.date: 08/21/2018
helpviewer_keywords:
- classes [C#]
- C# language, classes
ms.assetid: e8848524-7273-429f-8aba-c658d5eff5ad
ms.openlocfilehash: aadf555fb47963eab323bbb6105227c5b119e6f4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170316"
---
# <a name="classes-c-programming-guide"></a><span data-ttu-id="8efa8-103">Классы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="8efa8-103">Classes (C# Programming Guide)</span></span>

## <a name="reference-types"></a><span data-ttu-id="8efa8-104">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="8efa8-104">Reference types</span></span>  
<span data-ttu-id="8efa8-105">Тип, который определен как [класс](../../language-reference/keywords/class.md), является *ссылочным типом*.</span><span class="sxs-lookup"><span data-stu-id="8efa8-105">A type that is defined as a [class](../../language-reference/keywords/class.md) is a *reference type*.</span></span> <span data-ttu-id="8efa8-106">Когда во время выполнения вы объявляете переменную ссылочного типа, такая переменная будет содержать значение [NULL](../../language-reference/keywords/null.md), пока вы явным образом не создадите экземпляр класса с помощью оператора [new](../../language-reference/operators/new-operator.md) или не назначите его объекту совместимого типа, созданному в другом месте, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8efa8-106">At run time, when you declare a variable of a reference type, the variable contains the value [null](../../language-reference/keywords/null.md) until you explicitly create an instance of the class by using the [new](../../language-reference/operators/new-operator.md) operator, or assign it an object of a compatible type that may have been created elsewhere, as shown in the following example:</span></span>

```csharp
//Declaring an object of type MyClass.
MyClass mc = new MyClass();

//Declaring another object of the same type, assigning it the value of the first object.
MyClass mc2 = mc;
```

<span data-ttu-id="8efa8-107">При создании объекта выделяется достаточный объем памяти для этого объекта в управляемой куче, и переменная хранит только ссылку на расположение данного объекта.</span><span class="sxs-lookup"><span data-stu-id="8efa8-107">When the object is created, enough memory is allocated on the managed heap for that specific object, and the variable holds only a reference to the location of said object.</span></span> <span data-ttu-id="8efa8-108">Для типов в управляемой куче требуются временные затраты как при их выделении, так и удалении с помощью функции автоматического управления памятью в среде CLR, которая называется *сборкой мусора*.</span><span class="sxs-lookup"><span data-stu-id="8efa8-108">Types on the managed heap require overhead both when they are allocated and when they are reclaimed by the automatic memory management functionality of the CLR, which is known as *garbage collection*.</span></span> <span data-ttu-id="8efa8-109">Сборка мусора является хорошо оптимизированным процессом и в большинстве случаев не создает помех для производительности.</span><span class="sxs-lookup"><span data-stu-id="8efa8-109">However, garbage collection is also highly optimized and in most scenarios, it does not create a performance issue.</span></span> <span data-ttu-id="8efa8-110">Дополнительные сведения о сборке мусора см. в разделе [Автоматическое управление памятью и сборка мусора](../../../standard/garbage-collection/gc.md).</span><span class="sxs-lookup"><span data-stu-id="8efa8-110">For more information about garbage collection, see [Automatic memory management and garbage collection](../../../standard/garbage-collection/gc.md).</span></span>  
  
## <a name="declaring-classes"></a><span data-ttu-id="8efa8-111">Объявление классов</span><span class="sxs-lookup"><span data-stu-id="8efa8-111">Declaring Classes</span></span>

 <span data-ttu-id="8efa8-112">Классы объявляются с помощью ключевого слова [class](../../language-reference/keywords/class.md), за которым следует уникальный идентификатор, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8efa8-112">Classes are declared by using the [class](../../language-reference/keywords/class.md) keyword followed by a unique identifier, as shown in the following example:</span></span>

 ```csharp
//[access modifier] - [class] - [identifier]
 public class Customer
 {
    // Fields, properties, methods and events go here...
 }
```

 <span data-ttu-id="8efa8-113">Ключевому слову `class` предшествует уровень доступа.</span><span class="sxs-lookup"><span data-stu-id="8efa8-113">The `class` keyword is preceded by the access level.</span></span> <span data-ttu-id="8efa8-114">Так как в этом случае используется открытый класс ([public](../../language-reference/keywords/public.md)), любой пользователь может создавать его экземпляры.</span><span class="sxs-lookup"><span data-stu-id="8efa8-114">Because [public](../../language-reference/keywords/public.md) is used in this case, anyone can create instances of this class.</span></span> <span data-ttu-id="8efa8-115">За именем класса следует ключевое слово `class`.</span><span class="sxs-lookup"><span data-stu-id="8efa8-115">The name of the class follows the `class` keyword.</span></span> <span data-ttu-id="8efa8-116">Имя класса должно быть допустимым [именем идентификатора](../inside-a-program/identifier-names.md) C#.</span><span class="sxs-lookup"><span data-stu-id="8efa8-116">The name of the class must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span> <span data-ttu-id="8efa8-117">Оставшаяся часть определения — это тело класса, в котором задаются данные и поведение.</span><span class="sxs-lookup"><span data-stu-id="8efa8-117">The remainder of the definition is the class body, where the behavior and data are defined.</span></span> <span data-ttu-id="8efa8-118">Поля, свойства, методы и события в классе собирательно называются *членами класса*.</span><span class="sxs-lookup"><span data-stu-id="8efa8-118">Fields, properties, methods, and events on a class are collectively referred to as *class members*.</span></span>  
  
## <a name="creating-objects"></a><span data-ttu-id="8efa8-119">Создание объектов</span><span class="sxs-lookup"><span data-stu-id="8efa8-119">Creating objects</span></span>

<span data-ttu-id="8efa8-120">Несмотря на то, что они иногда взаимозаменяемы, класс и объект — разные вещи.</span><span class="sxs-lookup"><span data-stu-id="8efa8-120">Although they are sometimes used interchangeably, a class and an object are different things.</span></span> <span data-ttu-id="8efa8-121">Класс определяет тип объекта, но не является объектом.</span><span class="sxs-lookup"><span data-stu-id="8efa8-121">A class defines a type of object, but it is not an object itself.</span></span> <span data-ttu-id="8efa8-122">Объект — это конкретная сущность, основанная на классе, которую иногда называют экземпляром класса.</span><span class="sxs-lookup"><span data-stu-id="8efa8-122">An object is a concrete entity based on a class, and is sometimes referred to as an instance of a class.</span></span>  
  
 <span data-ttu-id="8efa8-123">Объекты можно создавать с помощью ключевого слова [new](../../language-reference/operators/new-operator.md), за которым следует имя класса, на котором будет основан объект, например следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8efa8-123">Objects can be created by using the [new](../../language-reference/operators/new-operator.md) keyword followed by the name of the class that the object will be based on, like this:</span></span>  

 ```csharp
 Customer object1 = new Customer();
 ```

 <span data-ttu-id="8efa8-124">При создании экземпляра класса ссылка на объект передается программисту.</span><span class="sxs-lookup"><span data-stu-id="8efa8-124">When an instance of a class is created, a reference to the object is passed back to the programmer.</span></span> <span data-ttu-id="8efa8-125">В предыдущем примере `object1` представляет собой ссылку на объект, который основан на `Customer`.</span><span class="sxs-lookup"><span data-stu-id="8efa8-125">In the previous example, `object1` is a reference to an object that is based on `Customer`.</span></span> <span data-ttu-id="8efa8-126">Эта ссылка указывает на новый объект, но не содержит данные этого объекта.</span><span class="sxs-lookup"><span data-stu-id="8efa8-126">This reference refers to the new object but does not contain the object data itself.</span></span> <span data-ttu-id="8efa8-127">Фактически, можно создать ссылку на объект без создания собственно объекта:</span><span class="sxs-lookup"><span data-stu-id="8efa8-127">In fact, you can create an object reference without creating an object at all:</span></span>  

```csharp
 Customer object2;
```

 <span data-ttu-id="8efa8-128">Создание таких ссылок, которые не указывают на объект, не рекомендуется, так как попытка доступа к объекту по такой ссылке приведет к сбою во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="8efa8-128">We don't recommend creating object references such as this one that don't refer to an object because trying to access an object through such a reference will fail at run time.</span></span> <span data-ttu-id="8efa8-129">Однако такую ссылку можно сделать указывающей на объект, создав новый объект или назначив ее существующему объекту, как показано далее:</span><span class="sxs-lookup"><span data-stu-id="8efa8-129">However, such a reference can be made to refer to an object, either by creating a new object, or by assigning it to an existing object, such as this:</span></span>  

 ```csharp
 Customer object3 = new Customer();
 Customer object4 = object3;
```
  
 <span data-ttu-id="8efa8-130">В этом коде создаются две ссылки на объект, которые указывают на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="8efa8-130">This code creates two object references that both refer to the same object.</span></span> <span data-ttu-id="8efa8-131">Таким образом, любые изменения объекта, выполненные посредством `object3`, отражаются при последующем использовании `object4`.</span><span class="sxs-lookup"><span data-stu-id="8efa8-131">Therefore, any changes to the object made through `object3` are reflected in subsequent uses of `object4`.</span></span> <span data-ttu-id="8efa8-132">Поскольку на объекты, основанные на классах, указывают ссылки, классы называют ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="8efa8-132">Because objects that are based on classes are referred to by reference, classes are known as reference types.</span></span>  
  
## <a name="class-inheritance"></a><span data-ttu-id="8efa8-133">Наследование классов</span><span class="sxs-lookup"><span data-stu-id="8efa8-133">Class inheritance</span></span>  

<span data-ttu-id="8efa8-134">Классы полностью поддерживают *наследование*, фундаментальный механизм объектно ориентированного программирования.</span><span class="sxs-lookup"><span data-stu-id="8efa8-134">Classes fully support *inheritance*, a fundamental characteristic of object-oriented programming.</span></span> <span data-ttu-id="8efa8-135">Создаваемый класс может наследовать от любого другого интерфейса или класса, который не определен как [запечатанный](../../language-reference/keywords/sealed.md), а другие классы могут наследовать от этого класса и переопределять его виртуальные методы.</span><span class="sxs-lookup"><span data-stu-id="8efa8-135">When you create a class, you can inherit from any other interface or class that is not defined as [sealed](../../language-reference/keywords/sealed.md), and other classes can inherit from your class and override class virtual methods.</span></span>

<span data-ttu-id="8efa8-136">При наследовании создается *производный* класс, то есть класс объявляется с помощью *базового класса*, от которого он наследует данные и поведение.</span><span class="sxs-lookup"><span data-stu-id="8efa8-136">Inheritance is accomplished by using a *derivation*, which means a class is declared by using a *base class* from which it inherits data and behavior.</span></span> <span data-ttu-id="8efa8-137">Базовый класс задается добавлением после имени производного класса двоеточия и имени базового класса, как показано далее:</span><span class="sxs-lookup"><span data-stu-id="8efa8-137">A base class is specified by appending a colon and the name of the base class following the derived class name, like this:</span></span>  

 ```csharp
 public class Manager : Employee
 {
     // Employee fields, properties, methods and events are inherited
     // New Manager fields, properties, methods and events go here...
 }
 ```

<span data-ttu-id="8efa8-138">Когда класс объявляет базовый класс, он наследует все члены базового класса, за исключением конструкторов.</span><span class="sxs-lookup"><span data-stu-id="8efa8-138">When a class declares a base class, it inherits all the members of the base class except the constructors.</span></span> <span data-ttu-id="8efa8-139">Дополнительные сведения см. в разделе [Наследование](inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="8efa8-139">For more information, see [Inheritance](inheritance.md).</span></span>
  
<span data-ttu-id="8efa8-140">В отличие от C++, класс в C# может только напрямую наследовать от одного базового класса.</span><span class="sxs-lookup"><span data-stu-id="8efa8-140">Unlike C++, a class in C# can only directly inherit from one base class.</span></span> <span data-ttu-id="8efa8-141">Тем не менее, поскольку базовый класс может сам наследовать от другого класса, класс может косвенно наследовать от нескольких базовых классов.</span><span class="sxs-lookup"><span data-stu-id="8efa8-141">However, because a base class may itself inherit from another class, a class may indirectly inherit multiple base classes.</span></span> <span data-ttu-id="8efa8-142">Кроме того, класс может напрямую реализовать несколько интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="8efa8-142">Furthermore, a class can directly implement more than one interface.</span></span> <span data-ttu-id="8efa8-143">Дополнительные сведения см. в статье [Интерфейсы](../interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="8efa8-143">For more information, see [Interfaces](../interfaces/index.md).</span></span>  
  
<span data-ttu-id="8efa8-144">Класс может быть объявлен [абстрактным](../../language-reference/keywords/abstract.md).</span><span class="sxs-lookup"><span data-stu-id="8efa8-144">A class can be declared [abstract](../../language-reference/keywords/abstract.md).</span></span> <span data-ttu-id="8efa8-145">Абстрактный класс содержит абстрактные методы, которые имеют определение сигнатуры, но не имеют реализации.</span><span class="sxs-lookup"><span data-stu-id="8efa8-145">An abstract class contains abstract methods that have a signature definition but no implementation.</span></span> <span data-ttu-id="8efa8-146">Нельзя создавать экземпляры абстрактных классов.</span><span class="sxs-lookup"><span data-stu-id="8efa8-146">Abstract classes cannot be instantiated.</span></span> <span data-ttu-id="8efa8-147">Они могут использоваться только через производные классы, реализующие абстрактные методы.</span><span class="sxs-lookup"><span data-stu-id="8efa8-147">They can only be used through derived classes that implement the abstract methods.</span></span> <span data-ttu-id="8efa8-148">И наоборот, [запечатанный](../../language-reference/keywords/sealed.md) класс не позволяет другим классам быть от него производными.</span><span class="sxs-lookup"><span data-stu-id="8efa8-148">By contrast, a [sealed](../../language-reference/keywords/sealed.md) class does not allow other classes to derive from it.</span></span> <span data-ttu-id="8efa8-149">Дополнительные сведения см. в статье [Абстрактные и запечатанные классы и члены классов](abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="8efa8-149">For more information, see [Abstract and Sealed Classes and Class Members](abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
<span data-ttu-id="8efa8-150">Определения классов можно разделить между различными исходными файлами.</span><span class="sxs-lookup"><span data-stu-id="8efa8-150">Class definitions can be split between different source files.</span></span> <span data-ttu-id="8efa8-151">Дополнительные сведения см. в статье [Разделяемые классы и методы](partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="8efa8-151">For more information, see [Partial Classes and Methods](partial-classes-and-methods.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8efa8-152">Пример</span><span class="sxs-lookup"><span data-stu-id="8efa8-152">Example</span></span>

<span data-ttu-id="8efa8-153">В следующем примере определяется открытый класс, содержащий [автоматически реализуемое свойство](auto-implemented-properties.md), метод и специальный метод, который называется конструктором.</span><span class="sxs-lookup"><span data-stu-id="8efa8-153">The following example defines a public class that contains an [auto-implemented property](auto-implemented-properties.md), a method, and a special method called a constructor.</span></span> <span data-ttu-id="8efa8-154">См. дополнительные сведения о [свойствах](properties.md), [методах](methods.md) и [конструкторах](constructors.md).</span><span class="sxs-lookup"><span data-stu-id="8efa8-154">For more information, see [Properties](properties.md), [Methods](methods.md), and [Constructors](constructors.md) topics.</span></span> <span data-ttu-id="8efa8-155">Затем создаются экземпляры этого класса с помощью ключевого слова `new`.</span><span class="sxs-lookup"><span data-stu-id="8efa8-155">The instances of the class are then instantiated with the `new` keyword.</span></span>  
  
[!code-csharp[Class Example](~/samples/snippets/csharp/programming-guide/classes-and-structs/class-example.cs)]
  
## <a name="c-language-specification"></a><span data-ttu-id="8efa8-156">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="8efa8-156">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8efa8-157">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8efa8-157">See also</span></span>

- [<span data-ttu-id="8efa8-158">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8efa8-158">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8efa8-159">Объектно-ориентированное программирование</span><span class="sxs-lookup"><span data-stu-id="8efa8-159">Object-Oriented Programming</span></span>](../concepts/object-oriented-programming.md)
- [<span data-ttu-id="8efa8-160">Полиморфизм</span><span class="sxs-lookup"><span data-stu-id="8efa8-160">Polymorphism</span></span>](polymorphism.md)
- [<span data-ttu-id="8efa8-161">Имена идентификаторов</span><span class="sxs-lookup"><span data-stu-id="8efa8-161">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="8efa8-162">Участники</span><span class="sxs-lookup"><span data-stu-id="8efa8-162">Members</span></span>](members.md)
- [<span data-ttu-id="8efa8-163">Методы</span><span class="sxs-lookup"><span data-stu-id="8efa8-163">Methods</span></span>](methods.md)
- [<span data-ttu-id="8efa8-164">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="8efa8-164">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="8efa8-165">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="8efa8-165">Finalizers</span></span>](destructors.md)
- [<span data-ttu-id="8efa8-166">Объекты</span><span class="sxs-lookup"><span data-stu-id="8efa8-166">Objects</span></span>](objects.md)
