---
title: Объектно ориентированного программирования (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 49794de4-64c3-473c-b8ed-fe98835df69c
ms.openlocfilehash: 058d8b932e50f784d4a5cefa9fadfb31953687f0
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153934"
---
# <a name="object-oriented-programming-visual-basic"></a><span data-ttu-id="f28dd-102">Объектно ориентированного программирования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f28dd-102">Object-oriented programming (Visual Basic)</span></span>

<span data-ttu-id="f28dd-103">Visual Basic предоставляет полную поддержку объектно ориентированного программирования, включая инкапсуляцию, наследование и полиморфизм.</span><span class="sxs-lookup"><span data-stu-id="f28dd-103">Visual Basic provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

 <span data-ttu-id="f28dd-104">*Инкапсуляция* означает, что группа связанных свойств, методов и других членов рассматривается как единый элемент или объект.</span><span class="sxs-lookup"><span data-stu-id="f28dd-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>

 <span data-ttu-id="f28dd-105">*Наследование* описывает возможность создания новых классов на основе существующих классов.</span><span class="sxs-lookup"><span data-stu-id="f28dd-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>

 <span data-ttu-id="f28dd-106">*Полиморфизм* означает, что можно иметь несколько взаимозаменяемых классов, даже если каждый класс реализует одни и те же свойства или методы разными способами.</span><span class="sxs-lookup"><span data-stu-id="f28dd-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

 <span data-ttu-id="f28dd-107">В этом разделе рассматриваются следующие понятия.</span><span class="sxs-lookup"><span data-stu-id="f28dd-107">This section describes the following concepts:</span></span>

- [<span data-ttu-id="f28dd-108">Классы и объекты</span><span class="sxs-lookup"><span data-stu-id="f28dd-108">Classes and objects</span></span>](#classes-and-objects)
  - [<span data-ttu-id="f28dd-109">Члены класса</span><span class="sxs-lookup"><span data-stu-id="f28dd-109">Class members</span></span>](#class-members)
    - [<span data-ttu-id="f28dd-110">Свойства и поля</span><span class="sxs-lookup"><span data-stu-id="f28dd-110">Properties and fields</span></span>](#properties-and-fields)
    - [<span data-ttu-id="f28dd-111">Методы</span><span class="sxs-lookup"><span data-stu-id="f28dd-111">Methods</span></span>](#methods)
    - [<span data-ttu-id="f28dd-112">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="f28dd-112">Constructors</span></span>](#constructors)
    - [<span data-ttu-id="f28dd-113">Деструкторы</span><span class="sxs-lookup"><span data-stu-id="f28dd-113">Destructors</span></span>](#destructors)
    - [<span data-ttu-id="f28dd-114">События</span><span class="sxs-lookup"><span data-stu-id="f28dd-114">Events</span></span>](#events)
    - [<span data-ttu-id="f28dd-115">Вложенные классы</span><span class="sxs-lookup"><span data-stu-id="f28dd-115">Nested classes</span></span>](#nested-classes)
  - [<span data-ttu-id="f28dd-116">Модификаторы доступа и уровни доступа</span><span class="sxs-lookup"><span data-stu-id="f28dd-116">Access modifiers and access levels</span></span>](#access-modifiers-and-access-levels)
    - [<span data-ttu-id="f28dd-117">Создание экземпляров классов</span><span class="sxs-lookup"><span data-stu-id="f28dd-117">Instantiating classes</span></span>](#instantiating-classes)
    - [<span data-ttu-id="f28dd-118">Общие классы и члены</span><span class="sxs-lookup"><span data-stu-id="f28dd-118">Shared classes and members</span></span>](#shared-classes-and-members)
    - [<span data-ttu-id="f28dd-119">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="f28dd-119">Anonymous types</span></span>](#anonymous-types)
- [<span data-ttu-id="f28dd-120">Наследование</span><span class="sxs-lookup"><span data-stu-id="f28dd-120">Inheritance</span></span>](#inheritance)
  - [<span data-ttu-id="f28dd-121">Переопределение членов</span><span class="sxs-lookup"><span data-stu-id="f28dd-121">Overriding members</span></span>](#overriding-members)
- [<span data-ttu-id="f28dd-122">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="f28dd-122">Interfaces</span></span>](#interfaces)
- [<span data-ttu-id="f28dd-123">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="f28dd-123">Generics</span></span>](#generics)
- [<span data-ttu-id="f28dd-124">Делегаты</span><span class="sxs-lookup"><span data-stu-id="f28dd-124">Delegates</span></span>](#delegates)

## <a name="classes-and-objects"></a><span data-ttu-id="f28dd-125">Классы и объекты</span><span class="sxs-lookup"><span data-stu-id="f28dd-125">Classes and objects</span></span>

<span data-ttu-id="f28dd-126">Термины *класс* и *объект* часто взаимозаменяемы, но в действительности классы описывают *типы* объектов, а объекты — это используемые *экземпляры* классов.</span><span class="sxs-lookup"><span data-stu-id="f28dd-126">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="f28dd-127">Поэтому процесс создания объекта называется *созданием экземпляра*.</span><span class="sxs-lookup"><span data-stu-id="f28dd-127">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="f28dd-128">Если использовать сравнение с чертежом, то класс является чертежом, а объект является зданием, построенным по нему.</span><span class="sxs-lookup"><span data-stu-id="f28dd-128">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="f28dd-129">Определение класса:</span><span class="sxs-lookup"><span data-stu-id="f28dd-129">To define a class:</span></span>

```vb
Class SampleClass
End Class
```

<span data-ttu-id="f28dd-130">Visual Basic также предоставляет облегченную версию классов — *структуры* , полезны, когда необходимо создать большой массив объектов и выполнять не требуется слишком много памяти.</span><span class="sxs-lookup"><span data-stu-id="f28dd-130">Visual Basic also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>

<span data-ttu-id="f28dd-131">Определение структуры:</span><span class="sxs-lookup"><span data-stu-id="f28dd-131">To define a structure:</span></span>

```vb
Structure SampleStructure
End Structure
```

<span data-ttu-id="f28dd-132">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="f28dd-132">For more information, see:</span></span>

- [<span data-ttu-id="f28dd-133">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="f28dd-133">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="f28dd-134">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="f28dd-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)

### <a name="class-members"></a><span data-ttu-id="f28dd-135">Члены класса</span><span class="sxs-lookup"><span data-stu-id="f28dd-135">Class members</span></span>

<span data-ttu-id="f28dd-136">Каждый класс может состоять из различных *членов класса*, которые содержат свойства, описывающие данные класса, методы, задающие поведение класса, и события, обеспечивающие связь между различными классами и объектами.</span><span class="sxs-lookup"><span data-stu-id="f28dd-136">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="f28dd-137">Свойства и поля</span><span class="sxs-lookup"><span data-stu-id="f28dd-137">Properties and fields</span></span>

<span data-ttu-id="f28dd-138">Поля и свойства представляют сведения, содержащиеся в объекте.</span><span class="sxs-lookup"><span data-stu-id="f28dd-138">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="f28dd-139">Поля подобны переменным в том, что их можно прочитать или изменить напрямую.</span><span class="sxs-lookup"><span data-stu-id="f28dd-139">Fields are like variables because they can be read or set directly.</span></span>

<span data-ttu-id="f28dd-140">Определение поля:</span><span class="sxs-lookup"><span data-stu-id="f28dd-140">To define a field:</span></span>

```vb
Class SampleClass
    Public SampleField As String
End Class
```

<span data-ttu-id="f28dd-141">Для работы со свойствами используются процедуры "Get" и "Set", которые расширяют возможности управления способом задания и возврата значений.</span><span class="sxs-lookup"><span data-stu-id="f28dd-141">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="f28dd-142">Visual Basic можно создать частное поле для хранения значения свойства или использовать так называемые автоматически реализуемые свойства, которые создают это поле автоматически в фоновом и обеспечивают базовую логику для процедур свойств.</span><span class="sxs-lookup"><span data-stu-id="f28dd-142">Visual Basic allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="f28dd-143">Определение автоматически реализуемого свойства:</span><span class="sxs-lookup"><span data-stu-id="f28dd-143">To define an auto-implemented property:</span></span>

```vb
Class SampleClass
    Public Property SampleProperty as String
End Class
```

<span data-ttu-id="f28dd-144">Если требуется выполнить дополнительные операции чтения и записи применительно к значению свойства, определите поле для хранения значения свойства и затем реализуйте базовую логику для хранения и извлечения этого значения:</span><span class="sxs-lookup"><span data-stu-id="f28dd-144">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

```vb
Class SampleClass
    Private m_Sample As String
    Public Property Sample() As String
        Get
            ' Return the value stored in the field.
            Return m_Sample
        End Get
        Set(ByVal Value As String)
            ' Store the value in the field.
            m_Sample = Value
        End Set
    End Property
End Class
```

<span data-ttu-id="f28dd-145">У большинства свойств есть методы или процедуры для задания и возврата значения свойства.</span><span class="sxs-lookup"><span data-stu-id="f28dd-145">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="f28dd-146">Однако можно создать свойства, доступные только для чтения или только на запись, чтобы запретить изменение или чтение значений свойств.</span><span class="sxs-lookup"><span data-stu-id="f28dd-146">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="f28dd-147">Для этого в Visual Basic можно использовать ключевые слова `ReadOnly` и `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="f28dd-147">In Visual Basic you can use `ReadOnly` and `WriteOnly` keywords.</span></span> <span data-ttu-id="f28dd-148">Следует отметить, что автоматически реализуемые свойства нельзя сделать доступными только для чтения или только для записи.</span><span class="sxs-lookup"><span data-stu-id="f28dd-148">However, auto-implemented properties cannot be read-only or write-only.</span></span>

<span data-ttu-id="f28dd-149">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="f28dd-149">For more information, see:</span></span>

- [<span data-ttu-id="f28dd-150">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="f28dd-150">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="f28dd-151">Оператор Get</span><span class="sxs-lookup"><span data-stu-id="f28dd-151">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="f28dd-152">Оператор Set</span><span class="sxs-lookup"><span data-stu-id="f28dd-152">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="f28dd-153">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="f28dd-153">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="f28dd-154">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="f28dd-154">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)

#### <a name="methods"></a><span data-ttu-id="f28dd-155">Методы</span><span class="sxs-lookup"><span data-stu-id="f28dd-155">Methods</span></span>

 <span data-ttu-id="f28dd-156">Действие, которое выполняет объект, называется *методом*.</span><span class="sxs-lookup"><span data-stu-id="f28dd-156">A *method* is an action that an object can perform.</span></span>

> [!NOTE]
> <span data-ttu-id="f28dd-157">В Visual Basic существует два способа создания метода: с помощью оператора `Sub` (если метод не возвращает значение) или с помощью оператора `Function` (если метод возвращает значение).</span><span class="sxs-lookup"><span data-stu-id="f28dd-157">In Visual Basic, there are two ways to create a method: the `Sub` statement is used if the method does not return a value; the `Function` statement is used if a method returns a value.</span></span>

<span data-ttu-id="f28dd-158">Определение метода класса:</span><span class="sxs-lookup"><span data-stu-id="f28dd-158">To define a method of a class:</span></span>

```vb
Class SampleClass
    Public Function SampleFunc(ByVal SampleParam As String)
        ' Add code here
    End Function
End Class
```

<span data-ttu-id="f28dd-159">Класс может иметь несколько реализаций или *перегрузок* одного и того же метода, которые отличаются от других числом или типами параметров.</span><span class="sxs-lookup"><span data-stu-id="f28dd-159">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="f28dd-160">Перегрузка метода:</span><span class="sxs-lookup"><span data-stu-id="f28dd-160">To overload a method:</span></span>

```vb
Overloads Sub Display(ByVal theChar As Char)
    ' Add code that displays Char data.
End Sub
Overloads Sub Display(ByVal theInteger As Integer)
    ' Add code that displays Integer data.
End Sub
```

<span data-ttu-id="f28dd-161">Как правило, метод объявляется при определении класса.</span><span class="sxs-lookup"><span data-stu-id="f28dd-161">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="f28dd-162">Тем не менее, Visual Basic также поддерживает *методы расширения* , которые позволяют добавлять методы в существующий класс вне определения класса.</span><span class="sxs-lookup"><span data-stu-id="f28dd-162">However, Visual Basic also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="f28dd-163">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="f28dd-163">For more information, see:</span></span>

- [<span data-ttu-id="f28dd-164">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="f28dd-164">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="f28dd-165">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="f28dd-165">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="f28dd-166">Перегрузки</span><span class="sxs-lookup"><span data-stu-id="f28dd-166">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="f28dd-167">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="f28dd-167">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)

#### <a name="constructors"></a><span data-ttu-id="f28dd-168">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="f28dd-168">Constructors</span></span>

<span data-ttu-id="f28dd-169">Конструкторы — это методы классов, выполняемые автоматически при создании объекта заданного типа.</span><span class="sxs-lookup"><span data-stu-id="f28dd-169">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="f28dd-170">Обычно конструкторы выполняют инициализацию членов данных нового объекта.</span><span class="sxs-lookup"><span data-stu-id="f28dd-170">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="f28dd-171">Конструктор можно запустить только один раз при создании класса.</span><span class="sxs-lookup"><span data-stu-id="f28dd-171">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="f28dd-172">Кроме того, код конструктора всегда выполняется раньше всех остальных частей кода в классе.</span><span class="sxs-lookup"><span data-stu-id="f28dd-172">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="f28dd-173">Следует отметить, что так же, как и для других методов, можно создать несколько перегрузок конструктора.</span><span class="sxs-lookup"><span data-stu-id="f28dd-173">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="f28dd-174">Определение конструктора для класса:</span><span class="sxs-lookup"><span data-stu-id="f28dd-174">To define a constructor for a class:</span></span>

```vb
Class SampleClass
    Sub New(ByVal s As String)
        // Add code here.
    End Sub
End Class
```

<span data-ttu-id="f28dd-175">Дополнительные сведения: [Время существования: Как создаются и удаляются объекты](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="f28dd-175">For more information, see: [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

#### <a name="destructors"></a><span data-ttu-id="f28dd-176">Деструкторы</span><span class="sxs-lookup"><span data-stu-id="f28dd-176">Destructors</span></span>

<span data-ttu-id="f28dd-177">Деструкторы используются для уничтожения экземпляров классов.</span><span class="sxs-lookup"><span data-stu-id="f28dd-177">Destructors are used to destruct instances of classes.</span></span> <span data-ttu-id="f28dd-178">В платформе .NET Framework сборщик мусора автоматически управляет распределением и освобождением памяти для управляемых объектов приложения.</span><span class="sxs-lookup"><span data-stu-id="f28dd-178">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="f28dd-179">Однако для очистки неуправляемых ресурсов, создаваемых приложением, могут потребоваться деструкторы.</span><span class="sxs-lookup"><span data-stu-id="f28dd-179">However, you may still need destructors to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="f28dd-180">На один класс допускается только один деструктор.</span><span class="sxs-lookup"><span data-stu-id="f28dd-180">There can be only one destructor for a class.</span></span>

<span data-ttu-id="f28dd-181">Дополнительные сведения о деструкторах и сборке мусора в .NET Framework см. в разделе [Сборка мусора](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="f28dd-181">For more information about destructors and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="f28dd-182">События</span><span class="sxs-lookup"><span data-stu-id="f28dd-182">Events</span></span>

<span data-ttu-id="f28dd-183">События позволяют классу или объекту уведомлять другие классы или объекты о возникновении каких-либо ситуаций.</span><span class="sxs-lookup"><span data-stu-id="f28dd-183">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="f28dd-184">Класс, отправляющий (или порождающий) событие, называется *издателем*, а классы, принимающие (или обрабатывающие) событие, называются *подписчиками*.</span><span class="sxs-lookup"><span data-stu-id="f28dd-184">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="f28dd-185">Дополнительные сведения о том, как порождаются и обрабатываются события, см. в разделе [События](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="f28dd-185">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="f28dd-186">Чтобы объявлять события, используйте [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f28dd-186">To declare events, use the [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>

- <span data-ttu-id="f28dd-187">Чтобы порождать события, используйте [оператор RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f28dd-187">To raise events, use the [RaiseEvent Statement](../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>

- <span data-ttu-id="f28dd-188">Чтобы указать обработчики событий декларативным способом, используйте [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) инструкции и [обрабатывает](../../../visual-basic/language-reference/statements/handles-clause.md) предложение.</span><span class="sxs-lookup"><span data-stu-id="f28dd-188">To specify event handlers using a declarative way, use the [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) statement and the [Handles](../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span>

- <span data-ttu-id="f28dd-189">Чтобы иметь возможность динамически добавлять, удалять и изменять обработчик событий, связанный с событием, используйте [оператор AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md) и [оператор RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md) вместе с [AddressOf Оператор](../../../visual-basic/language-reference/operators/addressof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="f28dd-189">To be able to dynamically add, remove, and change the event handler associated with an event, use the [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md) and [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) together with the [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md).</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="f28dd-190">Вложенные классы</span><span class="sxs-lookup"><span data-stu-id="f28dd-190">Nested classes</span></span>

<span data-ttu-id="f28dd-191">Класс, определенный внутри другого класса, называется *вложенным*.</span><span class="sxs-lookup"><span data-stu-id="f28dd-191">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="f28dd-192">По умолчанию вложенный класс является частным.</span><span class="sxs-lookup"><span data-stu-id="f28dd-192">By default, the nested class is private.</span></span>

```vb
Class Container
    Class Nested
    ' Add code here.
    End Class
End Class
```

<span data-ttu-id="f28dd-193">Чтобы создать экземпляр вложенного класса, укажите имя класса контейнера и имя вложенного класса, используя в качестве разделителя точку:</span><span class="sxs-lookup"><span data-stu-id="f28dd-193">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```vb
Dim nestedInstance As Container.Nested = New Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="f28dd-194">Модификаторы доступа и уровни доступа</span><span class="sxs-lookup"><span data-stu-id="f28dd-194">Access modifiers and access levels</span></span>

<span data-ttu-id="f28dd-195">С помощью *модификаторов доступа* все классы и члены классов могут указывать уровни доступа, предоставляемые другим классам.</span><span class="sxs-lookup"><span data-stu-id="f28dd-195">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="f28dd-196">Имеющиеся модификаторы доступа указаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f28dd-196">The following access modifiers are available:</span></span>

|<span data-ttu-id="f28dd-197">Модификатор Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f28dd-197">Visual Basic Modifier</span></span>|<span data-ttu-id="f28dd-198">Определение</span><span class="sxs-lookup"><span data-stu-id="f28dd-198">Definition</span></span>|
|---------------------------|----------------|
|[<span data-ttu-id="f28dd-199">Public</span><span class="sxs-lookup"><span data-stu-id="f28dd-199">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)|<span data-ttu-id="f28dd-200">Доступ к типу или члену возможен из любого другого кода в той же сборке или другой сборке, ссылающейся на него.</span><span class="sxs-lookup"><span data-stu-id="f28dd-200">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="f28dd-201">Закрытые</span><span class="sxs-lookup"><span data-stu-id="f28dd-201">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)|<span data-ttu-id="f28dd-202">Доступ к типу или члену можно получить только из кода в том же классе.</span><span class="sxs-lookup"><span data-stu-id="f28dd-202">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="f28dd-203">Protected</span><span class="sxs-lookup"><span data-stu-id="f28dd-203">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)|<span data-ttu-id="f28dd-204">Доступ к типу или члену можно получить только из кода в том же классе или в производном классе.</span><span class="sxs-lookup"><span data-stu-id="f28dd-204">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="f28dd-205">Friend</span><span class="sxs-lookup"><span data-stu-id="f28dd-205">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)|<span data-ttu-id="f28dd-206">Доступ к типу или члену возможен из любого кода в той же сборке, но не из другой сборки.</span><span class="sxs-lookup"><span data-stu-id="f28dd-206">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|`Protected Friend`|<span data-ttu-id="f28dd-207">Доступ к типу или члену возможен из любого кода в той же сборке, или из производного класса в другой сборке.</span><span class="sxs-lookup"><span data-stu-id="f28dd-207">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|

<span data-ttu-id="f28dd-208">Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f28dd-208">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="f28dd-209">Создание экземпляров классов</span><span class="sxs-lookup"><span data-stu-id="f28dd-209">Instantiating classes</span></span>

<span data-ttu-id="f28dd-210">Чтобы создать объект, необходимо создать экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="f28dd-210">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```vb
Dim sampleObject as New SampleClass()
```

<span data-ttu-id="f28dd-211">После создания экземпляра класса можно присваивать значения свойствам и полям экземпляра и вызывать методы класса.</span><span class="sxs-lookup"><span data-stu-id="f28dd-211">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```vb
' Set a property value.
sampleObject.SampleProperty = "Sample String"
' Call a method.
sampleObject.SampleMethod()
```

<span data-ttu-id="f28dd-212">Чтобы назначить значения свойствам в процессе создания экземпляра класса, используйте инициализаторы объектов:</span><span class="sxs-lookup"><span data-stu-id="f28dd-212">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```vb
Dim sampleObject = New SampleClass With
    {.FirstProperty = "A", .SecondProperty = "B"}
```

<span data-ttu-id="f28dd-213">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="f28dd-213">For more information, see:</span></span>

- [<span data-ttu-id="f28dd-214">Оператор New</span><span class="sxs-lookup"><span data-stu-id="f28dd-214">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="f28dd-215">Инициализаторы объектов. Именованные и анонимные типы</span><span class="sxs-lookup"><span data-stu-id="f28dd-215">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)

### <a name="shared-classes-and-members"></a><span data-ttu-id="f28dd-216">Общие классы и члены</span><span class="sxs-lookup"><span data-stu-id="f28dd-216">Shared classes and members</span></span>

 <span data-ttu-id="f28dd-217">Общий член класса — это свойство, процедура или поле, которое совместно используется всеми экземплярами класса.</span><span class="sxs-lookup"><span data-stu-id="f28dd-217">A shared member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

 <span data-ttu-id="f28dd-218">Для определения общего элемента:</span><span class="sxs-lookup"><span data-stu-id="f28dd-218">To define a shared member:</span></span>

```vb
Class SampleClass
    Public Shared SampleString As String = "Sample String"
End Class
```

 <span data-ttu-id="f28dd-219">Чтобы получить доступ к общему члену, используйте имя класса без создания объекта этого класса:</span><span class="sxs-lookup"><span data-stu-id="f28dd-219">To access the shared member, use the name of the class without creating an object of this class:</span></span>

```vb
MsgBox(SampleClass.SampleString)
```

 <span data-ttu-id="f28dd-220">Общих модулей в Visual Basic отправили только элементы и не может быть создан.</span><span class="sxs-lookup"><span data-stu-id="f28dd-220">Shared modules in Visual Basic have shared members only and cannot be instantiated.</span></span> <span data-ttu-id="f28dd-221">Общие члены также не может получить доступ к свойства, которые не являются общими, полям или методам</span><span class="sxs-lookup"><span data-stu-id="f28dd-221">Shared members also cannot access non-shared properties, fields or methods</span></span>

 <span data-ttu-id="f28dd-222">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="f28dd-222">For more information, see:</span></span>

- [<span data-ttu-id="f28dd-223">Общие</span><span class="sxs-lookup"><span data-stu-id="f28dd-223">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="f28dd-224">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="f28dd-224">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)

### <a name="anonymous-types"></a><span data-ttu-id="f28dd-225">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="f28dd-225">Anonymous types</span></span>

<span data-ttu-id="f28dd-226">Анонимные типы позволяют создавать объекты без написания определения класса для типа данных.</span><span class="sxs-lookup"><span data-stu-id="f28dd-226">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="f28dd-227">Вместо этого компилятор создает класс для вас.</span><span class="sxs-lookup"><span data-stu-id="f28dd-227">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="f28dd-228">Данный класс не имеет имени и содержит свойства, которые указаны при объявлении объекта.</span><span class="sxs-lookup"><span data-stu-id="f28dd-228">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="f28dd-229">Создание экземпляра анонимного типа:</span><span class="sxs-lookup"><span data-stu-id="f28dd-229">To create an instance of an anonymous type:</span></span>

```vb
' sampleObject is an instance of a simple anonymous type.
Dim sampleObject =
    New With {Key .FirstProperty = "A", .SecondProperty = "B"}
```

<span data-ttu-id="f28dd-230">Дополнительные сведения: [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="f28dd-230">For more information, see: [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="f28dd-231">Наследование</span><span class="sxs-lookup"><span data-stu-id="f28dd-231">Inheritance</span></span>

<span data-ttu-id="f28dd-232">Наследование позволяет создавать новые классы, которые повторно используют, расширяют и изменяют поведение, определенное в другом классе.</span><span class="sxs-lookup"><span data-stu-id="f28dd-232">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="f28dd-233">Класс, члены которого наследуются, называется *базовым классом*, а класс, который наследует эти члены, называется *производным классом*.</span><span class="sxs-lookup"><span data-stu-id="f28dd-233">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="f28dd-234">Тем не менее, все классы в Visual Basic неявно наследуются от <xref:System.Object> класс, который поддерживает иерархию классов .NET и предоставляет низкоуровневые службы для всех классов.</span><span class="sxs-lookup"><span data-stu-id="f28dd-234">However, all classes in Visual Basic implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="f28dd-235">Visual Basic не поддерживает множественное наследование.</span><span class="sxs-lookup"><span data-stu-id="f28dd-235">Visual Basic doesn't support multiple inheritance.</span></span> <span data-ttu-id="f28dd-236">То есть можно указать только один базовый класс для производного класса.</span><span class="sxs-lookup"><span data-stu-id="f28dd-236">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="f28dd-237">Наследование от базового класса:</span><span class="sxs-lookup"><span data-stu-id="f28dd-237">To inherit from a base class:</span></span>

```vb
Class DerivedClass
    Inherits BaseClass
End Class
```

<span data-ttu-id="f28dd-238">По умолчанию унаследовать класс можно от любого класса.</span><span class="sxs-lookup"><span data-stu-id="f28dd-238">By default all classes can be inherited.</span></span> <span data-ttu-id="f28dd-239">Однако можно указать, должен ли класс использоваться в качестве базового класса, или создать класс, который может использоваться только в качестве базового.</span><span class="sxs-lookup"><span data-stu-id="f28dd-239">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="f28dd-240">Указание, что класс не может использоваться в качестве базового класса:</span><span class="sxs-lookup"><span data-stu-id="f28dd-240">To specify that a class cannot be used as a base class:</span></span>

```vb
NotInheritable Class SampleClass
End Class
```

<span data-ttu-id="f28dd-241">Указание, что класс может использоваться только в качестве базового класса и нельзя создать экземпляр этого класса:</span><span class="sxs-lookup"><span data-stu-id="f28dd-241">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```vb
MustInherit Class BaseClass
End Class
```

<span data-ttu-id="f28dd-242">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="f28dd-242">For more information, see:</span></span>

- [<span data-ttu-id="f28dd-243">Оператор Inherits</span><span class="sxs-lookup"><span data-stu-id="f28dd-243">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="f28dd-244">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="f28dd-244">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="f28dd-245">MustInherit</span><span class="sxs-lookup"><span data-stu-id="f28dd-245">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)

### <a name="overriding-members"></a><span data-ttu-id="f28dd-246">Переопределение членов</span><span class="sxs-lookup"><span data-stu-id="f28dd-246">Overriding members</span></span>

<span data-ttu-id="f28dd-247">По умолчанию производный класс наследует все члены от своего базового класса.</span><span class="sxs-lookup"><span data-stu-id="f28dd-247">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="f28dd-248">Если необходимо изменить поведение унаследованного члена, необходимо переопределить его.</span><span class="sxs-lookup"><span data-stu-id="f28dd-248">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="f28dd-249">Т. е. в производном классе можно определить новую реализацию метода, свойства или события.</span><span class="sxs-lookup"><span data-stu-id="f28dd-249">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="f28dd-250">Следующие модификаторы используются для управления переопределением свойств и методов.</span><span class="sxs-lookup"><span data-stu-id="f28dd-250">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="f28dd-251">Модификатор Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f28dd-251">Visual Basic Modifier</span></span>|<span data-ttu-id="f28dd-252">Определение</span><span class="sxs-lookup"><span data-stu-id="f28dd-252">Definition</span></span>|
|---------------------------|----------------|
|[<span data-ttu-id="f28dd-253">Переопределяемые</span><span class="sxs-lookup"><span data-stu-id="f28dd-253">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)|<span data-ttu-id="f28dd-254">Разрешает переопределение члена класса в производном классе.</span><span class="sxs-lookup"><span data-stu-id="f28dd-254">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="f28dd-255">Переопределения</span><span class="sxs-lookup"><span data-stu-id="f28dd-255">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)|<span data-ttu-id="f28dd-256">Переопределяет виртуальный (переопределяемый) член в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="f28dd-256">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="f28dd-257">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="f28dd-257">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)|<span data-ttu-id="f28dd-258">Запрещает переопределение члена в наследующем классе.</span><span class="sxs-lookup"><span data-stu-id="f28dd-258">Prevents a member from being overridden in an inheriting class.</span></span>|
|[<span data-ttu-id="f28dd-259">MustOverride</span><span class="sxs-lookup"><span data-stu-id="f28dd-259">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)|<span data-ttu-id="f28dd-260">Требует, чтобы член класса был переопределен в производном классе.</span><span class="sxs-lookup"><span data-stu-id="f28dd-260">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="f28dd-261">Shadows</span><span class="sxs-lookup"><span data-stu-id="f28dd-261">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)|<span data-ttu-id="f28dd-262">Скрывает член, наследуемый от базового класса</span><span class="sxs-lookup"><span data-stu-id="f28dd-262">Hides a member inherited from a base class</span></span>|

## <a name="interfaces"></a><span data-ttu-id="f28dd-263">интерфейсов,</span><span class="sxs-lookup"><span data-stu-id="f28dd-263">Interfaces</span></span>

<span data-ttu-id="f28dd-264">Интерфейсы, как и классы, определяют набор свойств, методов и событий.</span><span class="sxs-lookup"><span data-stu-id="f28dd-264">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="f28dd-265">Но, в отличие от классов, интерфейсы не предоставляют реализацию.</span><span class="sxs-lookup"><span data-stu-id="f28dd-265">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="f28dd-266">Они реализуются классами, но определяются как отдельные от классов сущности.</span><span class="sxs-lookup"><span data-stu-id="f28dd-266">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="f28dd-267">Интерфейс представляет собой контракт, в котором класс, реализующий интерфейс, должен реализовывать каждый аспект этого интерфейса в точном соответствии с его определением.</span><span class="sxs-lookup"><span data-stu-id="f28dd-267">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="f28dd-268">Определение интерфейса:</span><span class="sxs-lookup"><span data-stu-id="f28dd-268">To define an interface:</span></span>

```vb
Public Interface ISampleInterface
    Sub DoSomething()
End Interface
```

<span data-ttu-id="f28dd-269">Реализация интерфейса в классе:</span><span class="sxs-lookup"><span data-stu-id="f28dd-269">To implement an interface in a class:</span></span>

```vb
Class SampleClass
    Implements ISampleInterface
    Sub DoSomething
        ' Method implementation.
    End Sub
End Class
```

<span data-ttu-id="f28dd-270">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="f28dd-270">For more information, see:</span></span>

- [<span data-ttu-id="f28dd-271">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="f28dd-271">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [<span data-ttu-id="f28dd-272">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="f28dd-272">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="f28dd-273">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="f28dd-273">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)

## <a name="generics"></a><span data-ttu-id="f28dd-274">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="f28dd-274">Generics</span></span>

<span data-ttu-id="f28dd-275">Классы, структуры, интерфейсы и методы в .NET можно включить *параметры типа* , которые определяют типы объектов, которые они могут хранить или использовать.</span><span class="sxs-lookup"><span data-stu-id="f28dd-275">Classes, structures, interfaces and methods in .NET can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="f28dd-276">Наиболее распространенным примером универсального шаблона является коллекция, в которой можно указать тип объектов, которые могут в ней храниться.</span><span class="sxs-lookup"><span data-stu-id="f28dd-276">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="f28dd-277">Определение универсального класса:</span><span class="sxs-lookup"><span data-stu-id="f28dd-277">To define a generic class:</span></span>

```vb
Class SampleGeneric(Of T)
    Public Field As T
End Class
```

<span data-ttu-id="f28dd-278">Создание экземпляра универсального класса:</span><span class="sxs-lookup"><span data-stu-id="f28dd-278">To create an instance of a generic class:</span></span>

```vb
Dim sampleObject As New SampleGeneric(Of String)
sampleObject.Field = "Sample string"
```

<span data-ttu-id="f28dd-279">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="f28dd-279">For more information, see:</span></span>

- [<span data-ttu-id="f28dd-280">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="f28dd-280">Generics</span></span>](../../../standard/generics/index.md)
- [<span data-ttu-id="f28dd-281">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f28dd-281">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)

## <a name="delegates"></a><span data-ttu-id="f28dd-282">Делегаты</span><span class="sxs-lookup"><span data-stu-id="f28dd-282">Delegates</span></span>

 <span data-ttu-id="f28dd-283">*Делегат* — это тип, который определяет сигнатуру метода и может обеспечивать связь с любым методом с совместимой сигнатурой.</span><span class="sxs-lookup"><span data-stu-id="f28dd-283">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="f28dd-284">Метод можно запустить (или вызвать) с помощью делегата.</span><span class="sxs-lookup"><span data-stu-id="f28dd-284">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="f28dd-285">Делегаты используются для передачи методов в качестве аргументов к другим методам.</span><span class="sxs-lookup"><span data-stu-id="f28dd-285">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="f28dd-286">Обработчики событий — это ничто иное, как методы, вызываемые с помощью делегатов.</span><span class="sxs-lookup"><span data-stu-id="f28dd-286">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="f28dd-287">Дополнительные сведения об использовании делегатов при обработке событий см. в разделе [События](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="f28dd-287">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="f28dd-288">Создание делегата:</span><span class="sxs-lookup"><span data-stu-id="f28dd-288">To create a delegate:</span></span>

```vb
Delegate Sub SampleDelegate(ByVal str As String)
```

<span data-ttu-id="f28dd-289">Создание ссылки на метод, сигнатура которого соответствует сигнатуре, указанной делегатом:</span><span class="sxs-lookup"><span data-stu-id="f28dd-289">To create a reference to a method that matches the signature specified by the delegate:</span></span>

```vb
Class SampleClass
    ' Method that matches the SampleDelegate signature.
    Sub SampleSub(ByVal str As String)
        ' Add code here.
    End Sub
    ' Method that instantiates the delegate.
    Sub SampleDelegateSub()
        Dim sd As SampleDelegate = AddressOf SampleSub
        sd("Sample string")
    End Sub
End Class
```

<span data-ttu-id="f28dd-290">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="f28dd-290">For more information, see:</span></span>

- [<span data-ttu-id="f28dd-291">Делегаты</span><span class="sxs-lookup"><span data-stu-id="f28dd-291">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="f28dd-292">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="f28dd-292">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="f28dd-293">Оператор AddressOf</span><span class="sxs-lookup"><span data-stu-id="f28dd-293">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)

## <a name="see-also"></a><span data-ttu-id="f28dd-294">См. также</span><span class="sxs-lookup"><span data-stu-id="f28dd-294">See also</span></span>

- [<span data-ttu-id="f28dd-295">Руководство по программированию на Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f28dd-295">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
