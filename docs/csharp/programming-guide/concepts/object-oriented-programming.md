---
title: Объектно ориентированное программирование (C#)
ms.date: 07/20/2015
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: 8bf02cbfca30d6dfc29c4e5e6c30a5013931e71b
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2019
ms.locfileid: "67398068"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="a9d51-102">Объектно ориентированное программирование (C#)</span><span class="sxs-lookup"><span data-stu-id="a9d51-102">Object-Oriented Programming (C#)</span></span>

<span data-ttu-id="a9d51-103">C# обеспечивает полную поддержку объектно ориентированного программирования, включая инкапсуляцию, наследование и полиморфизм.</span><span class="sxs-lookup"><span data-stu-id="a9d51-103">C# provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

<span data-ttu-id="a9d51-104">*Инкапсуляция* означает, что группа связанных свойств, методов и других членов рассматривается как единый элемент или объект.</span><span class="sxs-lookup"><span data-stu-id="a9d51-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>

<span data-ttu-id="a9d51-105">*Наследование* описывает возможность создания новых классов на основе существующих классов.</span><span class="sxs-lookup"><span data-stu-id="a9d51-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>

<span data-ttu-id="a9d51-106">*Полиморфизм* означает, что можно иметь несколько взаимозаменяемых классов, даже если каждый класс реализует одни и те же свойства или методы разными способами.</span><span class="sxs-lookup"><span data-stu-id="a9d51-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

<span data-ttu-id="a9d51-107">В этом разделе рассматриваются следующие понятия.</span><span class="sxs-lookup"><span data-stu-id="a9d51-107">This section describes the following concepts:</span></span>

- [<span data-ttu-id="a9d51-108">Классы и объекты</span><span class="sxs-lookup"><span data-stu-id="a9d51-108">Classes and Objects</span></span>](#Classes)

  - [<span data-ttu-id="a9d51-109">Члены класса</span><span class="sxs-lookup"><span data-stu-id="a9d51-109">Class Members</span></span>](#Members)

    - [<span data-ttu-id="a9d51-110">Свойства и поля</span><span class="sxs-lookup"><span data-stu-id="a9d51-110">Properties and Fields</span></span>](#Properties)

    - [<span data-ttu-id="a9d51-111">Методы</span><span class="sxs-lookup"><span data-stu-id="a9d51-111">Methods</span></span>](#Methods)

    - [<span data-ttu-id="a9d51-112">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="a9d51-112">Constructors</span></span>](#Constructors)

    - [<span data-ttu-id="a9d51-113">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="a9d51-113">Finalizers</span></span>](#Finalizers)

    - [<span data-ttu-id="a9d51-114">События</span><span class="sxs-lookup"><span data-stu-id="a9d51-114">Events</span></span>](#Events)

    - [<span data-ttu-id="a9d51-115">Вложенные классы</span><span class="sxs-lookup"><span data-stu-id="a9d51-115">Nested Classes</span></span>](#NestedClasses)

  - [<span data-ttu-id="a9d51-116">Модификаторы доступа и уровни доступа</span><span class="sxs-lookup"><span data-stu-id="a9d51-116">Access Modifiers and Access Levels</span></span>](#AccessModifiers)

  - [<span data-ttu-id="a9d51-117">Создание экземпляров классов</span><span class="sxs-lookup"><span data-stu-id="a9d51-117">Instantiating Classes</span></span>](#InstantiatingClasses)

  - [<span data-ttu-id="a9d51-118">Статические классы и их члены</span><span class="sxs-lookup"><span data-stu-id="a9d51-118">Static Classes and Members</span></span>](#Static)

  - [<span data-ttu-id="a9d51-119">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="a9d51-119">Anonymous Types</span></span>](#AnonymousTypes)

- [<span data-ttu-id="a9d51-120">Наследование</span><span class="sxs-lookup"><span data-stu-id="a9d51-120">Inheritance</span></span>](#Inheritance)

  - [<span data-ttu-id="a9d51-121">Переопределение членов</span><span class="sxs-lookup"><span data-stu-id="a9d51-121">Overriding Members</span></span>](#Overriding)

- [<span data-ttu-id="a9d51-122">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="a9d51-122">Interfaces</span></span>](#Interfaces)

- [<span data-ttu-id="a9d51-123">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="a9d51-123">Generics</span></span>](#Generics)

- [<span data-ttu-id="a9d51-124">Делегаты</span><span class="sxs-lookup"><span data-stu-id="a9d51-124">Delegates</span></span>](#Delegates)

## <a name="Classes"></a> <span data-ttu-id="a9d51-125">Классы и объекты</span><span class="sxs-lookup"><span data-stu-id="a9d51-125">Classes and Objects</span></span>

<span data-ttu-id="a9d51-126">Термины *класс* и *объект* часто взаимозаменяемы, но в действительности классы описывают *типы* объектов, а объекты — это используемые *экземпляры* классов.</span><span class="sxs-lookup"><span data-stu-id="a9d51-126">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="a9d51-127">Поэтому процесс создания объекта называется *созданием экземпляра*.</span><span class="sxs-lookup"><span data-stu-id="a9d51-127">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="a9d51-128">Если использовать сравнение с чертежом, то класс является чертежом, а объект является зданием, построенным по нему.</span><span class="sxs-lookup"><span data-stu-id="a9d51-128">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="a9d51-129">Определение класса:</span><span class="sxs-lookup"><span data-stu-id="a9d51-129">To define a class:</span></span>

```csharp
class SampleClass
{
}
```

<span data-ttu-id="a9d51-130">C# также предоставляет облегченную версию классов — *структуры*, которые используются, когда необходимо создать большой массив объектов, использующий небольшой объем памяти.</span><span class="sxs-lookup"><span data-stu-id="a9d51-130">C# also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>

<span data-ttu-id="a9d51-131">Определение структуры:</span><span class="sxs-lookup"><span data-stu-id="a9d51-131">To define a structure:</span></span>

```csharp
struct SampleStruct
{
}
```

<span data-ttu-id="a9d51-132">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="a9d51-132">For more information, see:</span></span>

- [<span data-ttu-id="a9d51-133">class</span><span class="sxs-lookup"><span data-stu-id="a9d51-133">class</span></span>](../../../csharp/language-reference/keywords/class.md)

- [<span data-ttu-id="a9d51-134">struct</span><span class="sxs-lookup"><span data-stu-id="a9d51-134">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)

### <a name="Members"></a> <span data-ttu-id="a9d51-135">Члены класса</span><span class="sxs-lookup"><span data-stu-id="a9d51-135">Class Members</span></span>

<span data-ttu-id="a9d51-136">Каждый класс может состоять из различных *членов класса*, которые содержат свойства, описывающие данные класса, методы, задающие поведение класса, и события, обеспечивающие связь между различными классами и объектами.</span><span class="sxs-lookup"><span data-stu-id="a9d51-136">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="Properties"></a> <span data-ttu-id="a9d51-137">Свойства и поля</span><span class="sxs-lookup"><span data-stu-id="a9d51-137">Properties and Fields</span></span>

<span data-ttu-id="a9d51-138">Поля и свойства представляют сведения, содержащиеся в объекте.</span><span class="sxs-lookup"><span data-stu-id="a9d51-138">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="a9d51-139">Поля подобны переменным в том, что их можно прочитать или изменить напрямую.</span><span class="sxs-lookup"><span data-stu-id="a9d51-139">Fields are like variables because they can be read or set directly.</span></span>

<span data-ttu-id="a9d51-140">Определение поля:</span><span class="sxs-lookup"><span data-stu-id="a9d51-140">To define a field:</span></span>

```csharp
class SampleClass
{
    public string sampleField;
}
```

<span data-ttu-id="a9d51-141">Для работы со свойствами используются процедуры "Get" и "Set", которые расширяют возможности управления способом задания и возврата значений.</span><span class="sxs-lookup"><span data-stu-id="a9d51-141">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="a9d51-142">В языке C# для хранения значения свойства можно создать частное поле (private) или использовать так называемые автоматически реализуемые свойства, которые автоматически создают это поле и обеспечивают базовую логику для процедур свойств.</span><span class="sxs-lookup"><span data-stu-id="a9d51-142">C# allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="a9d51-143">Определение автоматически реализуемого свойства:</span><span class="sxs-lookup"><span data-stu-id="a9d51-143">To define an auto-implemented property:</span></span>

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

<span data-ttu-id="a9d51-144">Если требуется выполнить дополнительные операции чтения и записи применительно к значению свойства, определите поле для хранения значения свойства и затем реализуйте базовую логику для хранения и извлечения этого значения:</span><span class="sxs-lookup"><span data-stu-id="a9d51-144">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

```csharp
class SampleClass
{
    private int _sample;
    public int Sample
    {
        // Return the value stored in a field.
        get { return _sample; }
        // Store the value in the field.
        set { _sample = value; }
    }
}
```

<span data-ttu-id="a9d51-145">У большинства свойств есть методы или процедуры для задания и возврата значения свойства.</span><span class="sxs-lookup"><span data-stu-id="a9d51-145">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="a9d51-146">Однако можно создать свойства, доступные только для чтения или только на запись, чтобы запретить изменение или чтение значений свойств.</span><span class="sxs-lookup"><span data-stu-id="a9d51-146">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="a9d51-147">В C# можно опустить метод свойства `get` или `set`.</span><span class="sxs-lookup"><span data-stu-id="a9d51-147">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="a9d51-148">Следует отметить, что автоматически реализуемые свойства нельзя сделать доступными только для чтения или только для записи.</span><span class="sxs-lookup"><span data-stu-id="a9d51-148">However, auto-implemented properties cannot be read-only or write-only.</span></span>

<span data-ttu-id="a9d51-149">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="a9d51-149">For more information, see:</span></span>

- [<span data-ttu-id="a9d51-150">get</span><span class="sxs-lookup"><span data-stu-id="a9d51-150">get</span></span>](../../../csharp/language-reference/keywords/get.md)

- [<span data-ttu-id="a9d51-151">set</span><span class="sxs-lookup"><span data-stu-id="a9d51-151">set</span></span>](../../../csharp/language-reference/keywords/set.md)

#### <a name="Methods"></a> <span data-ttu-id="a9d51-152">Методы</span><span class="sxs-lookup"><span data-stu-id="a9d51-152">Methods</span></span>

<span data-ttu-id="a9d51-153">Действие, которое выполняет объект, называется *методом*.</span><span class="sxs-lookup"><span data-stu-id="a9d51-153">A *method* is an action that an object can perform.</span></span>

<span data-ttu-id="a9d51-154">Определение метода класса:</span><span class="sxs-lookup"><span data-stu-id="a9d51-154">To define a method of a class:</span></span>

```csharp
class SampleClass
{
    public int sampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

<span data-ttu-id="a9d51-155">Класс может иметь несколько реализаций или *перегрузок* одного и того же метода, которые отличаются от других числом или типами параметров.</span><span class="sxs-lookup"><span data-stu-id="a9d51-155">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="a9d51-156">Перегрузка метода:</span><span class="sxs-lookup"><span data-stu-id="a9d51-156">To overload a method:</span></span>

```csharp
public int sampleMethod(string sampleParam) {};
public int sampleMethod(int sampleParam) {}
```

<span data-ttu-id="a9d51-157">Как правило, метод объявляется при определении класса.</span><span class="sxs-lookup"><span data-stu-id="a9d51-157">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="a9d51-158">Однако C# также поддерживает *методы расширения*, которые позволяют добавлять методы в существующий класс вне определения класса.</span><span class="sxs-lookup"><span data-stu-id="a9d51-158">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="a9d51-159">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="a9d51-159">For more information, see:</span></span>

- [<span data-ttu-id="a9d51-160">Методы</span><span class="sxs-lookup"><span data-stu-id="a9d51-160">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="a9d51-161">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="a9d51-161">Extension Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)

#### <a name="Constructors"></a> <span data-ttu-id="a9d51-162">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="a9d51-162">Constructors</span></span>

<span data-ttu-id="a9d51-163">Конструкторы — это методы классов, выполняемые автоматически при создании объекта заданного типа.</span><span class="sxs-lookup"><span data-stu-id="a9d51-163">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="a9d51-164">Обычно конструкторы выполняют инициализацию членов данных нового объекта.</span><span class="sxs-lookup"><span data-stu-id="a9d51-164">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="a9d51-165">Конструктор можно запустить только один раз при создании класса.</span><span class="sxs-lookup"><span data-stu-id="a9d51-165">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="a9d51-166">Кроме того, код конструктора всегда выполняется раньше всех остальных частей кода в классе.</span><span class="sxs-lookup"><span data-stu-id="a9d51-166">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="a9d51-167">Следует отметить, что так же, как и для других методов, можно создать несколько перегрузок конструктора.</span><span class="sxs-lookup"><span data-stu-id="a9d51-167">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="a9d51-168">Определение конструктора для класса:</span><span class="sxs-lookup"><span data-stu-id="a9d51-168">To define a constructor for a class:</span></span>

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

<span data-ttu-id="a9d51-169">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="a9d51-169">For more information, see:</span></span>

<span data-ttu-id="a9d51-170">[Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="a9d51-170">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md).</span></span>

#### <a name="Finalizers"></a> <span data-ttu-id="a9d51-171">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="a9d51-171">Finalizers</span></span>

<span data-ttu-id="a9d51-172">Методы завершения используются для уничтожения экземпляров классов.</span><span class="sxs-lookup"><span data-stu-id="a9d51-172">Finalizers are used to destruct instances of classes.</span></span> <span data-ttu-id="a9d51-173">В платформе .NET Framework сборщик мусора автоматически управляет распределением и освобождением памяти для управляемых объектов приложения.</span><span class="sxs-lookup"><span data-stu-id="a9d51-173">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="a9d51-174">Однако для очистки неуправляемых ресурсов, создаваемых приложением, могут потребоваться методы завершения.</span><span class="sxs-lookup"><span data-stu-id="a9d51-174">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="a9d51-175">На один класс допускается только один метод завершения.</span><span class="sxs-lookup"><span data-stu-id="a9d51-175">There can be only one finalizers for a class.</span></span>

<span data-ttu-id="a9d51-176">Дополнительные сведения о методах завершения и сборке мусора в .NET Framework см. в разделе [Сборка мусора](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="a9d51-176">For more information about finalizers and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="Events"></a> <span data-ttu-id="a9d51-177">События</span><span class="sxs-lookup"><span data-stu-id="a9d51-177">Events</span></span>

<span data-ttu-id="a9d51-178">События позволяют классу или объекту уведомлять другие классы или объекты о возникновении каких-либо ситуаций.</span><span class="sxs-lookup"><span data-stu-id="a9d51-178">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="a9d51-179">Класс, отправляющий (или порождающий) событие, называется *издателем*, а классы, принимающие (или обрабатывающие) событие, называются *подписчиками*.</span><span class="sxs-lookup"><span data-stu-id="a9d51-179">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="a9d51-180">Дополнительные сведения о том, как порождаются и обрабатываются события, см. в разделе [События](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="a9d51-180">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="a9d51-181">Чтобы объявить событие в классе, используйте ключевое слово [event](../../../csharp/language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="a9d51-181">To declare an event in a class, use the [event](../../../csharp/language-reference/keywords/event.md) keyword.</span></span>

- <span data-ttu-id="a9d51-182">Чтобы породить событие, вызовите делегат события.</span><span class="sxs-lookup"><span data-stu-id="a9d51-182">To raise an event, invoke the event delegate.</span></span>

- <span data-ttu-id="a9d51-183">Чтобы подписаться на событие, используйте оператор `+=`. Чтобы отменить подписку на событие, воспользуйтесь оператором `-=`.</span><span class="sxs-lookup"><span data-stu-id="a9d51-183">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>

#### <a name="NestedClasses"></a> <span data-ttu-id="a9d51-184">Вложенные классы</span><span class="sxs-lookup"><span data-stu-id="a9d51-184">Nested Classes</span></span>

<span data-ttu-id="a9d51-185">Класс, определенный внутри другого класса, называется *вложенным*.</span><span class="sxs-lookup"><span data-stu-id="a9d51-185">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="a9d51-186">По умолчанию вложенный класс является частным.</span><span class="sxs-lookup"><span data-stu-id="a9d51-186">By default, the nested class is private.</span></span>

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

<span data-ttu-id="a9d51-187">Чтобы создать экземпляр вложенного класса, укажите имя класса контейнера и имя вложенного класса, используя в качестве разделителя точку:</span><span class="sxs-lookup"><span data-stu-id="a9d51-187">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="AccessModifiers"></a> <span data-ttu-id="a9d51-188">Модификаторы доступа и уровни доступа</span><span class="sxs-lookup"><span data-stu-id="a9d51-188">Access Modifiers and Access Levels</span></span>

<span data-ttu-id="a9d51-189">С помощью *модификаторов доступа* все классы и члены классов могут указывать уровни доступа, предоставляемые другим классам.</span><span class="sxs-lookup"><span data-stu-id="a9d51-189">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="a9d51-190">Имеющиеся модификаторы доступа указаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a9d51-190">The following access modifiers are available:</span></span>

|<span data-ttu-id="a9d51-191">Модификатор C#</span><span class="sxs-lookup"><span data-stu-id="a9d51-191">C# Modifier</span></span>|<span data-ttu-id="a9d51-192">Определение</span><span class="sxs-lookup"><span data-stu-id="a9d51-192">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="a9d51-193">public</span><span class="sxs-lookup"><span data-stu-id="a9d51-193">public</span></span>](../../../csharp/language-reference/keywords/public.md)|<span data-ttu-id="a9d51-194">Доступ к типу или члену возможен из любого другого кода в той же сборке или другой сборке, ссылающейся на него.</span><span class="sxs-lookup"><span data-stu-id="a9d51-194">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="a9d51-195">private</span><span class="sxs-lookup"><span data-stu-id="a9d51-195">private</span></span>](../../../csharp/language-reference/keywords/private.md)|<span data-ttu-id="a9d51-196">Доступ к типу или члену можно получить только из кода в том же классе.</span><span class="sxs-lookup"><span data-stu-id="a9d51-196">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="a9d51-197">protected</span><span class="sxs-lookup"><span data-stu-id="a9d51-197">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)|<span data-ttu-id="a9d51-198">Доступ к типу или члену можно получить только из кода в том же классе или в производном классе.</span><span class="sxs-lookup"><span data-stu-id="a9d51-198">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="a9d51-199">internal</span><span class="sxs-lookup"><span data-stu-id="a9d51-199">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)|<span data-ttu-id="a9d51-200">Доступ к типу или члену возможен из любого кода в той же сборке, но не из другой сборки.</span><span class="sxs-lookup"><span data-stu-id="a9d51-200">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|[<span data-ttu-id="a9d51-201">protected internal</span><span class="sxs-lookup"><span data-stu-id="a9d51-201">protected internal</span></span>](../../../csharp/language-reference/keywords/protected-internal.md)|<span data-ttu-id="a9d51-202">Доступ к типу или члену возможен из любого кода в той же сборке, или из производного класса в другой сборке.</span><span class="sxs-lookup"><span data-stu-id="a9d51-202">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|
|[<span data-ttu-id="a9d51-203">private protected</span><span class="sxs-lookup"><span data-stu-id="a9d51-203">private protected</span></span>](../../../csharp/language-reference/keywords/private-protected.md)|<span data-ttu-id="a9d51-204">Доступ к типу или члену можно получить из кода в том же классе или в производном классе в сборке базового класса.</span><span class="sxs-lookup"><span data-stu-id="a9d51-204">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span>|

<span data-ttu-id="a9d51-205">Дополнительные сведения см. в статье [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="a9d51-205">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>

### <a name="InstantiatingClasses"></a> <span data-ttu-id="a9d51-206">Создание экземпляров классов</span><span class="sxs-lookup"><span data-stu-id="a9d51-206">Instantiating Classes</span></span>

<span data-ttu-id="a9d51-207">Чтобы создать объект, необходимо создать экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="a9d51-207">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```csharp
SampleClass sampleObject = new SampleClass();
```

<span data-ttu-id="a9d51-208">После создания экземпляра класса можно присваивать значения свойствам и полям экземпляра и вызывать методы класса.</span><span class="sxs-lookup"><span data-stu-id="a9d51-208">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.sampleMethod();
```

<span data-ttu-id="a9d51-209">Чтобы назначить значения свойствам в процессе создания экземпляра класса, используйте инициализаторы объектов:</span><span class="sxs-lookup"><span data-stu-id="a9d51-209">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```csharp
// Set a property value.
SampleClass sampleObject = new SampleClass
    { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="a9d51-210">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="a9d51-210">For more information, see:</span></span>

- [<span data-ttu-id="a9d51-211">Оператор new</span><span class="sxs-lookup"><span data-stu-id="a9d51-211">new Operator</span></span>](../../../csharp/language-reference/operators/new-operator.md)

- [<span data-ttu-id="a9d51-212">Инициализаторы объектов и коллекций</span><span class="sxs-lookup"><span data-stu-id="a9d51-212">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)

### <a name="Static"></a> <span data-ttu-id="a9d51-213">Статические классы и их члены</span><span class="sxs-lookup"><span data-stu-id="a9d51-213">Static Classes and Members</span></span>

<span data-ttu-id="a9d51-214">Статический член класса — это свойство, процедура или поле, которое совместно используется всеми экземплярами класса.</span><span class="sxs-lookup"><span data-stu-id="a9d51-214">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

<span data-ttu-id="a9d51-215">Определение статического члена</span><span class="sxs-lookup"><span data-stu-id="a9d51-215">To define a static member:</span></span>

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

<span data-ttu-id="a9d51-216">Чтобы получить доступ к статическому члену, используйте имя класса без создания объекта этого класса:</span><span class="sxs-lookup"><span data-stu-id="a9d51-216">To access the static member, use the name of the class without creating an object of this class:</span></span>

```csharp
Console.WriteLine(SampleClass.SampleString);
```

<span data-ttu-id="a9d51-217">Статические классы в C# имеют только статические члены и не могут быть созданы.</span><span class="sxs-lookup"><span data-stu-id="a9d51-217">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="a9d51-218">Статические члены также не могут обращаться к нестатическим свойствам, полям или методам.</span><span class="sxs-lookup"><span data-stu-id="a9d51-218">Static members also cannot access non-static  properties, fields or methods</span></span>

<span data-ttu-id="a9d51-219">Дополнительные сведения см. в разделе [static](../../../csharp/language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="a9d51-219">For more information, see: [static](../../../csharp/language-reference/keywords/static.md).</span></span>

### <a name="AnonymousTypes"></a> <span data-ttu-id="a9d51-220">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="a9d51-220">Anonymous Types</span></span>

<span data-ttu-id="a9d51-221">Анонимные типы позволяют создавать объекты без написания определения класса для типа данных.</span><span class="sxs-lookup"><span data-stu-id="a9d51-221">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="a9d51-222">Вместо этого компилятор создает класс для вас.</span><span class="sxs-lookup"><span data-stu-id="a9d51-222">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="a9d51-223">Данный класс не имеет имени и содержит свойства, которые указаны при объявлении объекта.</span><span class="sxs-lookup"><span data-stu-id="a9d51-223">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="a9d51-224">Создание экземпляра анонимного типа:</span><span class="sxs-lookup"><span data-stu-id="a9d51-224">To create an instance of an anonymous type:</span></span>

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject =
    new { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="a9d51-225">Дополнительные сведения: [Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="a9d51-225">For more information, see: [Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>

## <a name="Inheritance"></a> <span data-ttu-id="a9d51-226">Наследование</span><span class="sxs-lookup"><span data-stu-id="a9d51-226">Inheritance</span></span>

<span data-ttu-id="a9d51-227">Наследование позволяет создавать новые классы, которые повторно используют, расширяют и изменяют поведение, определенное в другом классе.</span><span class="sxs-lookup"><span data-stu-id="a9d51-227">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="a9d51-228">Класс, члены которого наследуются, называется *базовым классом*, а класс, который наследует эти члены, называется *производным классом*.</span><span class="sxs-lookup"><span data-stu-id="a9d51-228">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="a9d51-229">Следует учитывать, что все классы в C# неявно наследуются от класса <xref:System.Object>, который поддерживает иерархию классов .NET и предоставляет низкоуровневые службы для всех классов.</span><span class="sxs-lookup"><span data-stu-id="a9d51-229">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="a9d51-230">C# не поддерживает множественное наследование.</span><span class="sxs-lookup"><span data-stu-id="a9d51-230">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="a9d51-231">То есть можно указать только один базовый класс для производного класса.</span><span class="sxs-lookup"><span data-stu-id="a9d51-231">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="a9d51-232">Наследование от базового класса:</span><span class="sxs-lookup"><span data-stu-id="a9d51-232">To inherit from a base class:</span></span>

```csharp
class DerivedClass:BaseClass {}
```

<span data-ttu-id="a9d51-233">По умолчанию унаследовать класс можно от любого класса.</span><span class="sxs-lookup"><span data-stu-id="a9d51-233">By default all classes can be inherited.</span></span> <span data-ttu-id="a9d51-234">Однако можно указать, должен ли класс использоваться в качестве базового класса, или создать класс, который может использоваться только в качестве базового.</span><span class="sxs-lookup"><span data-stu-id="a9d51-234">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="a9d51-235">Указание, что класс не может использоваться в качестве базового класса:</span><span class="sxs-lookup"><span data-stu-id="a9d51-235">To specify that a class cannot be used as a base class:</span></span>

```csharp
public sealed class A { }
```

<span data-ttu-id="a9d51-236">Указание, что класс может использоваться только в качестве базового класса и нельзя создать экземпляр этого класса:</span><span class="sxs-lookup"><span data-stu-id="a9d51-236">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```csharp
public abstract class B { }
```

<span data-ttu-id="a9d51-237">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="a9d51-237">For more information, see:</span></span>

- [<span data-ttu-id="a9d51-238">sealed</span><span class="sxs-lookup"><span data-stu-id="a9d51-238">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)

- [<span data-ttu-id="a9d51-239">abstract</span><span class="sxs-lookup"><span data-stu-id="a9d51-239">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)

### <a name="Overriding"></a> <span data-ttu-id="a9d51-240">Переопределение членов</span><span class="sxs-lookup"><span data-stu-id="a9d51-240">Overriding Members</span></span>

<span data-ttu-id="a9d51-241">По умолчанию производный класс наследует все члены от своего базового класса.</span><span class="sxs-lookup"><span data-stu-id="a9d51-241">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="a9d51-242">Если необходимо изменить поведение унаследованного члена, необходимо переопределить его.</span><span class="sxs-lookup"><span data-stu-id="a9d51-242">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="a9d51-243">Т. е. в производном классе можно определить новую реализацию метода, свойства или события.</span><span class="sxs-lookup"><span data-stu-id="a9d51-243">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="a9d51-244">Следующие модификаторы используются для управления переопределением свойств и методов.</span><span class="sxs-lookup"><span data-stu-id="a9d51-244">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="a9d51-245">Модификатор C#</span><span class="sxs-lookup"><span data-stu-id="a9d51-245">C# Modifier</span></span>|<span data-ttu-id="a9d51-246">Определение</span><span class="sxs-lookup"><span data-stu-id="a9d51-246">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="a9d51-247">virtual</span><span class="sxs-lookup"><span data-stu-id="a9d51-247">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)|<span data-ttu-id="a9d51-248">Разрешает переопределение члена класса в производном классе.</span><span class="sxs-lookup"><span data-stu-id="a9d51-248">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="a9d51-249">override</span><span class="sxs-lookup"><span data-stu-id="a9d51-249">override</span></span>](../../../csharp/language-reference/keywords/override.md)|<span data-ttu-id="a9d51-250">Переопределяет виртуальный (переопределяемый) член в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="a9d51-250">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="a9d51-251">abstract</span><span class="sxs-lookup"><span data-stu-id="a9d51-251">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)|<span data-ttu-id="a9d51-252">Требует, чтобы член класса был переопределен в производном классе.</span><span class="sxs-lookup"><span data-stu-id="a9d51-252">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="a9d51-253">Модификатор new</span><span class="sxs-lookup"><span data-stu-id="a9d51-253">new Modifier</span></span>](../../../csharp/language-reference/keywords/new-modifier.md)|<span data-ttu-id="a9d51-254">Скрывает член, наследуемый от базового класса</span><span class="sxs-lookup"><span data-stu-id="a9d51-254">Hides a member inherited from a base class</span></span>|

## <a name="Interfaces"></a> <span data-ttu-id="a9d51-255">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="a9d51-255">Interfaces</span></span>

<span data-ttu-id="a9d51-256">Интерфейсы, как и классы, определяют набор свойств, методов и событий.</span><span class="sxs-lookup"><span data-stu-id="a9d51-256">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="a9d51-257">Но, в отличие от классов, интерфейсы не предоставляют реализацию.</span><span class="sxs-lookup"><span data-stu-id="a9d51-257">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="a9d51-258">Они реализуются классами, но определяются как отдельные от классов сущности.</span><span class="sxs-lookup"><span data-stu-id="a9d51-258">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="a9d51-259">Интерфейс представляет собой контракт, в котором класс, реализующий интерфейс, должен реализовывать каждый аспект этого интерфейса в точном соответствии с его определением.</span><span class="sxs-lookup"><span data-stu-id="a9d51-259">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="a9d51-260">Определение интерфейса:</span><span class="sxs-lookup"><span data-stu-id="a9d51-260">To define an interface:</span></span>

```csharp
interface ISampleInterface
{
    void doSomething();
}
```

<span data-ttu-id="a9d51-261">Реализация интерфейса в классе:</span><span class="sxs-lookup"><span data-stu-id="a9d51-261">To implement an interface in a class:</span></span>

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.doSomething()
    {
        // Method implementation.
    }
}
```

<span data-ttu-id="a9d51-262">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="a9d51-262">For more information, see:</span></span>

[<span data-ttu-id="a9d51-263">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="a9d51-263">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)

[<span data-ttu-id="a9d51-264">interface</span><span class="sxs-lookup"><span data-stu-id="a9d51-264">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)

## <a name="Generics"></a> <span data-ttu-id="a9d51-265">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="a9d51-265">Generics</span></span>

<span data-ttu-id="a9d51-266">Классы, структуры, интерфейсы и методы в платформе .NET Framework могут иметь *параметры типа*, которые определяют типы объектов, которые они могут хранить или использовать.</span><span class="sxs-lookup"><span data-stu-id="a9d51-266">Classes, structures, interfaces and methods in the .NET Framework can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="a9d51-267">Наиболее распространенным примером универсального шаблона является коллекция, в которой можно указать тип объектов, которые могут в ней храниться.</span><span class="sxs-lookup"><span data-stu-id="a9d51-267">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="a9d51-268">Определение универсального класса:</span><span class="sxs-lookup"><span data-stu-id="a9d51-268">To define a generic class:</span></span>

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

<span data-ttu-id="a9d51-269">Создание экземпляра универсального класса:</span><span class="sxs-lookup"><span data-stu-id="a9d51-269">To create an instance of a generic class:</span></span>

```csharp
SampleGeneric<string> sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

<span data-ttu-id="a9d51-270">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="a9d51-270">For more information, see:</span></span>

- [<span data-ttu-id="a9d51-271">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="a9d51-271">Generics</span></span>](~/docs/standard/generics/index.md)

- [<span data-ttu-id="a9d51-272">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="a9d51-272">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)

## <a name="Delegates"></a> <span data-ttu-id="a9d51-273">Делегаты</span><span class="sxs-lookup"><span data-stu-id="a9d51-273">Delegates</span></span>

<span data-ttu-id="a9d51-274">*Делегат* — это тип, который определяет сигнатуру метода и может обеспечивать связь с любым методом с совместимой сигнатурой.</span><span class="sxs-lookup"><span data-stu-id="a9d51-274">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="a9d51-275">Метод можно запустить (или вызвать) с помощью делегата.</span><span class="sxs-lookup"><span data-stu-id="a9d51-275">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="a9d51-276">Делегаты используются для передачи методов в качестве аргументов к другим методам.</span><span class="sxs-lookup"><span data-stu-id="a9d51-276">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="a9d51-277">Обработчики событий — это ничто иное, как методы, вызываемые с помощью делегатов.</span><span class="sxs-lookup"><span data-stu-id="a9d51-277">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="a9d51-278">Дополнительные сведения об использовании делегатов при обработке событий см. в разделе [События](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="a9d51-278">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="a9d51-279">Создание делегата:</span><span class="sxs-lookup"><span data-stu-id="a9d51-279">To create a delegate:</span></span>

```csharp
public delegate void SampleDelegate(string str);
```

<span data-ttu-id="a9d51-280">Создание ссылки на метод, сигнатура которого соответствует сигнатуре, указанной делегатом:</span><span class="sxs-lookup"><span data-stu-id="a9d51-280">To create a reference to a method that matches the signature specified by the delegate:</span></span>

```csharp
class SampleClass
{
    // Method that matches the SampleDelegate signature.
    public static void sampleMethod(string message)
    {
        // Add code here.
    }
    // Method that instantiates the delegate.
    void SampleDelegate()
    {
        SampleDelegate sd = sampleMethod;
        sd("Sample string");
    }
}
```

<span data-ttu-id="a9d51-281">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="a9d51-281">For more information, see:</span></span>

- [<span data-ttu-id="a9d51-282">Делегаты</span><span class="sxs-lookup"><span data-stu-id="a9d51-282">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)

- [<span data-ttu-id="a9d51-283">delegate</span><span class="sxs-lookup"><span data-stu-id="a9d51-283">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)

## <a name="see-also"></a><span data-ttu-id="a9d51-284">См. также</span><span class="sxs-lookup"><span data-stu-id="a9d51-284">See also</span></span>

- [<span data-ttu-id="a9d51-285">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a9d51-285">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
