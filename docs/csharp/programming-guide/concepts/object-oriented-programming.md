---
title: Объектно ориентированное программирование (C#)
ms.date: 02/08/2020
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: 01d6f55bf0752f902f351675c4596abbb8ac85c2
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77627894"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="d0c10-102">Объектно-ориентированное программирование (C#)</span><span class="sxs-lookup"><span data-stu-id="d0c10-102">Object-Oriented programming (C#)</span></span>

<span data-ttu-id="d0c10-103">C# обеспечивает полную поддержку объектно ориентированного программирования, включая инкапсуляцию, наследование и полиморфизм.</span><span class="sxs-lookup"><span data-stu-id="d0c10-103">C# provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

- <span data-ttu-id="d0c10-104">*Инкапсуляция* означает, что группа связанных свойств, методов и других членов рассматривается как единый элемент или объект.</span><span class="sxs-lookup"><span data-stu-id="d0c10-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>
- <span data-ttu-id="d0c10-105">*Наследование* описывает возможность создания новых классов на основе существующих классов.</span><span class="sxs-lookup"><span data-stu-id="d0c10-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>
- <span data-ttu-id="d0c10-106">*Полиморфизм* означает, что можно иметь несколько взаимозаменяемых классов, даже если каждый класс реализует одни и те же свойства или методы разными способами.</span><span class="sxs-lookup"><span data-stu-id="d0c10-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

## <a name="classes-and-objects"></a><span data-ttu-id="d0c10-107">Классы и объекты</span><span class="sxs-lookup"><span data-stu-id="d0c10-107">Classes and objects</span></span>

<span data-ttu-id="d0c10-108">Термины *класс* и *объект* описывают *тип* объектов и *экземпляры* классов, соответственно.</span><span class="sxs-lookup"><span data-stu-id="d0c10-108">The terms *class* and *object* describe the *type* of objects, and the *instances* of classes, respectively.</span></span> <span data-ttu-id="d0c10-109">Поэтому процесс создания объекта называется *созданием экземпляра*.</span><span class="sxs-lookup"><span data-stu-id="d0c10-109">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="d0c10-110">Если использовать сравнение с чертежом, то класс является чертежом, а объект является зданием, построенным по нему.</span><span class="sxs-lookup"><span data-stu-id="d0c10-110">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="d0c10-111">Определение класса:</span><span class="sxs-lookup"><span data-stu-id="d0c10-111">To define a class:</span></span>

```csharp
class SampleClass
{
}
```

<span data-ttu-id="d0c10-112">C# также предоставляет типы, называемые *структурами*, которые удобно использовать, когда не требуется поддержка наследования или полиморфизма.</span><span class="sxs-lookup"><span data-stu-id="d0c10-112">C# also provides types called *structures* that are useful when you don't need support for inheritance or polymorphism.</span></span>

<span data-ttu-id="d0c10-113">Определение структуры:</span><span class="sxs-lookup"><span data-stu-id="d0c10-113">To define a structure:</span></span>

```csharp
struct SampleStruct
{
}
```

<span data-ttu-id="d0c10-114">Дополнительные сведения см. в статьях, посвященных ключевым словам [class](../../language-reference/keywords/class.md) и [struct](../../language-reference/builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="d0c10-114">For more information, see the articles on the [class](../../language-reference/keywords/class.md) and [struct](../../language-reference/builtin-types/struct.md) keywords.</span></span>

### <a name="class-members"></a><span data-ttu-id="d0c10-115">Члены класса</span><span class="sxs-lookup"><span data-stu-id="d0c10-115">Class members</span></span>

<span data-ttu-id="d0c10-116">Каждый класс может состоять из различных *членов класса*, которые содержат свойства, описывающие данные класса, методы, задающие поведение класса, и события, обеспечивающие связь между различными классами и объектами.</span><span class="sxs-lookup"><span data-stu-id="d0c10-116">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="d0c10-117">Свойства и поля</span><span class="sxs-lookup"><span data-stu-id="d0c10-117">Properties and fields</span></span>

<span data-ttu-id="d0c10-118">Поля и свойства представляют сведения, содержащиеся в объекте.</span><span class="sxs-lookup"><span data-stu-id="d0c10-118">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="d0c10-119">Поля подобны переменным в том, что их можно прочитать или изменить напрямую с использованием применимых модификаторов доступа.</span><span class="sxs-lookup"><span data-stu-id="d0c10-119">Fields are like variables because they can be read or set directly, subject to applicable access modifiers.</span></span>

<span data-ttu-id="d0c10-120">Определение поля, доступ к которому можно получить из экземпляров класса:</span><span class="sxs-lookup"><span data-stu-id="d0c10-120">To define a field that can be accessed from within instances of the class:</span></span>

```csharp
public class SampleClass
{
    string sampleField;
}
```

<span data-ttu-id="d0c10-121">Для работы со свойствами используются методы доступа `get` и `set`, которые расширяют возможности управления способом задания и возврата значений.</span><span class="sxs-lookup"><span data-stu-id="d0c10-121">Properties have `get` and `set` accessors, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="d0c10-122">В языке C# для хранения значения свойства можно создать частное поле (private) или использовать автоматически реализуемые свойства, которые автоматически создают такое поле и обеспечивают базовую логику для процедур свойств.</span><span class="sxs-lookup"><span data-stu-id="d0c10-122">C# allows you either to create a private field for storing the property value or use auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="d0c10-123">Определение автоматически реализуемого свойства:</span><span class="sxs-lookup"><span data-stu-id="d0c10-123">To define an auto-implemented property:</span></span>

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

<span data-ttu-id="d0c10-124">Если требуется выполнить дополнительные операции чтения и записи применительно к значению свойства, определите поле для хранения значения свойства и затем реализуйте базовую логику для хранения и извлечения этого значения:</span><span class="sxs-lookup"><span data-stu-id="d0c10-124">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

```csharp
class SampleClass
{
    private int _sample;
    public int Sample
    {
        // Return the value stored in a field.
        get => _sample;
        // Store the value in the field.
        set =>  _sample = value;
    }
}
```

<span data-ttu-id="d0c10-125">У большинства свойств есть методы или процедуры для задания и возврата значения свойства.</span><span class="sxs-lookup"><span data-stu-id="d0c10-125">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="d0c10-126">Однако можно создать свойства, доступные только для чтения или только на запись, чтобы запретить изменение или чтение значений свойств.</span><span class="sxs-lookup"><span data-stu-id="d0c10-126">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="d0c10-127">В C# можно опустить метод свойства `get` или `set`.</span><span class="sxs-lookup"><span data-stu-id="d0c10-127">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="d0c10-128">Следует отметить, что автоматически реализуемые свойства не могут быть доступными только для записи.</span><span class="sxs-lookup"><span data-stu-id="d0c10-128">However, auto-implemented properties cannot be write-only.</span></span> <span data-ttu-id="d0c10-129">Автоматически реализуемые свойства, доступные только для чтения, можно задать в конструкторах содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="d0c10-129">Read-only auto-implemented properties can be set in constructors of the containing class.</span></span>

<span data-ttu-id="d0c10-130">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="d0c10-130">For more information, see:</span></span>

- [<span data-ttu-id="d0c10-131">get</span><span class="sxs-lookup"><span data-stu-id="d0c10-131">get</span></span>](../../language-reference/keywords/get.md)

- [<span data-ttu-id="d0c10-132">set</span><span class="sxs-lookup"><span data-stu-id="d0c10-132">set</span></span>](../../language-reference/keywords/set.md)

#### <a name="methods"></a><span data-ttu-id="d0c10-133">Методы</span><span class="sxs-lookup"><span data-stu-id="d0c10-133">Methods</span></span>

<span data-ttu-id="d0c10-134">Действие, которое выполняет объект, называется *методом*.</span><span class="sxs-lookup"><span data-stu-id="d0c10-134">A *method* is an action that an object can perform.</span></span>

<span data-ttu-id="d0c10-135">Определение метода класса:</span><span class="sxs-lookup"><span data-stu-id="d0c10-135">To define a method of a class:</span></span>

```csharp
class SampleClass
{
    public int sampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

<span data-ttu-id="d0c10-136">Класс может иметь несколько реализаций или *перегрузок* одного и того же метода, которые отличаются от других числом или типами параметров.</span><span class="sxs-lookup"><span data-stu-id="d0c10-136">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="d0c10-137">Перегрузка метода:</span><span class="sxs-lookup"><span data-stu-id="d0c10-137">To overload a method:</span></span>

```csharp
public int sampleMethod(string sampleParam) {}
public int sampleMethod(int sampleParam) {}
```

<span data-ttu-id="d0c10-138">Как правило, метод объявляется при определении класса.</span><span class="sxs-lookup"><span data-stu-id="d0c10-138">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="d0c10-139">Однако C# также поддерживает *методы расширения*, которые позволяют добавлять методы в существующий класс вне определения класса.</span><span class="sxs-lookup"><span data-stu-id="d0c10-139">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="d0c10-140">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="d0c10-140">For more information, see:</span></span>

- [<span data-ttu-id="d0c10-141">Методы</span><span class="sxs-lookup"><span data-stu-id="d0c10-141">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="d0c10-142">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="d0c10-142">Extension Methods</span></span>](../classes-and-structs/extension-methods.md)

#### <a name="constructors"></a><span data-ttu-id="d0c10-143">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="d0c10-143">Constructors</span></span>

<span data-ttu-id="d0c10-144">Конструкторы — это методы классов, выполняемые автоматически при создании объекта заданного типа.</span><span class="sxs-lookup"><span data-stu-id="d0c10-144">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="d0c10-145">Обычно конструкторы выполняют инициализацию членов данных нового объекта.</span><span class="sxs-lookup"><span data-stu-id="d0c10-145">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="d0c10-146">Конструктор можно запустить только один раз при создании класса.</span><span class="sxs-lookup"><span data-stu-id="d0c10-146">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="d0c10-147">Кроме того, код конструктора всегда выполняется раньше всех остальных частей кода в классе.</span><span class="sxs-lookup"><span data-stu-id="d0c10-147">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="d0c10-148">Следует отметить, что так же, как и для других методов, можно создать несколько перегрузок конструктора.</span><span class="sxs-lookup"><span data-stu-id="d0c10-148">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="d0c10-149">Определение конструктора для класса:</span><span class="sxs-lookup"><span data-stu-id="d0c10-149">To define a constructor for a class:</span></span>

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

<span data-ttu-id="d0c10-150">Дополнительные сведения см. в разделе [Конструкторы](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="d0c10-150">For more information, see [Constructors](../classes-and-structs/constructors.md).</span></span>

#### <a name="finalizers"></a><span data-ttu-id="d0c10-151">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="d0c10-151">Finalizers</span></span>

<span data-ttu-id="d0c10-152">Методы завершения используются для уничтожения экземпляров классов.</span><span class="sxs-lookup"><span data-stu-id="d0c10-152">Finalizers are used to destruct instances of classes.</span></span> <span data-ttu-id="d0c10-153">В платформе .NET Framework сборщик мусора автоматически управляет распределением и освобождением памяти для управляемых объектов приложения.</span><span class="sxs-lookup"><span data-stu-id="d0c10-153">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="d0c10-154">Однако для очистки неуправляемых ресурсов, создаваемых приложением, могут потребоваться методы завершения.</span><span class="sxs-lookup"><span data-stu-id="d0c10-154">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="d0c10-155">На один класс допускается только один метод завершения.</span><span class="sxs-lookup"><span data-stu-id="d0c10-155">There can be only one finalizers for a class.</span></span>

<span data-ttu-id="d0c10-156">Дополнительные сведения о методах завершения и сборке мусора в .NET Framework см. в разделе [Сборка мусора](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="d0c10-156">For more information about finalizers and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="d0c10-157">События</span><span class="sxs-lookup"><span data-stu-id="d0c10-157">Events</span></span>

<span data-ttu-id="d0c10-158">События позволяют классу или объекту уведомлять другие классы или объекты о возникновении каких-либо ситуаций.</span><span class="sxs-lookup"><span data-stu-id="d0c10-158">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="d0c10-159">Класс, отправляющий (или порождающий) событие, называется *издателем*, а классы, принимающие (или обрабатывающие) событие, называются *подписчиками*.</span><span class="sxs-lookup"><span data-stu-id="d0c10-159">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="d0c10-160">Дополнительные сведения о том, как порождаются и обрабатываются события, см. в разделе [События](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="d0c10-160">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="d0c10-161">Чтобы объявить событие в классе, используйте ключевое слово [event](../../language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="d0c10-161">To declare an event in a class, use the [event](../../language-reference/keywords/event.md) keyword.</span></span>

- <span data-ttu-id="d0c10-162">Чтобы породить событие, вызовите делегат события.</span><span class="sxs-lookup"><span data-stu-id="d0c10-162">To raise an event, invoke the event delegate.</span></span>

- <span data-ttu-id="d0c10-163">Чтобы подписаться на событие, используйте оператор `+=`. Чтобы отменить подписку на событие, воспользуйтесь оператором `-=`.</span><span class="sxs-lookup"><span data-stu-id="d0c10-163">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="d0c10-164">Вложенные классы</span><span class="sxs-lookup"><span data-stu-id="d0c10-164">Nested classes</span></span>

<span data-ttu-id="d0c10-165">Класс, определенный внутри другого класса, называется *вложенным*.</span><span class="sxs-lookup"><span data-stu-id="d0c10-165">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="d0c10-166">По умолчанию вложенный класс является частным.</span><span class="sxs-lookup"><span data-stu-id="d0c10-166">By default, the nested class is private.</span></span>

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

<span data-ttu-id="d0c10-167">Чтобы создать экземпляр вложенного класса, укажите имя класса контейнера и имя вложенного класса, используя в качестве разделителя точку:</span><span class="sxs-lookup"><span data-stu-id="d0c10-167">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="d0c10-168">Модификаторы доступа и уровни доступа</span><span class="sxs-lookup"><span data-stu-id="d0c10-168">Access modifiers and access levels</span></span>

<span data-ttu-id="d0c10-169">С помощью *модификаторов доступа* все классы и члены классов могут указывать уровни доступа, предоставляемые другим классам.</span><span class="sxs-lookup"><span data-stu-id="d0c10-169">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="d0c10-170">Имеющиеся модификаторы доступа указаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d0c10-170">The following access modifiers are available:</span></span>

|<span data-ttu-id="d0c10-171">Модификатор C#</span><span class="sxs-lookup"><span data-stu-id="d0c10-171">C# Modifier</span></span>|<span data-ttu-id="d0c10-172">Определение</span><span class="sxs-lookup"><span data-stu-id="d0c10-172">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="d0c10-173">public</span><span class="sxs-lookup"><span data-stu-id="d0c10-173">public</span></span>](../../language-reference/keywords/public.md)|<span data-ttu-id="d0c10-174">Доступ к типу или члену возможен из любого другого кода в той же сборке или другой сборке, ссылающейся на него.</span><span class="sxs-lookup"><span data-stu-id="d0c10-174">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="d0c10-175">private</span><span class="sxs-lookup"><span data-stu-id="d0c10-175">private</span></span>](../../language-reference/keywords/private.md)|<span data-ttu-id="d0c10-176">Доступ к типу или члену можно получить только из кода в том же классе.</span><span class="sxs-lookup"><span data-stu-id="d0c10-176">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="d0c10-177">protected</span><span class="sxs-lookup"><span data-stu-id="d0c10-177">protected</span></span>](../../language-reference/keywords/protected.md)|<span data-ttu-id="d0c10-178">Доступ к типу или члену можно получить только из кода в том же классе или в производном классе.</span><span class="sxs-lookup"><span data-stu-id="d0c10-178">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="d0c10-179">internal</span><span class="sxs-lookup"><span data-stu-id="d0c10-179">internal</span></span>](../../language-reference/keywords/internal.md)|<span data-ttu-id="d0c10-180">Доступ к типу или члену возможен из любого кода в той же сборке, но не из другой сборки.</span><span class="sxs-lookup"><span data-stu-id="d0c10-180">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|[<span data-ttu-id="d0c10-181">protected internal</span><span class="sxs-lookup"><span data-stu-id="d0c10-181">protected internal</span></span>](../../language-reference/keywords/protected-internal.md)|<span data-ttu-id="d0c10-182">Доступ к типу или члену возможен из любого кода в той же сборке, или из производного класса в другой сборке.</span><span class="sxs-lookup"><span data-stu-id="d0c10-182">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|
|[<span data-ttu-id="d0c10-183">private protected</span><span class="sxs-lookup"><span data-stu-id="d0c10-183">private protected</span></span>](../../language-reference/keywords/private-protected.md)|<span data-ttu-id="d0c10-184">Доступ к типу или члену можно получить из кода в том же классе или в производном классе в сборке базового класса.</span><span class="sxs-lookup"><span data-stu-id="d0c10-184">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span>|

<span data-ttu-id="d0c10-185">Дополнительные сведения см. в статье [Модификаторы доступа](../classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="d0c10-185">For more information, see [Access Modifiers](../classes-and-structs/access-modifiers.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="d0c10-186">Создание экземпляров классов</span><span class="sxs-lookup"><span data-stu-id="d0c10-186">Instantiating classes</span></span>

<span data-ttu-id="d0c10-187">Чтобы создать объект, необходимо создать экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="d0c10-187">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```csharp
SampleClass sampleObject = new SampleClass();
```

<span data-ttu-id="d0c10-188">После создания экземпляра класса можно присваивать значения свойствам и полям экземпляра и вызывать методы класса.</span><span class="sxs-lookup"><span data-stu-id="d0c10-188">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.sampleMethod();
```

<span data-ttu-id="d0c10-189">Чтобы назначить значения свойствам в процессе создания экземпляра класса, используйте инициализаторы объектов:</span><span class="sxs-lookup"><span data-stu-id="d0c10-189">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```csharp
// Set a property value.
SampleClass sampleObject = new SampleClass
    { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="d0c10-190">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="d0c10-190">For more information, see:</span></span>

- [<span data-ttu-id="d0c10-191">Оператор new</span><span class="sxs-lookup"><span data-stu-id="d0c10-191">new Operator</span></span>](../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="d0c10-192">Инициализаторы объектов и коллекций</span><span class="sxs-lookup"><span data-stu-id="d0c10-192">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)

### <a name="static-classes-and-members"></a><span data-ttu-id="d0c10-193">статические классы и их члены;</span><span class="sxs-lookup"><span data-stu-id="d0c10-193">Static Classes and Members</span></span>

<span data-ttu-id="d0c10-194">Статический член класса — это свойство, процедура или поле, которое совместно используется всеми экземплярами класса.</span><span class="sxs-lookup"><span data-stu-id="d0c10-194">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

<span data-ttu-id="d0c10-195">Определение статического члена</span><span class="sxs-lookup"><span data-stu-id="d0c10-195">To define a static member:</span></span>

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

<span data-ttu-id="d0c10-196">Чтобы получить доступ к статическому члену, используйте имя класса без создания объекта этого класса:</span><span class="sxs-lookup"><span data-stu-id="d0c10-196">To access the static member, use the name of the class without creating an object of this class:</span></span>

```csharp
Console.WriteLine(SampleClass.SampleString);
```

<span data-ttu-id="d0c10-197">Статические классы в C# имеют только статические члены и не могут быть созданы.</span><span class="sxs-lookup"><span data-stu-id="d0c10-197">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="d0c10-198">Статические члены также не могут обращаться к нестатическим свойствам, полям или методам.</span><span class="sxs-lookup"><span data-stu-id="d0c10-198">Static members also cannot access non-static  properties, fields or methods</span></span>

<span data-ttu-id="d0c10-199">Дополнительные сведения см. в разделе [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="d0c10-199">For more information, see: [static](../../language-reference/keywords/static.md).</span></span>

### <a name="anonymous-types"></a><span data-ttu-id="d0c10-200">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="d0c10-200">Anonymous types</span></span>

<span data-ttu-id="d0c10-201">Анонимные типы позволяют создавать объекты без написания определения класса для типа данных.</span><span class="sxs-lookup"><span data-stu-id="d0c10-201">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="d0c10-202">Вместо этого компилятор создает класс для вас.</span><span class="sxs-lookup"><span data-stu-id="d0c10-202">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="d0c10-203">Данный класс не имеет имени и содержит свойства, которые указаны при объявлении объекта.</span><span class="sxs-lookup"><span data-stu-id="d0c10-203">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="d0c10-204">Создание экземпляра анонимного типа:</span><span class="sxs-lookup"><span data-stu-id="d0c10-204">To create an instance of an anonymous type:</span></span>

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject =
    new { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="d0c10-205">Дополнительные сведения можно найти в разделе  [Анонимные типы](../classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="d0c10-205">For more information, see: [Anonymous Types](../classes-and-structs/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="d0c10-206">Наследование</span><span class="sxs-lookup"><span data-stu-id="d0c10-206">Inheritance</span></span>

<span data-ttu-id="d0c10-207">Наследование позволяет создавать новые классы, которые повторно используют, расширяют и изменяют поведение, определенное в другом классе.</span><span class="sxs-lookup"><span data-stu-id="d0c10-207">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="d0c10-208">Класс, члены которого наследуются, называется *базовым классом*, а класс, который наследует эти члены, называется *производным классом*.</span><span class="sxs-lookup"><span data-stu-id="d0c10-208">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="d0c10-209">Следует учитывать, что все классы в C# неявно наследуются от класса <xref:System.Object>, который поддерживает иерархию классов .NET и предоставляет низкоуровневые службы для всех классов.</span><span class="sxs-lookup"><span data-stu-id="d0c10-209">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="d0c10-210">C# не поддерживает множественное наследование.</span><span class="sxs-lookup"><span data-stu-id="d0c10-210">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="d0c10-211">То есть можно указать только один базовый класс для производного класса.</span><span class="sxs-lookup"><span data-stu-id="d0c10-211">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="d0c10-212">Наследование от базового класса:</span><span class="sxs-lookup"><span data-stu-id="d0c10-212">To inherit from a base class:</span></span>

```csharp
class DerivedClass:BaseClass {}
```

<span data-ttu-id="d0c10-213">По умолчанию унаследовать класс можно от любого класса.</span><span class="sxs-lookup"><span data-stu-id="d0c10-213">By default all classes can be inherited.</span></span> <span data-ttu-id="d0c10-214">Однако можно указать, должен ли класс использоваться в качестве базового класса, или создать класс, который может использоваться только в качестве базового.</span><span class="sxs-lookup"><span data-stu-id="d0c10-214">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="d0c10-215">Указание, что класс не может использоваться в качестве базового класса:</span><span class="sxs-lookup"><span data-stu-id="d0c10-215">To specify that a class cannot be used as a base class:</span></span>

```csharp
public sealed class A { }
```

<span data-ttu-id="d0c10-216">Указание, что класс может использоваться только в качестве базового класса и нельзя создать экземпляр этого класса:</span><span class="sxs-lookup"><span data-stu-id="d0c10-216">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```csharp
public abstract class B { }
```

<span data-ttu-id="d0c10-217">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="d0c10-217">For more information, see:</span></span>

- [<span data-ttu-id="d0c10-218">sealed</span><span class="sxs-lookup"><span data-stu-id="d0c10-218">sealed</span></span>](../../language-reference/keywords/sealed.md)

- [<span data-ttu-id="d0c10-219">abstract</span><span class="sxs-lookup"><span data-stu-id="d0c10-219">abstract</span></span>](../../language-reference/keywords/abstract.md)

### <a name="overriding-members"></a><span data-ttu-id="d0c10-220">переопределение членов;</span><span class="sxs-lookup"><span data-stu-id="d0c10-220">Overriding Members</span></span>

<span data-ttu-id="d0c10-221">По умолчанию производный класс наследует все члены от своего базового класса.</span><span class="sxs-lookup"><span data-stu-id="d0c10-221">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="d0c10-222">Если необходимо изменить поведение унаследованного члена, необходимо переопределить его.</span><span class="sxs-lookup"><span data-stu-id="d0c10-222">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="d0c10-223">Т. е. в производном классе можно определить новую реализацию метода, свойства или события.</span><span class="sxs-lookup"><span data-stu-id="d0c10-223">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="d0c10-224">Следующие модификаторы используются для управления переопределением свойств и методов.</span><span class="sxs-lookup"><span data-stu-id="d0c10-224">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="d0c10-225">Модификатор C#</span><span class="sxs-lookup"><span data-stu-id="d0c10-225">C# Modifier</span></span>|<span data-ttu-id="d0c10-226">Определение</span><span class="sxs-lookup"><span data-stu-id="d0c10-226">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="d0c10-227">virtual</span><span class="sxs-lookup"><span data-stu-id="d0c10-227">virtual</span></span>](../../language-reference/keywords/virtual.md)|<span data-ttu-id="d0c10-228">Разрешает переопределение члена класса в производном классе.</span><span class="sxs-lookup"><span data-stu-id="d0c10-228">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="d0c10-229">override</span><span class="sxs-lookup"><span data-stu-id="d0c10-229">override</span></span>](../../language-reference/keywords/override.md)|<span data-ttu-id="d0c10-230">Переопределяет виртуальный (переопределяемый) член в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="d0c10-230">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="d0c10-231">abstract</span><span class="sxs-lookup"><span data-stu-id="d0c10-231">abstract</span></span>](../../language-reference/keywords/abstract.md)|<span data-ttu-id="d0c10-232">Требует, чтобы член класса был переопределен в производном классе.</span><span class="sxs-lookup"><span data-stu-id="d0c10-232">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="d0c10-233">Модификатор new</span><span class="sxs-lookup"><span data-stu-id="d0c10-233">new Modifier</span></span>](../../language-reference/keywords/new-modifier.md)|<span data-ttu-id="d0c10-234">Скрывает член, наследуемый от базового класса</span><span class="sxs-lookup"><span data-stu-id="d0c10-234">Hides a member inherited from a base class</span></span>|

## <a name="interfaces"></a><span data-ttu-id="d0c10-235">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="d0c10-235">Interfaces</span></span>

<span data-ttu-id="d0c10-236">Интерфейсы, как и классы, определяют набор свойств, методов и событий.</span><span class="sxs-lookup"><span data-stu-id="d0c10-236">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="d0c10-237">Но, в отличие от классов, интерфейсы не предоставляют реализацию.</span><span class="sxs-lookup"><span data-stu-id="d0c10-237">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="d0c10-238">Они реализуются классами, но определяются как отдельные от классов сущности.</span><span class="sxs-lookup"><span data-stu-id="d0c10-238">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="d0c10-239">Интерфейс представляет собой контракт, в котором класс, реализующий интерфейс, должен реализовывать каждый аспект этого интерфейса в точном соответствии с его определением.</span><span class="sxs-lookup"><span data-stu-id="d0c10-239">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="d0c10-240">Определение интерфейса:</span><span class="sxs-lookup"><span data-stu-id="d0c10-240">To define an interface:</span></span>

```csharp
interface ISampleInterface
{
    void doSomething();
}
```

<span data-ttu-id="d0c10-241">Реализация интерфейса в классе:</span><span class="sxs-lookup"><span data-stu-id="d0c10-241">To implement an interface in a class:</span></span>

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.doSomething()
    {
        // Method implementation.
    }
}
```

<span data-ttu-id="d0c10-242">Дополнительные сведения см. в разделе руководства по программированию, посвященного [интерфейсам](../interfaces/index.md), и в статье справочника по языку, посвященной ключевому слову [interface](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="d0c10-242">For more information, see the programming guide article on [Interfaces](../interfaces/index.md) and the language reference article on the [interface](../../language-reference/keywords/interface.md) keyword.</span></span>

## <a name="generics"></a><span data-ttu-id="d0c10-243">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="d0c10-243">Generics</span></span>

<span data-ttu-id="d0c10-244">Классы, структуры, интерфейсы и методы в платформе .NET Framework могут иметь *параметры типа*, которые определяют типы объектов, которые они могут хранить или использовать.</span><span class="sxs-lookup"><span data-stu-id="d0c10-244">Classes, structures, interfaces and methods in the .NET Framework can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="d0c10-245">Наиболее распространенным примером универсального шаблона является коллекция, в которой можно указать тип объектов, которые могут в ней храниться.</span><span class="sxs-lookup"><span data-stu-id="d0c10-245">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="d0c10-246">Определение универсального класса:</span><span class="sxs-lookup"><span data-stu-id="d0c10-246">To define a generic class:</span></span>

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

<span data-ttu-id="d0c10-247">Создание экземпляра универсального класса:</span><span class="sxs-lookup"><span data-stu-id="d0c10-247">To create an instance of a generic class:</span></span>

```csharp
SampleGeneric<string> sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

<span data-ttu-id="d0c10-248">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="d0c10-248">For more information, see:</span></span>

- [<span data-ttu-id="d0c10-249">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="d0c10-249">Generics</span></span>](../../../standard/generics/index.md)

- [<span data-ttu-id="d0c10-250">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="d0c10-250">Generics</span></span>](../generics/index.md)

## <a name="delegates"></a><span data-ttu-id="d0c10-251">Делегаты</span><span class="sxs-lookup"><span data-stu-id="d0c10-251">Delegates</span></span>

<span data-ttu-id="d0c10-252">*Делегат* — это тип, который определяет сигнатуру метода и может обеспечивать связь с любым методом с совместимой сигнатурой.</span><span class="sxs-lookup"><span data-stu-id="d0c10-252">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="d0c10-253">Метод можно запустить (или вызвать) с помощью делегата.</span><span class="sxs-lookup"><span data-stu-id="d0c10-253">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="d0c10-254">Делегаты используются для передачи методов в качестве аргументов к другим методам.</span><span class="sxs-lookup"><span data-stu-id="d0c10-254">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="d0c10-255">Обработчики событий — это ничто иное, как методы, вызываемые с помощью делегатов.</span><span class="sxs-lookup"><span data-stu-id="d0c10-255">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="d0c10-256">Дополнительные сведения об использовании делегатов при обработке событий см. в разделе [События](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="d0c10-256">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="d0c10-257">Создание делегата:</span><span class="sxs-lookup"><span data-stu-id="d0c10-257">To create a delegate:</span></span>

```csharp
public delegate void SampleDelegate(string str);
```

<span data-ttu-id="d0c10-258">Создание ссылки на метод, сигнатура которого соответствует сигнатуре, указанной делегатом:</span><span class="sxs-lookup"><span data-stu-id="d0c10-258">To create a reference to a method that matches the signature specified by the delegate:</span></span>

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

<span data-ttu-id="d0c10-259">Дополнительные сведения см. в разделе руководства по программированию, посвященного [делегатам](../delegates/index.md), и в статье справочника по языку, посвященной ключевому слову [delegate](../../language-reference/builtin-types/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="d0c10-259">For more information, see the programming guide article on [Delegates](../delegates/index.md) and the language reference article on the [delegate](../../language-reference/builtin-types/reference-types.md) keyword.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0c10-260">См. также</span><span class="sxs-lookup"><span data-stu-id="d0c10-260">See also</span></span>

- [<span data-ttu-id="d0c10-261">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d0c10-261">C# Programming Guide</span></span>](../index.md)
