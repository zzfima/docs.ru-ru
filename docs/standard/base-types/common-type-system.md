---
title: "Система общих типов CTS"
description: "Система общих типов CTS"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: b5482a1d-7bdc-40fe-aa45-10df930ceb5b
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 6be672acc84a76106e25b82574acad16beb4a8ac
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="common-type-system-in-depth"></a><span data-ttu-id="144a4-104">Система общих типов CTS</span><span class="sxs-lookup"><span data-stu-id="144a4-104">Common type system in depth</span></span>

<span data-ttu-id="144a4-105">В этом разделе содержатся следующие подразделы с подробным описанием системы общих типов:</span><span class="sxs-lookup"><span data-stu-id="144a4-105">This topic contains the following sections that explore the common type system in depth:</span></span>

* [<span data-ttu-id="144a4-106">Типы в .NET</span><span class="sxs-lookup"><span data-stu-id="144a4-106">Types in .NET</span></span>](#types-in-net)

* [<span data-ttu-id="144a4-107">Определения типов</span><span class="sxs-lookup"><span data-stu-id="144a4-107">Type definitions</span></span>](#type-definitions)

* [<span data-ttu-id="144a4-108">Члены типов</span><span class="sxs-lookup"><span data-stu-id="144a4-108">Type members</span></span>](#type-members)

* [<span data-ttu-id="144a4-109">Характеристики членов типов</span><span class="sxs-lookup"><span data-stu-id="144a4-109">Characteristics of type members</span></span>](#characteristics-of-type-members)


## <a name="types-in-net"></a><span data-ttu-id="144a4-110">Типы в .NET</span><span class="sxs-lookup"><span data-stu-id="144a4-110">Types in .NET</span></span>

<span data-ttu-id="144a4-111">Все типы на платформе .NET делятся на типы значений и ссылочные типы.</span><span class="sxs-lookup"><span data-stu-id="144a4-111">All types in .NET are either value types or reference types.</span></span> 

<span data-ttu-id="144a4-112">Типы значений — это типы данных, объекты которых представлены фактическим значением объекта.</span><span class="sxs-lookup"><span data-stu-id="144a4-112">Value types are data types whose objects are represented by the object's actual value.</span></span> <span data-ttu-id="144a4-113">Если экземпляр типа значения присваивается переменной, то эта переменная получает новую копию значения.</span><span class="sxs-lookup"><span data-stu-id="144a4-113">If an instance of a value type is assigned to a variable, that variable is given a fresh copy of the value.</span></span>

<span data-ttu-id="144a4-114">Ссылочные типы — это типы данных, объекты которых представлены ссылкой (аналогичной указателю) на фактическое значение объекта.</span><span class="sxs-lookup"><span data-stu-id="144a4-114">Reference types are data types whose objects are represented by a reference (similar to a pointer) to the object's actual value.</span></span> <span data-ttu-id="144a4-115">Если экземпляр ссылочного типа присваивается переменной, то эта переменная будет ссылаться (указывать) на исходное значение.</span><span class="sxs-lookup"><span data-stu-id="144a4-115">If a reference type is assigned to a variable, that variable references (points to) the original value.</span></span> <span data-ttu-id="144a4-116">Копирования при этом не происходит.</span><span class="sxs-lookup"><span data-stu-id="144a4-116">No copy is made.</span></span> 

<span data-ttu-id="144a4-117">Система общих типов CTS на платформе .NET поддерживает следующие пять категорий типов:</span><span class="sxs-lookup"><span data-stu-id="144a4-117">The common type system in .NET supports the following five categories of types:</span></span>

* [<span data-ttu-id="144a4-118">Классы</span><span class="sxs-lookup"><span data-stu-id="144a4-118">Classes</span></span>](#classes)

* [<span data-ttu-id="144a4-119">Структуры</span><span class="sxs-lookup"><span data-stu-id="144a4-119">Structures</span></span>](#structures)

* [<span data-ttu-id="144a4-120">Перечисления</span><span class="sxs-lookup"><span data-stu-id="144a4-120">Enumerations</span></span>](#enumerations)

* [<span data-ttu-id="144a4-121">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="144a4-121">Interfaces</span></span>](#interfaces)

* [<span data-ttu-id="144a4-122">Делегаты</span><span class="sxs-lookup"><span data-stu-id="144a4-122">Delegates</span></span>](#delegates)

### <a name="classes"></a><span data-ttu-id="144a4-123">Классы</span><span class="sxs-lookup"><span data-stu-id="144a4-123">Classes</span></span>

<span data-ttu-id="144a4-124">Класс — это ссылочный тип, который может быть прямым производным от другого класса и является неявным производным от типа [System.Object](xref:System.Object).</span><span class="sxs-lookup"><span data-stu-id="144a4-124">A class is a reference type that can be derived directly from another class and that is derived implicitly from [System.Object](xref:System.Object).</span></span> <span data-ttu-id="144a4-125">В классе определяются операции, которые объект (являющийся экземпляром класса) может выполнять (методы, события или свойства), и данные, которые объект содержит (поля).</span><span class="sxs-lookup"><span data-stu-id="144a4-125">The class defines the operations that an object (which is an instance of the class) can perform (methods, events, or properties) and the data that the object contains (fields).</span></span> <span data-ttu-id="144a4-126">Обычно класс включает и определение, и реализацию (в отличие, например, от интерфейса, который содержит только определение без реализации), однако один или несколько членов класса могут не иметь реализации.</span><span class="sxs-lookup"><span data-stu-id="144a4-126">Although a class generally includes both definition and implementation (unlike interfaces, for example, which contain only definition without implementation), it can have one or more members that have no implementation.</span></span>

<span data-ttu-id="144a4-127">В приведенной ниже таблице описываются некоторые характеристики, которыми может обладать класс.</span><span class="sxs-lookup"><span data-stu-id="144a4-127">The following table describes some of the characteristics that a class may have.</span></span> <span data-ttu-id="144a4-128">Каждый язык, поддерживающий среду выполнения, позволяет указать на наличие у класса или члена класса одной или нескольких из этих характеристик.</span><span class="sxs-lookup"><span data-stu-id="144a4-128">Each language that supports the runtime provides a way to indicate that a class or class member has one or more of these characteristics.</span></span> <span data-ttu-id="144a4-129">Вместе с тем отдельные языки программирования, ориентированные на платформу .NET, могут не поддерживать некоторые из этих характеристик.</span><span class="sxs-lookup"><span data-stu-id="144a4-129">However, individual programming languages that target .NET may not make all these characteristics available.</span></span>

<span data-ttu-id="144a4-130">Характеристика</span><span class="sxs-lookup"><span data-stu-id="144a4-130">Characteristic</span></span> | <span data-ttu-id="144a4-131">Описание</span><span class="sxs-lookup"><span data-stu-id="144a4-131">Description</span></span>
-------------- | -----------
<span data-ttu-id="144a4-132">sealed</span><span class="sxs-lookup"><span data-stu-id="144a4-132">sealed</span></span> | <span data-ttu-id="144a4-133">Указывает, что наследование от данного класса не допускается.</span><span class="sxs-lookup"><span data-stu-id="144a4-133">Specifies that another class cannot be derived from this type.</span></span>
<span data-ttu-id="144a4-134">реализует</span><span class="sxs-lookup"><span data-stu-id="144a4-134">implements</span></span> | <span data-ttu-id="144a4-135">Показывает, что в классе используется один или несколько интерфейсов за счет предоставления реализаций их членов.</span><span class="sxs-lookup"><span data-stu-id="144a4-135">Indicates that the class uses one or more interfaces by providing implementations of interface members.</span></span>
<span data-ttu-id="144a4-136">abstract</span><span class="sxs-lookup"><span data-stu-id="144a4-136">abstract</span></span> | <span data-ttu-id="144a4-137">Указывает, что создавать экземпляры этого класса нельзя.</span><span class="sxs-lookup"><span data-stu-id="144a4-137">Indicates that the class cannot be instantiated.</span></span> <span data-ttu-id="144a4-138">Чтобы его использовать, необходимо создать из данного класса производный класс.</span><span class="sxs-lookup"><span data-stu-id="144a4-138">To use it, you must derive another class from it.</span></span>
<span data-ttu-id="144a4-139">наследует</span><span class="sxs-lookup"><span data-stu-id="144a4-139">inherits</span></span> | <span data-ttu-id="144a4-140">Показывает, что экземпляры класса можно использовать везде, где задан базовый класс.</span><span class="sxs-lookup"><span data-stu-id="144a4-140">Indicates that instances of the class can be used anywhere the base class is specified.</span></span> <span data-ttu-id="144a4-141">Производный класс, который наследует от базового, может использовать реализацию любых открытых членов, предоставляемых базовым классом, либо переопределить реализацию этих открытых членов собственной их реализацией.</span><span class="sxs-lookup"><span data-stu-id="144a4-141">A derived class that inherits from a base class can use the implementation of any public members provided by the base class, or the derived class can override the implementation of the public members with its own implementation.</span></span>
<span data-ttu-id="144a4-142">exported или not exported</span><span class="sxs-lookup"><span data-stu-id="144a4-142">exported or not exported</span></span> | <span data-ttu-id="144a4-143">Показывает, виден ли класс за пределами сборки, в которой он определен.</span><span class="sxs-lookup"><span data-stu-id="144a4-143">Indicates whether a class is visible outside the assembly in which it is defined.</span></span> <span data-ttu-id="144a4-144">Эта характеристика применима только к классам верхнего уровня, но не к вложенным классам.</span><span class="sxs-lookup"><span data-stu-id="144a4-144">This characteristic applies only to top-level classes and not to nested classes.</span></span>

> [!NOTE]
> <span data-ttu-id="144a4-145">Класс может также быть вложен в родительский класс или родительскую структуру.</span><span class="sxs-lookup"><span data-stu-id="144a4-145">A class can also be nested in a parent class or structure.</span></span> <span data-ttu-id="144a4-146">Вложенные классы также имеют характеристики членов.</span><span class="sxs-lookup"><span data-stu-id="144a4-146">Nested classes also have member characteristics.</span></span> <span data-ttu-id="144a4-147">Дополнительные сведения см. в разделе [Вложенные типы](#nested-types).</span><span class="sxs-lookup"><span data-stu-id="144a4-147">For more information, see [Nested types](#nested-types).</span></span>

<span data-ttu-id="144a4-148">Члены классов, не имеющие реализации, являются абстрактными.</span><span class="sxs-lookup"><span data-stu-id="144a4-148">Class members that have no implementation are abstract members.</span></span> <span data-ttu-id="144a4-149">Класс, содержащий несколько абстрактных членов, сам является абстрактным. Новые экземпляры этого класса создать нельзя.</span><span class="sxs-lookup"><span data-stu-id="144a4-149">A class that has one or more abstract members is itself abstract; new instances of it cannot be created.</span></span> <span data-ttu-id="144a4-150">Некоторые языки, ориентированные на среду выполнения, позволяют пометить класс как абстрактный даже в том случае, если он не содержит ни одного абстрактного члена.</span><span class="sxs-lookup"><span data-stu-id="144a4-150">Some languages that target the runtime let you mark a class as abstract even if none of its members are abstract.</span></span> <span data-ttu-id="144a4-151">Абстрактный класс можно использовать, когда требуется инкапсулировать базовый набор функциональных возможностей, которые производные классы могут наследовать или переопределять.</span><span class="sxs-lookup"><span data-stu-id="144a4-151">You can use an abstract class when you want to encapsulate a basic set of functionality that derived classes can inherit or override when appropriate.</span></span> <span data-ttu-id="144a4-152">Классы, не являющиеся абстрактными, называются конкретными классами.</span><span class="sxs-lookup"><span data-stu-id="144a4-152">Classes that are not abstract are referred to as concrete classes.</span></span>

<span data-ttu-id="144a4-153">Класс может реализовывать любое число интерфейсов, однако он также может наследовать только от одного базового класса в дополнение к [System.Object](xref:System.Object), от которого неявно наследуют все классы.</span><span class="sxs-lookup"><span data-stu-id="144a4-153">A class can implement any number of interfaces, but it can inherit from only one base class in addition to [System.Object](xref:System.Object), from which all classes inherit implicitly.</span></span> <span data-ttu-id="144a4-154">Любой класс должен иметь по крайней мере один конструктор, который инициализирует новые экземпляры класса.</span><span class="sxs-lookup"><span data-stu-id="144a4-154">All classes must have at least one constructor, which initializes new instances of the class.</span></span> <span data-ttu-id="144a4-155">Если конструктор не определен явно, большинство компиляторов автоматически предоставят заданный по умолчанию конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="144a4-155">If you do not explicitly define a constructor, most compilers will automatically provide a default (parameterless) constructor.</span></span>

### <a name="structures"></a><span data-ttu-id="144a4-156">Структуры</span><span class="sxs-lookup"><span data-stu-id="144a4-156">Structures</span></span>

<span data-ttu-id="144a4-157">Структура — это тип значения, неявно производный от типа [System.ValueType](xref:System.ValueType), который, в свою очередь, является производным от типа [System.Object](xref:System.Object).</span><span class="sxs-lookup"><span data-stu-id="144a4-157">A structure is a value type that derives implicitly from [System.ValueType](xref:System.ValueType), which in turn is derived from [System.Object](xref:System.Object).</span></span> <span data-ttu-id="144a4-158">Структуры весьма полезны для представления значений с небольшими требованиями к памяти и для передачи параметров по значению в методы со строгой типизацией параметров.</span><span class="sxs-lookup"><span data-stu-id="144a4-158">A structure is very useful for representing values whose memory requirements are small, and for passing values as by-value parameters to methods that have strongly typed parameters.</span></span> <span data-ttu-id="144a4-159">В среде .NET все типы-примитивы ([Boolean](xref:System.Boolean), [Byte](xref:System.Byte), [Char](xref:System.Char), [DateTime](xref:System.DateTime), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32) и [UInt64](xref:System.UInt64)) определяются как структуры.</span><span class="sxs-lookup"><span data-stu-id="144a4-159">In .NET, all primitive data types ([Boolean](xref:System.Boolean), [Byte](xref:System.Byte), [Char](xref:System.Char), [DateTime](xref:System.DateTime), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), and [UInt64](xref:System.UInt64)) are defined as structures.</span></span>

<span data-ttu-id="144a4-160">Как и в классах, в структурах определяются и данные (поля структуры), и операции, которые можно выполнять над этими данными (методы структуры).</span><span class="sxs-lookup"><span data-stu-id="144a4-160">Like classes, structures define both data (the fields of the structure) and the operations that can be performed on that data (the methods of the structure).</span></span> <span data-ttu-id="144a4-161">Это означает, что применительно к структурам можно вызывать методы, в том числе виртуальные методы, определенные в классах [System.Object](xref:System.Object) и [System.ValueType](xref:System.ValueType), а также любые методы, определенные в самом типе значения.</span><span class="sxs-lookup"><span data-stu-id="144a4-161">This means that you can call methods on structures, including the virtual methods defined on the [System.Object](xref:System.Object) and [System.ValueType](xref:System.ValueType) classes, and any methods defined on the value type itself.</span></span> <span data-ttu-id="144a4-162">Другими словами, структуры могут иметь поля, свойства и события, а также статические и нестатические методы.</span><span class="sxs-lookup"><span data-stu-id="144a4-162">In other words, structures can have fields, properties, and events, as well as static and nonstatic methods.</span></span> <span data-ttu-id="144a4-163">Можно создавать экземпляры структур, передавать их в качестве параметров, хранить их в качестве локальных переменных либо в поле другого типа значения или ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="144a4-163">You can create instances of structures, pass them as parameters, store them as local variables, or store them in a field of another value type or reference type.</span></span> <span data-ttu-id="144a4-164">Структуры также могут реализовывать интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="144a4-164">Structures can also implement interfaces.</span></span>

<span data-ttu-id="144a4-165">Кроме того, типы значений отличаются от классов в ряде других вопросов.</span><span class="sxs-lookup"><span data-stu-id="144a4-165">Value types also differ from classes in several respects.</span></span> <span data-ttu-id="144a4-166">Во-первых, хотя они неявно наследуют от [System.ValueType](xref:System.ValueType), они не могут напрямую наследовать ни от какого типа.</span><span class="sxs-lookup"><span data-stu-id="144a4-166">First, although they implicitly inherit from [System.ValueType](xref:System.ValueType), they cannot directly inherit from any type.</span></span> <span data-ttu-id="144a4-167">Аналогичным образом, все типы значений являются запечатанными. Это значит, что наследование от них не допускается.</span><span class="sxs-lookup"><span data-stu-id="144a4-167">Similarly, all value types are sealed, which means that no other type can be derived from them.</span></span> <span data-ttu-id="144a4-168">Им также не требуются конструкторы.</span><span class="sxs-lookup"><span data-stu-id="144a4-168">They also do not require constructors.</span></span>

<span data-ttu-id="144a4-169">Для каждого типа значения среда CLR предоставляет соответствующий упакованный тип — класс, имеющий то же состояние и поведение, что и тип значения.</span><span class="sxs-lookup"><span data-stu-id="144a4-169">For each value type, the common language runtime supplies a corresponding boxed type, which is a class that has the same state and behavior as the value type.</span></span> <span data-ttu-id="144a4-170">Экземпляр типа значения упаковывается при передаче в метод, принимающий параметр типа [System.Object](xref:System.Object).</span><span class="sxs-lookup"><span data-stu-id="144a4-170">An instance of a value type is boxed when it is passed to a method that accepts a parameter of type [System.Object](xref:System.Object).</span></span> <span data-ttu-id="144a4-171">Распаковка (преобразование из экземпляра класса обратно в экземпляр типа значения) производится при возврате управления после вызова метода, принимающего тип значения в качестве параметра по ссылке.</span><span class="sxs-lookup"><span data-stu-id="144a4-171">It is unboxed (that is, converted from an instance of a class back to an instance of a value type) when control returns from a method call that accepts a value type as a by-reference parameter.</span></span> <span data-ttu-id="144a4-172">В некоторых языках необходимо применение специального синтаксиса, когда требуется упакованный тип; в других упакованный тип используется автоматически, когда он нужен.</span><span class="sxs-lookup"><span data-stu-id="144a4-172">Some languages require that you use special syntax when the boxed type is required; others automatically use the boxed type when it is needed.</span></span> <span data-ttu-id="144a4-173">При определении типа значений определяется и упакованный, и неупакованный тип.</span><span class="sxs-lookup"><span data-stu-id="144a4-173">When you define a value type, you are defining both the boxed and the unboxed type.</span></span>

### <a name="enumerations"></a><span data-ttu-id="144a4-174">Перечисления</span><span class="sxs-lookup"><span data-stu-id="144a4-174">Enumerations</span></span>

<span data-ttu-id="144a4-175">Перечисление (enum) — это тип значения, который напрямую наследует от [System.Enum](xref:System.Enum) и предоставляет альтернативные имена для значений базового типа-примитива.</span><span class="sxs-lookup"><span data-stu-id="144a4-175">An enumeration (enum) is a value type that inherits directly from [System.Enum](xref:System.Enum) and that supplies alternate names for the values of an underlying primitive type.</span></span> <span data-ttu-id="144a4-176">Тип перечисления имеет имя, базовый тип, который должен быть одним из встроенных целочисленных знаковых или беззнаковых типов (например, [Byte](xref:System.Byte), [Int32](xref:System.Int32) или [UInt64](xref:System.UInt64)), а также набор полей.</span><span class="sxs-lookup"><span data-stu-id="144a4-176">An enumeration type has a name, an underlying type that must be one of the built-in signed or unsigned integer types (such as [Byte](xref:System.Byte), [Int32](xref:System.Int32), or [UInt64](xref:System.UInt64)), and a set of fields.</span></span> <span data-ttu-id="144a4-177">Поля являются статическими полями литералов, каждое из которых представляет константу.</span><span class="sxs-lookup"><span data-stu-id="144a4-177">The fields are static literal fields, each of which represents a constant.</span></span> <span data-ttu-id="144a4-178">Одно значение можно присвоить нескольким полям.</span><span class="sxs-lookup"><span data-stu-id="144a4-178">The same value can be assigned to multiple fields.</span></span> <span data-ttu-id="144a4-179">В этом случае необходимо пометить одно из значений как первичное значение перечисления для отражения и преобразования строк.</span><span class="sxs-lookup"><span data-stu-id="144a4-179">When this occurs, you must mark one of the values as the primary enumeration value for reflection and string conversion.</span></span>

<span data-ttu-id="144a4-180">Значение базового типа можно присвоить перечислению и наоборот (среда выполнения не требует приведения типов).</span><span class="sxs-lookup"><span data-stu-id="144a4-180">You can assign a value of the underlying type to an enumeration and vice versa (no cast is required by the runtime).</span></span> <span data-ttu-id="144a4-181">Можно создавать экземпляры перечислений и вызвать методы [System.Enum](xref:System.Enum), а также любые методы, определенные в базовом типе перечисления.</span><span class="sxs-lookup"><span data-stu-id="144a4-181">You can create an instance of an enumeration and call the methods of [System.Enum](xref:System.Enum), as well as any methods defined on the enumeration's underlying type.</span></span> <span data-ttu-id="144a4-182">При этом в некоторых языках передача перечисления в виде параметра может не допускаться, если требуется передать экземпляр базового типа (или наоборот).</span><span class="sxs-lookup"><span data-stu-id="144a4-182">However, some languages might not let you pass an enumeration as a parameter when an instance of the underlying type is required (or vice versa).</span></span>

<span data-ttu-id="144a4-183">К перечислениям применяются следующие дополнительные ограничения.</span><span class="sxs-lookup"><span data-stu-id="144a4-183">The following additional restrictions apply to enumerations:</span></span> 

* <span data-ttu-id="144a4-184">В них нельзя определять собственные методы.</span><span class="sxs-lookup"><span data-stu-id="144a4-184">They cannot define their own methods.</span></span>

* <span data-ttu-id="144a4-185">В них нельзя реализовывать интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="144a4-185">They cannot implement interfaces.</span></span>

* <span data-ttu-id="144a4-186">В них нельзя определять свойства и события.</span><span class="sxs-lookup"><span data-stu-id="144a4-186">They cannot define properties or events.</span></span>

* <span data-ttu-id="144a4-187">Они не могут быть универсальными, если только они становятся таковыми за счет вложения внутрь универсального типа.</span><span class="sxs-lookup"><span data-stu-id="144a4-187">They cannot be generic, unless they are generic only because they are nested within a generic type.</span></span> <span data-ttu-id="144a4-188">То есть перечисления не могут иметь свои собственные параметры типов.</span><span class="sxs-lookup"><span data-stu-id="144a4-188">That is, an enumeration cannot have type parameters of its own.</span></span> 

> [!NOTE]
> <span data-ttu-id="144a4-189">Вложенные типы (в том числе перечисления), созданные на языке C#, содержат параметры всех включающих их универсальных типов и, таким образом, являются универсальными, даже если они не имеют своих собственных параметров типов.</span><span class="sxs-lookup"><span data-stu-id="144a4-189">Nested types (including enumerations) created with C# include the type parameters of all enclosing generic types, and are therefore generic even if they do not have type parameters of their own.</span></span> <span data-ttu-id="144a4-190">Дополнительные сведения см. в разделе справки по [Type.MakeGenericType](xref:System.Type.MakeGenericType(System.Type[])).</span><span class="sxs-lookup"><span data-stu-id="144a4-190">For more information, see the [Type.MakeGenericType](xref:System.Type.MakeGenericType(System.Type[])) reference topic.</span></span> 

<span data-ttu-id="144a4-191">Атрибут [FlagsAttribute](xref:System.FlagsAttribute) обозначает специальный вид перечисления, называемый битовым полем.</span><span class="sxs-lookup"><span data-stu-id="144a4-191">The [FlagsAttribute](xref:System.FlagsAttribute) attribute denotes a special kind of enumeration called a bit field.</span></span> <span data-ttu-id="144a4-192">Среда выполнения (в отличие от языка программирования) не различает обычные перечисления и битовые поля.</span><span class="sxs-lookup"><span data-stu-id="144a4-192">The runtime itself does not distinguish between traditional enumerations and bit fields, but your language might do so.</span></span> <span data-ttu-id="144a4-193">Если это отличие обнаружено, для создания неименованных значений в битовых полях можно использовать битовые операторы (в перечислениях их использовать нельзя).</span><span class="sxs-lookup"><span data-stu-id="144a4-193">When this distinction is made, bitwise operators can be used on bit fields, but not on enumerations, to generate unnamed values.</span></span> <span data-ttu-id="144a4-194">Перечисления обычно используются для списков уникальных элементов, например дней недели, названий стран или областей и т. д.</span><span class="sxs-lookup"><span data-stu-id="144a4-194">Enumerations are generally used for lists of unique elements, such as days of the week, country or region names, and so on.</span></span> <span data-ttu-id="144a4-195">Битовые поля обычно используются для списков количеств и качеств, которые могут возникать в таких комбинациях, как `Red And Big And Fast`.</span><span class="sxs-lookup"><span data-stu-id="144a4-195">Bit fields are generally used for lists of qualities or quantities that might occur in combination, such as `Red And Big And Fast`.</span></span>

<span data-ttu-id="144a4-196">В следующем примере показан способ использования битовых полей и обычных перечислений.</span><span class="sxs-lookup"><span data-stu-id="144a4-196">The following example shows how to use both bit fields and traditional enumerations.</span></span>

```csharp
using System;
using System.Collections.Generic;

// A traditional enumeration of some root vegetables.
public enum SomeRootVegetables
{
    HorseRadish,
    Radish,
    Turnip
}

// A bit field or flag enumeration of harvesting seasons.
[Flags]
public enum Seasons
{
    None = 0,
    Summer = 1,
    Autumn = 2,
    Winter = 4,
    Spring = 8,
    All = Summer | Autumn | Winter | Spring
}

public class Example
{
   public static void Main()
   {
       // Hash table of when vegetables are available.
       Dictionary<SomeRootVegetables, Seasons> AvailableIn = new Dictionary<SomeRootVegetables, Seasons>();

       AvailableIn[SomeRootVegetables.HorseRadish] = Seasons.All;
       AvailableIn[SomeRootVegetables.Radish] = Seasons.Spring;
       AvailableIn[SomeRootVegetables.Turnip] = Seasons.Spring | 
            Seasons.Autumn;

       // Array of the seasons, using the enumeration.
       Seasons[] theSeasons = new Seasons[] { Seasons.Summer, Seasons.Autumn, 
            Seasons.Winter, Seasons.Spring };

       // Print information of what vegetables are available each season.
       foreach (Seasons season in theSeasons)
       {
          Console.Write(String.Format(
              "The following root vegetables are harvested in {0}:\n", 
              season.ToString("G")));
          foreach (KeyValuePair<SomeRootVegetables, Seasons> item in AvailableIn)
          {
             // A bitwise comparison.
             if (((Seasons)item.Value & season) > 0)
                 Console.Write(String.Format("  {0:G}\n", 
                      (SomeRootVegetables)item.Key));
          }
       }
   }
}
// The example displays the following output:
//    The following root vegetables are harvested in Summer:
//      HorseRadish
//    The following root vegetables are harvested in Autumn:
//      Turnip
//      HorseRadish
//    The following root vegetables are harvested in Winter:
//      HorseRadish
//    The following root vegetables are harvested in Spring:
//      Turnip
//      Radish
//      HorseRadish
```

```vb
Imports System.Collections.Generic

' A traditional enumeration of some root vegetables.
Public Enum SomeRootVegetables
   HorseRadish
   Radish
   Turnip
End Enum 

' A bit field or flag enumeration of harvesting seasons.
<Flags()> Public Enum Seasons
   None = 0
   Summer = 1
   Autumn = 2
   Winter = 4
   Spring = 8
   All = Summer Or Autumn Or Winter Or Spring
End Enum 

' Entry point.
Public Class Example
   Public Shared Sub Main()
      ' Hash table of when vegetables are available.
      Dim AvailableIn As New Dictionary(Of SomeRootVegetables, Seasons)()

      AvailableIn(SomeRootVegetables.HorseRadish) = Seasons.All
      AvailableIn(SomeRootVegetables.Radish) = Seasons.Spring
      AvailableIn(SomeRootVegetables.Turnip) = Seasons.Spring Or _
                                               Seasons.Autumn

      ' Array of the seasons, using the enumeration.
      Dim theSeasons() As Seasons = {Seasons.Summer, Seasons.Autumn, _
                                     Seasons.Winter, Seasons.Spring}

      ' Print information of what vegetables are available each season.
      For Each season As Seasons In theSeasons
         Console.WriteLine(String.Format( _
              "The following root vegetables are harvested in {0}:", _
              season.ToString("G")))
         For Each item As KeyValuePair(Of SomeRootVegetables, Seasons) In AvailableIn
            ' A bitwise comparison.
            If(CType(item.Value, Seasons) And season) > 0 Then
               Console.WriteLine("  " + _
                     CType(item.Key, SomeRootVegetables).ToString("G"))
            End If
         Next
      Next
   End Sub 
End Class 
' The example displays the following output:
'    The following root vegetables are harvested in Summer:
'      HorseRadish
'    The following root vegetables are harvested in Autumn:
'      Turnip
'      HorseRadish
'    The following root vegetables are harvested in Winter:
'      HorseRadish
'    The following root vegetables are harvested in Spring:
'      Turnip
'      Radish
'      HorseRadish
```

### <a name="interfaces"></a><span data-ttu-id="144a4-197">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="144a4-197">Interfaces</span></span>

<span data-ttu-id="144a4-198">Интерфейс задает контракт, определяющий отношение типа "может" или "имеет".</span><span class="sxs-lookup"><span data-stu-id="144a4-198">An interface defines a contract that specifies a "can do" relationship or a "has a" relationship.</span></span> <span data-ttu-id="144a4-199">Интерфейсы часто используются для реализации различных функций, например для сравнения и сортировки (интерфейсы [IComparable](xref:System.IComparable) и [IComparable&lt;T&gt;](xref:System.IComparable%601)), проверки равенства (интерфейс [IEquatable&lt;T&gt;](xref:System.IEquatable%601)) или перечисления элементов коллекции (интерфейсы [IEnumerable](xref:System.Collections.IEnumerable) и [IEnumerable&lt;T&gt;](xref:System.Collections.Generic.IEnumerable%601)).</span><span class="sxs-lookup"><span data-stu-id="144a4-199">Interfaces are often used to implement functionality, such as comparing and sorting (the [IComparable](xref:System.IComparable) and [IComparable&lt;T&gt;](xref:System.IComparable%601) interfaces), testing for equality (the [IEquatable&lt;T&gt;](xref:System.IEquatable%601) interface), or enumerating items in a collection (the [IEnumerable](xref:System.Collections.IEnumerable) and [IEnumerable&lt;T&gt;](xref:System.Collections.Generic.IEnumerable%601) interfaces).</span></span> <span data-ttu-id="144a4-200">Интерфейсы могут иметь свойства, методы и события, являющиеся абстрактными членами. Это значит, что хотя в интерфейсе определяются члены и их сигнатуры, за определение функциональности всех членов интерфейса отвечает тип, реализующий данный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="144a4-200">Interfaces can have properties, methods, and events, all of which are abstract members; that is, although the interface defines the members and their signatures, it leaves it to the type that implements the interface to define the functionality of each interface member.</span></span> <span data-ttu-id="144a4-201">Любой класс или структура, реализующие интерфейс, должны содержать определения абстрактных членов, объявленных в этом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="144a4-201">This means that any class or structure that implements an interface must supply definitions for the abstract members declared in the interface.</span></span> <span data-ttu-id="144a4-202">Обязательным условием реализации интерфейса в классе или структуре также может быть реализация одного или нескольких других интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="144a4-202">An interface can require any implementing class or structure to also implement one or more other interfaces.</span></span>

<span data-ttu-id="144a4-203">К интерфейсам применяются следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="144a4-203">The following restrictions apply to interfaces:</span></span> 

* <span data-ttu-id="144a4-204">Интерфейс может быть объявлен с любой доступностью, однако, члены интерфейса всегда должны иметь доступность уровня public.</span><span class="sxs-lookup"><span data-stu-id="144a4-204">An interface can be declared with any accessibility, but interface members must all have public accessibility.</span></span>

* <span data-ttu-id="144a4-205">В интерфейсах нельзя определять конструкторы.</span><span class="sxs-lookup"><span data-stu-id="144a4-205">Interfaces cannot define constructors.</span></span>

* <span data-ttu-id="144a4-206">В интерфейсах нельзя определять поля.</span><span class="sxs-lookup"><span data-stu-id="144a4-206">Interfaces cannot define fields.</span></span>

* <span data-ttu-id="144a4-207">В интерфейсах можно определять только члены экземпляров.</span><span class="sxs-lookup"><span data-stu-id="144a4-207">Interfaces can define only instance members.</span></span> <span data-ttu-id="144a4-208">Статические члены определять в них нельзя.</span><span class="sxs-lookup"><span data-stu-id="144a4-208">They cannot define static members.</span></span>

<span data-ttu-id="144a4-209">Поскольку в нескольких интерфейсах могут быть объявлены члены с одной и той же сигнатурой, имеющие разные реализации, любой язык должен предоставлять правила сопоставления реализации с интерфейсом, для которого требуется данный член.</span><span class="sxs-lookup"><span data-stu-id="144a4-209">Each language must provide rules for mapping an implementation to the interface that requires the member, because more than one interface can declare a member with the same signature, and these members can have separate implementations.</span></span>

### <a name="delegates"></a><span data-ttu-id="144a4-210">Делегаты</span><span class="sxs-lookup"><span data-stu-id="144a4-210">Delegates</span></span>

<span data-ttu-id="144a4-211">Делегаты — это ссылочные типы, аналогичные по назначению указателям на функции в языке C++.</span><span class="sxs-lookup"><span data-stu-id="144a4-211">Delegates are reference types that serve a purpose similar to that of function pointers in C++.</span></span> <span data-ttu-id="144a4-212">Они применяются в обработчиках событий и функциях обратного вызова в составе платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="144a4-212">They are used for event handlers and callback functions in .NET.</span></span> <span data-ttu-id="144a4-213">В отличие от указателей функций, делегаты являются безопасными, проверяемыми и типобезопасными.</span><span class="sxs-lookup"><span data-stu-id="144a4-213">Unlike function pointers, delegates are secure, verifiable, and type safe.</span></span> <span data-ttu-id="144a4-214">Тип делегата может представлять любой метод экземпляра или статический метод, имеющий совместимую сигнатуру.</span><span class="sxs-lookup"><span data-stu-id="144a4-214">A delegate type can represent any instance method or static method that has a compatible signature.</span></span> 

<span data-ttu-id="144a4-215">Если тип параметра делегата является более строгим, чем тип параметра метода, то параметр делегата совместим с соответствующим параметром метода, так как это гарантирует, что аргумент, переданный делегату, может быть безопасно передан методу.</span><span class="sxs-lookup"><span data-stu-id="144a4-215">A parameter of a delegate is compatible with the corresponding parameter of a method if the type of the delegate parameter is more restrictive than the type of the method parameter, because this guarantees that an argument passed to the delegate can be passed safely to the method.</span></span>

<span data-ttu-id="144a4-216">Аналогичным образом, тип возвращаемого значения делегата совместим с типом возвращаемого значения метода, если тип возвращаемого значения метода является более строгим, чем тип возвращаемого значения делегата, так как это гарантирует, что возвращаемое значение метода может быть безопасно приведено к типу возвращаемого значения делегата.</span><span class="sxs-lookup"><span data-stu-id="144a4-216">Similarly, the return type of a delegate is compatible with the return type of a method if the return type of the method is more restrictive than the return type of the delegate, because this guarantees that the return value of the method can be cast safely to the return type of the delegate.</span></span>

<span data-ttu-id="144a4-217">Например, делегат с параметром типа [IEnumerable](xref:System.Collections.IEnumerable) и типом возвращаемого значения [Object](xref:System.Object) может представлять метод с параметром типа [Object](xref:System.Object) и типом возвращаемого значения [IEnumerable](xref:System.Collections.IEnumerable).</span><span class="sxs-lookup"><span data-stu-id="144a4-217">For example, a delegate that has a parameter of type [IEnumerable](xref:System.Collections.IEnumerable) and a return type of [Object](xref:System.Object) can represent a method that has a parameter of type [Object](xref:System.Object) and a return value of type [IEnumerable](xref:System.Collections.IEnumerable).</span></span> 

 <span data-ttu-id="144a4-218">Делегат называют связанным с методом, который он представляет.</span><span class="sxs-lookup"><span data-stu-id="144a4-218">A delegate is said to be bound to the method it represents.</span></span> <span data-ttu-id="144a4-219">Помимо привязки к методу, делегат может быть связан с отдельным объектом.</span><span class="sxs-lookup"><span data-stu-id="144a4-219">In addition to being bound to the method, a delegate can be bound to an object.</span></span> <span data-ttu-id="144a4-220">Этот объект представляет первый параметр метода и передается методу при каждом вызове делегата.</span><span class="sxs-lookup"><span data-stu-id="144a4-220">The object represents the first parameter of the method, and is passed to the method every time the delegate is invoked.</span></span> <span data-ttu-id="144a4-221">Если это метод экземпляра, то связанный объект передается как неявный параметр `this` (`Me` в Visual Basic); если метод является статическим, то объект передается как первый формальный параметр метода, и сигнатура делегата при этом должна соответствовать остальным параметрам.</span><span class="sxs-lookup"><span data-stu-id="144a4-221">If the method is an instance method, the bound object is passed as the implicit `this` parameter (`Me` in Visual Basic); if the method is static, the object is passed as the first formal parameter of the method, and the delegate signature must match the remaining parameters.</span></span> 
 
 <span data-ttu-id="144a4-222">Все делегаты наследуют от [System.MulticastDelegate](xref:System.MulticastDelegate), который наследует от [System.Delegate](xref:System.Delegate).</span><span class="sxs-lookup"><span data-stu-id="144a4-222">All delegates inherit from [System.MulticastDelegate](xref:System.MulticastDelegate), which inherits from [System.Delegate](xref:System.Delegate).</span></span> <span data-ttu-id="144a4-223">Языки C# и Visual Basic не допускают наследование от этих типов.</span><span class="sxs-lookup"><span data-stu-id="144a4-223">The C# and Visual Basic languages don't allow inheritance from these types.</span></span> <span data-ttu-id="144a4-224">Вместо этого они предоставляют ключевые слова для объявления делегатов.</span><span class="sxs-lookup"><span data-stu-id="144a4-224">Instead, they provide keywords for declaring delegates.</span></span>
 
 <span data-ttu-id="144a4-225">Поскольку делегаты наследуют от [MulticastDelegate](xref:System.MulticastDelegate), делегат имеет список вызова, представляющий собой список методов, которые представляет делегат и которые выполняются при вызове делегата.</span><span class="sxs-lookup"><span data-stu-id="144a4-225">Because delegates inherit from [MulticastDelegate](xref:System.MulticastDelegate), a delegate has an invocation list, which is a list of methods that the delegate represents and that are executed when the delegate is invoked.</span></span> <span data-ttu-id="144a4-226">Все методы в списке получают аргументы, предоставляемые при вызове делегата.</span><span class="sxs-lookup"><span data-stu-id="144a4-226">All methods in the list receive the arguments supplied when the delegate is invoked.</span></span>

> [!NOTE]
> <span data-ttu-id="144a4-227">Для делегата, имеющего более одного метода в списке вызовов, возвращаемое значение не определяется, даже если у делегата есть возвращаемый тип.</span><span class="sxs-lookup"><span data-stu-id="144a4-227">The return value is not defined for a delegate that has more than one method in its invocation list, even if the delegate has a return type.</span></span>

<span data-ttu-id="144a4-228">Зачастую, как, например, в случае с методами обратного вызова, делегат представляет только один метод, поэтому единственное действие, которое нужно выполнить, — это создание и вызов делегата.</span><span class="sxs-lookup"><span data-stu-id="144a4-228">In many cases, such as with callback methods, a delegate represents only one method, and the only actions you have to take are creating the delegate and invoking it.</span></span> 

<span data-ttu-id="144a4-229">Для делегатов, представляющих несколько методов, .NET предоставляет методы классов делегатов [Delegate](xref:System.Delegate) и [MulticastDelegate](xref:System.MulticastDelegate) для поддержки таких операций, как добавление методов к списку вызовов делегата (метод [Delegate.Combine](xref:System.Delegate.Combine(System.Delegate,System.Delegate))), удаление метода (метод [Delegate.Remove](xref:System.Delegate.Remove(System.Delegate,System.Delegate))) и получение списка вызовов (метод [Delegate.GetInvocationList](xref:System.Delegate.GetInvocationList)).</span><span class="sxs-lookup"><span data-stu-id="144a4-229">For delegates that represent multiple methods, .NET provides methods of the [Delegate](xref:System.Delegate) and [MulticastDelegate](xref:System.MulticastDelegate) delegate classes to support operations such as adding a method to a delegate's invocation list (the [Delegate.Combine](xref:System.Delegate.Combine(System.Delegate,System.Delegate)) method), removing a method (the [Delegate.Remove](xref:System.Delegate.Remove(System.Delegate,System.Delegate)) method), and getting the invocation list (the [Delegate.GetInvocationList](xref:System.Delegate.GetInvocationList) method).</span></span>

> [!NOTE]
> <span data-ttu-id="144a4-230">Применение этих методов к делегатам обработчиков событий в C# или Visual Basic необязательно, так как эти языки предоставляют синтаксис для добавления и удаления обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="144a4-230">It is not necessary to use these methods for event-handler delegates in C# or Visual Basic, because these languages provide syntax for adding and removing event handlers.</span></span>

## <a name="type-definitions"></a><span data-ttu-id="144a4-231">Определения типов</span><span class="sxs-lookup"><span data-stu-id="144a4-231">Type definitions</span></span>

<span data-ttu-id="144a4-232">Определение типа включает следующее:</span><span class="sxs-lookup"><span data-stu-id="144a4-232">A type definition includes the following:</span></span> 

* <span data-ttu-id="144a4-233">все определенные в типе атрибуты;</span><span class="sxs-lookup"><span data-stu-id="144a4-233">Any attributes defined on the type.</span></span>

* <span data-ttu-id="144a4-234">доступность (видимость) типа;</span><span class="sxs-lookup"><span data-stu-id="144a4-234">The type's accessibility (visibility).</span></span>

* <span data-ttu-id="144a4-235">имя типа;</span><span class="sxs-lookup"><span data-stu-id="144a4-235">The type's name.</span></span>

* <span data-ttu-id="144a4-236">базовый тип данного типа;</span><span class="sxs-lookup"><span data-stu-id="144a4-236">The type's base type.</span></span>

* <span data-ttu-id="144a4-237">все интерфейсы, реализованные этим типом;</span><span class="sxs-lookup"><span data-stu-id="144a4-237">Any interfaces implemented by the type.</span></span>

* <span data-ttu-id="144a4-238">определения каждого члена типа.</span><span class="sxs-lookup"><span data-stu-id="144a4-238">Definitions for each of the type's members.</span></span>

### <a name="attributes"></a><span data-ttu-id="144a4-239">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="144a4-239">Attributes</span></span>

<span data-ttu-id="144a4-240">Атрибуты предоставляют дополнительные пользовательские метаданные.</span><span class="sxs-lookup"><span data-stu-id="144a4-240">Attributes provide additional user-defined metadata.</span></span> <span data-ttu-id="144a4-241">Они чаще всего используются для хранения дополнительной информации о типе в его сборке либо для изменения поведения члена типа во время разработки или выполнения.</span><span class="sxs-lookup"><span data-stu-id="144a4-241">Most commonly, they are used to store additional information about a type in its assembly, or to modify the behavior of a type member in either the design-time or run-time environment.</span></span> 

<span data-ttu-id="144a4-242">Сами атрибуты представляют собой классы, которые наследуют от [System.Attribute](xref:System.Attribute).</span><span class="sxs-lookup"><span data-stu-id="144a4-242">Attributes are themselves classes that inherit from [System.Attribute](xref:System.Attribute).</span></span> <span data-ttu-id="144a4-243">Любой язык, поддерживающий использование атрибутов, имеет собственный синтаксис для применения атрибутов к элементам языка.</span><span class="sxs-lookup"><span data-stu-id="144a4-243">Languages that support the use of attributes each have their own syntax for applying attributes to a language element.</span></span> <span data-ttu-id="144a4-244">Атрибуты можно применять почти к любым элементам языка. Конкретные элементы, к которым можно применять определенный атрибут, задаются атрибутом [AttributeUsageAttribute](xref:System.AttributeUsageAttribute), примененным к классу этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="144a4-244">Attributes can be applied to almost any language element; the specific elements to which an attribute can be applied are defined by the [AttributeUsageAttribute](xref:System.AttributeUsageAttribute) that is applied to that attribute class.</span></span>

### <a name="type-accessibility"></a><span data-ttu-id="144a4-245">Доступность типов</span><span class="sxs-lookup"><span data-stu-id="144a4-245">Type accessibility</span></span>

<span data-ttu-id="144a4-246">Все типы имеют модификатор, который определяет их доступность из других типов.</span><span class="sxs-lookup"><span data-stu-id="144a4-246">All types have a modifier that governs their accessibility from other types.</span></span> <span data-ttu-id="144a4-247">В следующей таблице описаны виды доступности типов, поддерживаемые в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="144a4-247">The following table describes the type accessibilities supported by the runtime.</span></span>

<span data-ttu-id="144a4-248">Специальные возможности</span><span class="sxs-lookup"><span data-stu-id="144a4-248">Accessibility</span></span> | <span data-ttu-id="144a4-249">Описание</span><span class="sxs-lookup"><span data-stu-id="144a4-249">Description</span></span>
------------- | -----------
<span data-ttu-id="144a4-250">public</span><span class="sxs-lookup"><span data-stu-id="144a4-250">public</span></span> | <span data-ttu-id="144a4-251">Тип доступен во всех сборках.</span><span class="sxs-lookup"><span data-stu-id="144a4-251">The type is accessible by all assemblies.</span></span>
<span data-ttu-id="144a4-252">сборка</span><span class="sxs-lookup"><span data-stu-id="144a4-252">assembly</span></span> | <span data-ttu-id="144a4-253">Тип доступен только в пределах своей сборки.</span><span class="sxs-lookup"><span data-stu-id="144a4-253">The type is accessible only from within its assembly.</span></span>

<span data-ttu-id="144a4-254">Доступность вложенного типа зависит от домена доступности, который определяется объявленным уровнем доступности члена и доменом доступности непосредственно вмещающего его типа.</span><span class="sxs-lookup"><span data-stu-id="144a4-254">The accessibility of a nested type depends on its accessibility domain, which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="144a4-255">Однако домен доступности вложенного типа не может выходить за границы домена доступности содержащего его типа.</span><span class="sxs-lookup"><span data-stu-id="144a4-255">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>

<span data-ttu-id="144a4-256">Домен доступности вложенного члена `M`, объявленного в типе `T` в рамках программы `P`, определяется следующим образом (при этом `M` также может быть типом):</span><span class="sxs-lookup"><span data-stu-id="144a4-256">The accessibility domain of a nested member `M` declared in a type `T`within a program `P` is defined as follows (noting that `M` might itself be a type):</span></span> 

* <span data-ttu-id="144a4-257">Если объявленный уровень доступности `M` — `public`, то домен доступности `M` совпадает с доменом доступности `T`.</span><span class="sxs-lookup"><span data-stu-id="144a4-257">If the declared accessibility of `M` is `public`, the accessibility domain of `M` is the accessibility domain of `T`.</span></span>

* <span data-ttu-id="144a4-258">Если объявленный уровень доступности `M` — `protected internal`, то домен доступности `M` представляет собой пересечение домена доступности `T` с текстом программы `P` и текстом программ любого типа, производного от `T` и объявленного вне `P`.</span><span class="sxs-lookup"><span data-stu-id="144a4-258">If the declared accessibility of `M` is `protected internal`, the accessibility domain of `M` is the intersection of the accessibility domain of `T` with the program text of `P` and the program text of any type derived from `T` declared outside `P`.</span></span>

* <span data-ttu-id="144a4-259">Если объявленный уровень доступности `M` — `protected`, то домен доступности `M` представляет собой пересечение домена доступности `T` с текстом программы `T` и текстом программы любого типа, производного от `T`.</span><span class="sxs-lookup"><span data-stu-id="144a4-259">If the declared accessibility of `M` is `protected`, the accessibility domain of `M` is the intersection of the accessibility domain of `T` with the program text of `T` and any type derived from `T`.</span></span>

* <span data-ttu-id="144a4-260">Если объявленный уровень доступности `M` — `internal`, то домен доступности `M` представляет собой пересечение домена доступности `T` с текстом программы `P`.</span><span class="sxs-lookup"><span data-stu-id="144a4-260">If the declared accessibility of `M` is `internal`, the accessibility domain of `M` is the intersection of the accessibility domain of `T` with the program text of`P`.</span></span>

* <span data-ttu-id="144a4-261">Если объявленный уровень доступности `M` — `private`, то домен доступности `M` совпадает с текстом программы `T`.</span><span class="sxs-lookup"><span data-stu-id="144a4-261">If the declared accessibility of `M` is `private`, the accessibility domain of `M` is the program text of `T`.</span></span>

### <a name="type-names"></a><span data-ttu-id="144a4-262">Имена типов</span><span class="sxs-lookup"><span data-stu-id="144a4-262">Type names</span></span>

<span data-ttu-id="144a4-263">Система общих типов накладывает на имена только два следующих ограничения.</span><span class="sxs-lookup"><span data-stu-id="144a4-263">The common type system imposes only two restrictions on names:</span></span> 

* <span data-ttu-id="144a4-264">Все имена кодируются в виде строк, состоящих из символов Юникода (16-разрядная кодировка).</span><span class="sxs-lookup"><span data-stu-id="144a4-264">All names are encoded as strings of Unicode (16-bit) characters.</span></span>

* <span data-ttu-id="144a4-265">Имена не могут иметь внедренное (16-разрядное) значение 0x0000.</span><span class="sxs-lookup"><span data-stu-id="144a4-265">Names are not permitted to have an embedded (16-bit) value of 0x0000.</span></span>

<span data-ttu-id="144a4-266">Тем не менее в большинстве языков на имена типов налагаются дополнительные ограничения.</span><span class="sxs-lookup"><span data-stu-id="144a4-266">However, most languages impose additional restrictions on type names.</span></span> <span data-ttu-id="144a4-267">Все сравнения выполняются на побайтовой основе, поэтому в них учитывается регистр, но они не зависят от языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="144a4-267">All comparisons are done on a byte-by-byte basis, and are therefore case-sensitive and locale-independent.</span></span>

<span data-ttu-id="144a4-268">Несмотря на то, что тип может ссылаться на типы из других модулей и сборок, он должен полностью определяться в одном модуле платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="144a4-268">Although a type might reference types from other modules and assemblies, a type must be fully defined within one .NET module.</span></span> <span data-ttu-id="144a4-269">(Тем не менее при поддержке соответствующей возможности в компиляторе он может быть разделен на несколько файлов исходного кода.) Имена типов должны быть уникальными только в пределах пространства имен.</span><span class="sxs-lookup"><span data-stu-id="144a4-269">(Depending on compiler support, however, it can be divided into multiple source code files.) Type names need be unique only within a namespace.</span></span> <span data-ttu-id="144a4-270">Для полной идентификации типа его имя должно квалифицироваться именем пространства имен, в котором содержится реализация этого типа.</span><span class="sxs-lookup"><span data-stu-id="144a4-270">To fully identify a type, the type name must be qualified by the namespace that contains the implementation of the type.</span></span>

### <a name="base-types-and-interfaces"></a><span data-ttu-id="144a4-271">Базовые типы и интерфейсы</span><span class="sxs-lookup"><span data-stu-id="144a4-271">Base types and interfaces</span></span>

<span data-ttu-id="144a4-272">Тип может наследовать значения и поведение другого типа.</span><span class="sxs-lookup"><span data-stu-id="144a4-272">A type can inherit values and behaviors from another type.</span></span> <span data-ttu-id="144a4-273">Система общих типов не разрешает наследование от нескольких базовых типов.</span><span class="sxs-lookup"><span data-stu-id="144a4-273">The common type system does not allow types to inherit from more than one base type.</span></span>

<span data-ttu-id="144a4-274">Тип может реализовывать любое число интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="144a4-274">A type can implement any number of interfaces.</span></span> <span data-ttu-id="144a4-275">Для этого он должен реализовать все виртуальные члены этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="144a4-275">To implement an interface, a type must implement all the virtual members of that interface.</span></span> <span data-ttu-id="144a4-276">Виртуальный метод может быть реализован с помощью производного типа и может вызываться либо статически, либо динамически.</span><span class="sxs-lookup"><span data-stu-id="144a4-276">A virtual method can be implemented by a derived type and can be invoked either statically or dynamically.</span></span>

## <a name="type-members"></a><span data-ttu-id="144a4-277">Члены типов</span><span class="sxs-lookup"><span data-stu-id="144a4-277">Type members</span></span>

<span data-ttu-id="144a4-278">Среда выполнения позволяет определять члены типа, задающих поведение и состояние типа.</span><span class="sxs-lookup"><span data-stu-id="144a4-278">The runtime enables you to define members of your type, which specifies the behavior and state of a type.</span></span> <span data-ttu-id="144a4-279">К членам типа относятся:</span><span class="sxs-lookup"><span data-stu-id="144a4-279">Type members include the following:</span></span>

* [<span data-ttu-id="144a4-280">Поля</span><span class="sxs-lookup"><span data-stu-id="144a4-280">Fields</span></span>](#fields)

* [<span data-ttu-id="144a4-281">Свойства</span><span class="sxs-lookup"><span data-stu-id="144a4-281">Properties</span></span>](#properties)

* [<span data-ttu-id="144a4-282">Методы</span><span class="sxs-lookup"><span data-stu-id="144a4-282">Methods</span></span>](#methods)

* [<span data-ttu-id="144a4-283">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="144a4-283">Constructors</span></span>](#constructors)

* [<span data-ttu-id="144a4-284">События</span><span class="sxs-lookup"><span data-stu-id="144a4-284">Events</span></span>](#events)

* [<span data-ttu-id="144a4-285">Вложенные типы</span><span class="sxs-lookup"><span data-stu-id="144a4-285">Nested types</span></span>](#nested-types)

### <a name="fields"></a><span data-ttu-id="144a4-286">Поля</span><span class="sxs-lookup"><span data-stu-id="144a4-286">Fields</span></span>

<span data-ttu-id="144a4-287">Поле описывает и содержит часть состояния типа.</span><span class="sxs-lookup"><span data-stu-id="144a4-287">A field describes and contains part of the type's state.</span></span> <span data-ttu-id="144a4-288">Поля могут иметь любой тип, поддерживаемый средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="144a4-288">Fields can be of any type supported by the runtime.</span></span> <span data-ttu-id="144a4-289">Поля чаще всего имеют уровень доступности `private` или `protected`, поэтому они доступны только изнутри самого класса или из производных от него классов.</span><span class="sxs-lookup"><span data-stu-id="144a4-289">Most commonly, fields are either `private` or `protected`, so that they are accessible only from within the class or from a derived class.</span></span> <span data-ttu-id="144a4-290">Если значение поля может быть изменено извне его типа, то для этого обычно используется метод доступа набора свойств.</span><span class="sxs-lookup"><span data-stu-id="144a4-290">If the value of a field can be modified from outside its type, a property set accessor is typically used.</span></span> <span data-ttu-id="144a4-291">Открытые поля обычно доступны только для чтения и могут относиться к одному из двух типов:</span><span class="sxs-lookup"><span data-stu-id="144a4-291">Publicly exposed fields are usually read-only and can be of two types:</span></span> 

* <span data-ttu-id="144a4-292">Константы, значение которых задается во время разработки.</span><span class="sxs-lookup"><span data-stu-id="144a4-292">Constants, whose value is assigned at design time.</span></span> <span data-ttu-id="144a4-293">Они являются статическими членами класса, хотя и не определяются с помощью ключевого слова `static` (`Shared` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="144a4-293">These are static members of a class, although they are not defined using the `static` (`Shared` in Visual Basic) keyword.</span></span>

* <span data-ttu-id="144a4-294">Доступные только для чтения переменные, значения которых задаются в конструкторе класса.</span><span class="sxs-lookup"><span data-stu-id="144a4-294">Read-only variables, whose values can be assigned in the class constructor.</span></span>

<span data-ttu-id="144a4-295">В следующем примере демонстрируются эти два способа использования доступных только для чтения полей.</span><span class="sxs-lookup"><span data-stu-id="144a4-295">The following example illustrates these two usages of read-only fields.</span></span>

```csharp
using System;

public class Constants
{
   public const double Pi = 3.1416;
   public readonly DateTime BirthDate;

   public Constants(DateTime birthDate)
   {
      this.BirthDate = birthDate;
   }
}

public class Example
{
   public static void Main()
   {
      Constants con = new Constants(new DateTime(1974, 8, 18));
      Console.Write(Constants.Pi + "\n");
      Console.Write(con.BirthDate.ToString("d") + "\n");
   }
}
// The example displays the following output if run on a system whose current
// culture is en-US:
//    3.1417
//    8/18/1974
```

```vb
Public Class Constants
   Public Const Pi As Double = 3.1416
   Public ReadOnly BirthDate As Date

   Public Sub New(birthDate As Date)
      Me.BirthDate = birthDate
   End Sub
End Class

Public Module Example
   Public Sub Main()
      Dim con As New Constants(#8/18/1974#)
      Console.WriteLine(Constants.Pi.ToString())
      Console.WriteLine(con.BirthDate.ToString("d"))
   End Sub
End Module
' The example displays the following output if run on a system whose current
' culture is en-US:
'    3.1417
'    8/18/1974
```

### <a name="properties"></a><span data-ttu-id="144a4-296">Свойства</span><span class="sxs-lookup"><span data-stu-id="144a4-296">Properties</span></span>

<span data-ttu-id="144a4-297">Свойство задает определенное значение или состояние типа, а также определяет методы получения и установки значения свойства.</span><span class="sxs-lookup"><span data-stu-id="144a4-297">A property names a value or state of the type and defines methods for getting or setting the property's value.</span></span> <span data-ttu-id="144a4-298">Свойства могут быть простыми типами, коллекциями простых типов, пользовательскими типами или коллекциями пользовательских типов.</span><span class="sxs-lookup"><span data-stu-id="144a4-298">Properties can be primitive types, collections of primitive types, user-defined types, or collections of user-defined types.</span></span> <span data-ttu-id="144a4-299">Свойства часто используются, чтобы обеспечить независимость общего интерфейса типа от фактической реализации данного типа.</span><span class="sxs-lookup"><span data-stu-id="144a4-299">Properties are often used to keep the public interface of a type independent from the type's actual representation.</span></span> <span data-ttu-id="144a4-300">Это позволяет представлять с помощью свойств значения, которые не хранятся непосредственно в классе (например, когда свойство возвращает вычисляемое значение), либо выполнять проверку перед присваиванием значений закрытым полям.</span><span class="sxs-lookup"><span data-stu-id="144a4-300">This enables properties to reflect values that are not directly stored in the class (for example, when a property returns a computed value) or to perform validation before values are assigned to private fields.</span></span> <span data-ttu-id="144a4-301">В следующем примере демонстрируется второй вариант.</span><span class="sxs-lookup"><span data-stu-id="144a4-301">The following example illustrates the latter pattern.</span></span>

```csharp
using System;

public class Person
{
   private int m_Age;

   public int Age
   { 
      get { return m_Age; }
      set {
         if (value < 0 || value > 125)
         {
            throw new ArgumentOutOfRangeException("The value of the Age property must be between 0 and 125.");
         }
         else
         {
            m_Age = value;
         }         
      }
   }
}
```

```vb
Public Class Person
   Private m_Age As Integer

   Public Property Age As Integer
      Get
         Return m_Age
      End Get
      Set
         If value < 0 Or value > 125 Then
            Throw New ArgumentOutOfRangeException("The value of the Age property must be between 0 and 125.")
         Else
            m_Age = value
         End If
      End Set
   End Property
End Class
```

<span data-ttu-id="144a4-302">Помимо самого свойства MSIL-код типа, имеющего доступное для чтения свойство, включает метод `get`*_propertyname*, а MSIL-код типа, имеющего доступное для записи свойство, — метод `set`*_propertyname*.</span><span class="sxs-lookup"><span data-stu-id="144a4-302">In addition to including the property itself, the Microsoft intermediate language (MSIL) for a type that contains a readable property includes a `get`*_propertyname* method, and the MSIL for a type that contains a writable property includes a `set`*_propertyname* method.</span></span>

### <a name="methods"></a><span data-ttu-id="144a4-303">Методы</span><span class="sxs-lookup"><span data-stu-id="144a4-303">Methods</span></span>

<span data-ttu-id="144a4-304">Метод описывает операции, доступные в определенном типе.</span><span class="sxs-lookup"><span data-stu-id="144a4-304">A method describes operations that are available on the type.</span></span> <span data-ttu-id="144a4-305">Сигнатура метода указывает допустимые типы всех его параметров и возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="144a4-305">A method's signature specifies the allowable types of all its parameters and of its return value.</span></span>

<span data-ttu-id="144a4-306">Хотя большинство методов определяют точное число параметров, необходимых для вызовов метода, некоторые методы поддерживают переменное число параметров.</span><span class="sxs-lookup"><span data-stu-id="144a4-306">Although most methods define the precise number of parameters required for method calls, some methods support a variable number of parameters.</span></span> <span data-ttu-id="144a4-307">Конечный объявленный параметр этих методов помечается атрибутом [ParamArrayAttribute](xref:System.ParamArrayAttribute).</span><span class="sxs-lookup"><span data-stu-id="144a4-307">The final declared parameter of these methods is marked with the [ParamArrayAttribute](xref:System.ParamArrayAttribute) attribute.</span></span> <span data-ttu-id="144a4-308">Компиляторы языка обычно предоставляют ключевое слово, такое как `params` в C# и `ParamArray` в Visual Basic, которое исключает необходимость явного использования [ParamArrayAttribute](xref:System.ParamArrayAttribute).</span><span class="sxs-lookup"><span data-stu-id="144a4-308">Language compilers typically provide a keyword, such as `params` in C# and `ParamArray` in Visual Basic, that makes explicit use of [ParamArrayAttribute](xref:System.ParamArrayAttribute) unnecessary.</span></span>

### <a name="constructors"></a><span data-ttu-id="144a4-309">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="144a4-309">Constructors</span></span>

<span data-ttu-id="144a4-310">Конструктор — это специальный метод, который служит для создания новых экземпляров класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="144a4-310">A constructor is a special kind of method that creates new instances of a class or structure.</span></span> <span data-ttu-id="144a4-311">Как и любой другой метод, конструктор может иметь параметры, однако у конструкторов отсутствует возвращаемое значение (они возвращают `void`).</span><span class="sxs-lookup"><span data-stu-id="144a4-311">Like any other method, a constructor can include parameters; however, constructors have no return value (that is, they return `void`).</span></span> 

<span data-ttu-id="144a4-312">Если исходный код класса не содержит явного определения конструктора, то компилятор включает заданный по умолчанию конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="144a4-312">If the source code for a class does not explicitly define a constructor, the compiler includes a default (parameterless) constructor.</span></span> <span data-ttu-id="144a4-313">Однако если исходный код класса определяет только параметризованные конструкторы, компилятор C# не создает конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="144a4-313">However, if the source code for a class defines only parameterized constructors, the C# compiler doesn't generate a parameterless constructor.</span></span>

<span data-ttu-id="144a4-314">Если исходный код для структуры определяет конструкторы, они должны быть параметризованы; структура не может определять конструктор по умолчанию (без параметров), и компиляторы не создают конструкторы без параметров для структур и других типов значений.</span><span class="sxs-lookup"><span data-stu-id="144a4-314">If the source code for a structure defines constructors, they must be parameterized; a structure cannot define a default (parameterless) constructor, and compilers do not generate parameterless constructors for structures or other value types.</span></span> <span data-ttu-id="144a4-315">Все типы значений не имеют неявного конструктора, заданного по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="144a4-315">All value types do have an implicit default constructor.</span></span> <span data-ttu-id="144a4-316">Этот конструктор реализован средой CLR и инициализирует все поля структуры, задавая для них значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="144a4-316">This constructor is implemented by the common language runtime and initializes all fields of the structure to their default values.</span></span> 

### <a name="events"></a><span data-ttu-id="144a4-317">События</span><span class="sxs-lookup"><span data-stu-id="144a4-317">Events</span></span>

<span data-ttu-id="144a4-318">Событие определяет происшествие, на которое можно реагировать, а также методы подписки, отказа от подписки или порождения события.</span><span class="sxs-lookup"><span data-stu-id="144a4-318">An event defines an incident that can be responded to, and defines methods for subscribing to, unsubscribing from, and raising the event.</span></span> <span data-ttu-id="144a4-319">События часто используются для оповещения других типов об изменениях состояния.</span><span class="sxs-lookup"><span data-stu-id="144a4-319">Events are often used to inform other types of state changes.</span></span>

### <a name="nested-types"></a><span data-ttu-id="144a4-320">Вложенные типы</span><span class="sxs-lookup"><span data-stu-id="144a4-320">Nested types</span></span>

<span data-ttu-id="144a4-321">Вложенный тип — это тип, являющийся членом какого-либо другого типа.</span><span class="sxs-lookup"><span data-stu-id="144a4-321">A nested type is a type that is a member of some other type.</span></span> <span data-ttu-id="144a4-322">Вложенные типы должны быть тесно связаны со своим вмещающим типом и не должны использоваться в качестве типа общего назначения.</span><span class="sxs-lookup"><span data-stu-id="144a4-322">Nested types should be tightly coupled to their containing type and must not be useful as a general-purpose type.</span></span> <span data-ttu-id="144a4-323">Вложенные типы полезны, когда объявляющий тип использует и создает экземпляры вложенного типа и использование вложенного типа не открывается в публичных членах.</span><span class="sxs-lookup"><span data-stu-id="144a4-323">Nested types are useful when the declaring type uses and creates instances of the nested type, and use of the nested type is not exposed in public members.</span></span>

<span data-ttu-id="144a4-324">Особенности вложенных типов не всегда понятны некоторым разработчикам; эти типы не должны быть открыто видимыми, если существенной причины для подобной видимости не имеется.</span><span class="sxs-lookup"><span data-stu-id="144a4-324">Nested types are confusing to some developers and should not be publicly visible unless there is a compelling reason for visibility.</span></span> <span data-ttu-id="144a4-325">В хорошо спроектированной библиотеке разработчикам редко приходится использовать вложенные типы для создания экземпляров объектов или объявления переменных.</span><span class="sxs-lookup"><span data-stu-id="144a4-325">In a well-designed library, developers should rarely have to use nested types to instantiate objects or declare variables.</span></span>

## <a name="characteristics-of-type-members"></a><span data-ttu-id="144a4-326">Характеристики членов типов</span><span class="sxs-lookup"><span data-stu-id="144a4-326">Characteristics of type members</span></span>

<span data-ttu-id="144a4-327">Система общих типов CTS допускает наличие у членов типов различных характеристик, однако некоторые характеристики могут не поддерживаться в отдельных языках программирования.</span><span class="sxs-lookup"><span data-stu-id="144a4-327">The common type system allows type members to have a variety of characteristics; however, languages are not required to support all these characteristics.</span></span> <span data-ttu-id="144a4-328">В следующей таблице описаны характеристики членов.</span><span class="sxs-lookup"><span data-stu-id="144a4-328">The following table describes member characteristics.</span></span>

<span data-ttu-id="144a4-329">Характеристика</span><span class="sxs-lookup"><span data-stu-id="144a4-329">Characteristic</span></span> | <span data-ttu-id="144a4-330">Применение</span><span class="sxs-lookup"><span data-stu-id="144a4-330">Can apply to</span></span> | <span data-ttu-id="144a4-331">Описание</span><span class="sxs-lookup"><span data-stu-id="144a4-331">Description</span></span>
-------------- | ------------ | -----------
<span data-ttu-id="144a4-332">abstract</span><span class="sxs-lookup"><span data-stu-id="144a4-332">abstract</span></span> | <span data-ttu-id="144a4-333">Методы, свойства и события</span><span class="sxs-lookup"><span data-stu-id="144a4-333">Methods, properties, and events</span></span> | <span data-ttu-id="144a4-334">Тип не предоставляет реализацию метода.</span><span class="sxs-lookup"><span data-stu-id="144a4-334">The type does not supply the method's implementation.</span></span> <span data-ttu-id="144a4-335">Типы, которые наследуют или реализуют абстрактный метод, должны предоставлять реализацию метода.</span><span class="sxs-lookup"><span data-stu-id="144a4-335">Types that inherit or implement abstract methods must supply an implementation for the method.</span></span> <span data-ttu-id="144a4-336">Единственное исключение — когда производный тип является абстрактным.</span><span class="sxs-lookup"><span data-stu-id="144a4-336">The only exception is when the derived type is itself an abstract type.</span></span> <span data-ttu-id="144a4-337">Все абстрактные методы являются виртуальными.</span><span class="sxs-lookup"><span data-stu-id="144a4-337">All abstract methods are virtual.</span></span>
<span data-ttu-id="144a4-338">private</span><span class="sxs-lookup"><span data-stu-id="144a4-338">private</span></span> | <span data-ttu-id="144a4-339">Все</span><span class="sxs-lookup"><span data-stu-id="144a4-339">All</span></span> | <span data-ttu-id="144a4-340">Доступен только изнутри типа, к которому принадлежит член, или изнутри вложенного типа.</span><span class="sxs-lookup"><span data-stu-id="144a4-340">Accessible only from within the same type as the member, or within a nested type.</span></span>
<span data-ttu-id="144a4-341">family</span><span class="sxs-lookup"><span data-stu-id="144a4-341">family</span></span> | <span data-ttu-id="144a4-342">Все</span><span class="sxs-lookup"><span data-stu-id="144a4-342">All</span></span> | <span data-ttu-id="144a4-343">Доступен изнутри типа, к которому принадлежит член, а также из производных от него типов.</span><span class="sxs-lookup"><span data-stu-id="144a4-343">Accessible from within the same type as the member, and from derived types that inherit from it.</span></span>
<span data-ttu-id="144a4-344">assemby</span><span class="sxs-lookup"><span data-stu-id="144a4-344">assemby</span></span> | <span data-ttu-id="144a4-345">Все</span><span class="sxs-lookup"><span data-stu-id="144a4-345">All</span></span> | <span data-ttu-id="144a4-346">Доступен только в сборке, в которой определен тип.</span><span class="sxs-lookup"><span data-stu-id="144a4-346">Accessible only in the assembly in which the type is defined.</span></span>
<span data-ttu-id="144a4-347">family and assembly</span><span class="sxs-lookup"><span data-stu-id="144a4-347">family and assembly</span></span> | <span data-ttu-id="144a4-348">Все</span><span class="sxs-lookup"><span data-stu-id="144a4-348">All</span></span> | <span data-ttu-id="144a4-349">Доступен только в типах с уровнем доступа family и assembly.</span><span class="sxs-lookup"><span data-stu-id="144a4-349">Accessible only from types that qualify for both family and assembly access.</span></span>
<span data-ttu-id="144a4-350">family или assembly</span><span class="sxs-lookup"><span data-stu-id="144a4-350">family or assemby</span></span> | <span data-ttu-id="144a4-351">Все</span><span class="sxs-lookup"><span data-stu-id="144a4-351">All</span></span> | <span data-ttu-id="144a4-352">Доступен только в типах с уровнем доступа либо family, либо assembly.</span><span class="sxs-lookup"><span data-stu-id="144a4-352">Accessible only from types that qualify for either family or assembly access.</span></span>
<span data-ttu-id="144a4-353">public</span><span class="sxs-lookup"><span data-stu-id="144a4-353">public</span></span> | <span data-ttu-id="144a4-354">Все</span><span class="sxs-lookup"><span data-stu-id="144a4-354">All</span></span> | <span data-ttu-id="144a4-355">Доступен в любом типе.</span><span class="sxs-lookup"><span data-stu-id="144a4-355">Accessible from any type.</span></span>
<span data-ttu-id="144a4-356">final</span><span class="sxs-lookup"><span data-stu-id="144a4-356">final</span></span> | <span data-ttu-id="144a4-357">Методы, свойства и события</span><span class="sxs-lookup"><span data-stu-id="144a4-357">Methods, properties, and events</span></span> | <span data-ttu-id="144a4-358">Виртуальный метод нельзя переопределить в производном типе.</span><span class="sxs-lookup"><span data-stu-id="144a4-358">The virtual method cannot be overridden in a derived type.</span></span>
<span data-ttu-id="144a4-359">initialize-only</span><span class="sxs-lookup"><span data-stu-id="144a4-359">initialize-only</span></span> | <span data-ttu-id="144a4-360">Поля</span><span class="sxs-lookup"><span data-stu-id="144a4-360">Fields</span></span> | <span data-ttu-id="144a4-361">Значение можно только инициализировать и невозможно установить после инициализации.</span><span class="sxs-lookup"><span data-stu-id="144a4-361">The value can only be initialized, and cannot be written after initialization.</span></span>
<span data-ttu-id="144a4-362">экземпляр</span><span class="sxs-lookup"><span data-stu-id="144a4-362">instance</span></span> | <span data-ttu-id="144a4-363">Поля, методы, свойства и события</span><span class="sxs-lookup"><span data-stu-id="144a4-363">Fields, methods, properties, and events</span></span> | <span data-ttu-id="144a4-364">Если член не помечен как `static` (C#), `Shared` (Visual Basic), `virtual` (C#) или `Overridable` (Visual Basic), то он является членом экземпляра (ключевое слово instance не используется).</span><span class="sxs-lookup"><span data-stu-id="144a4-364">If a member is not marked as `static` (C#), `Shared` (Visual Basic), `virtual` (C#), or `Overridable` (Visual Basic),  it is an instance member (there is no instance keyword).</span></span> <span data-ttu-id="144a4-365">Копий таких членов в памяти будет столько, сколько объектов их использует.</span><span class="sxs-lookup"><span data-stu-id="144a4-365">There will be as many copies of such members in memory as there are objects that use it.</span></span>
<span data-ttu-id="144a4-366">литерал</span><span class="sxs-lookup"><span data-stu-id="144a4-366">literal</span></span> | <span data-ttu-id="144a4-367">Поля</span><span class="sxs-lookup"><span data-stu-id="144a4-367">Fields</span></span> | <span data-ttu-id="144a4-368">Значение, присвоенное полю, является фиксированным значением встроенного типа значения и становится известным во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="144a4-368">The value assigned to the field is a fixed value, known at compile time, of a built-in value type.</span></span> <span data-ttu-id="144a4-369">Поля литералов иногда называются константами.</span><span class="sxs-lookup"><span data-stu-id="144a4-369">Literal fields are sometimes referred to as constants.</span></span>
<span data-ttu-id="144a4-370">newslot или override</span><span class="sxs-lookup"><span data-stu-id="144a4-370">newslot or override</span></span> | <span data-ttu-id="144a4-371">Все</span><span class="sxs-lookup"><span data-stu-id="144a4-371">All</span></span> | <span data-ttu-id="144a4-372">Определяет способ взаимодействия члена с унаследованными членами, имеющими ту же сигнатуру: `newslot` скрывает унаследованные члены с той же сигнатурой. `override` заменяет определение наследуемого виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="144a4-372">Defines how the member interacts with inherited members that have the same signature: `newslot` hides inherited members that have the same signature; `override` replaces the definition of an inherited virtual method.</span></span> <span data-ttu-id="144a4-373">По умолчанию используется характеристика newslot.</span><span class="sxs-lookup"><span data-stu-id="144a4-373">The default is newslot.</span></span>
<span data-ttu-id="144a4-374">статический</span><span class="sxs-lookup"><span data-stu-id="144a4-374">static</span></span> | <span data-ttu-id="144a4-375">Поля, методы, свойства и события</span><span class="sxs-lookup"><span data-stu-id="144a4-375">Fields, methods, properties, and events</span></span> | <span data-ttu-id="144a4-376">Член принадлежит к типу, в котором он определен, а не к конкретному экземпляру типа. Член существует, даже если экземпляр типа не создан, и является общим для всех экземпляров типа.</span><span class="sxs-lookup"><span data-stu-id="144a4-376">The member belongs to the type it is defined on, not to a particular instance of the type; the member exists even if an instance of the type is not created, and it is shared among all instances of the type.</span></span>
<span data-ttu-id="144a4-377">виртуальный</span><span class="sxs-lookup"><span data-stu-id="144a4-377">virtual</span></span> | <span data-ttu-id="144a4-378">Методы, свойства и события</span><span class="sxs-lookup"><span data-stu-id="144a4-378">Methods, properties, and events</span></span> | <span data-ttu-id="144a4-379">Метод может реализовываться с помощью производного типа и вызываться либо статически, либо динамически.</span><span class="sxs-lookup"><span data-stu-id="144a4-379">The method can be implemented by a derived type and can be invoked either statically or dynamically.</span></span> <span data-ttu-id="144a4-380">Если используется динамический вызов, то вызываемая реализация метода определяется типом экземпляра, выполняющего вызов во время выполнения, а не типом, известным во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="144a4-380">If dynamic invocation is used, the type of the instance that makes the call at run time (rather than the type known at compile time) determines which implementation of the method is called.</span></span> <span data-ttu-id="144a4-381">Для статического вызова виртуального метода может потребоваться приведение переменной к типу, который использует нужную версию метода.</span><span class="sxs-lookup"><span data-stu-id="144a4-381">To invoke a virtual method statically, the variable might have to be cast to a type that uses the desired version of the method.</span></span>

### <a name="overloading"></a><span data-ttu-id="144a4-382">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="144a4-382">Overloading</span></span>

<span data-ttu-id="144a4-383">У каждого члена типа есть уникальная сигнатура.</span><span class="sxs-lookup"><span data-stu-id="144a4-383">Each type member has a unique signature.</span></span> <span data-ttu-id="144a4-384">Сигнатуры методов содержат имя метода и список параметров (порядок и типы аргументов метода).</span><span class="sxs-lookup"><span data-stu-id="144a4-384">Method signatures consist of the method name and a parameter list (the order and types of the method's arguments).</span></span> <span data-ttu-id="144a4-385">В типе можно определить несколько методов с одним именем и разными сигнатурами.</span><span class="sxs-lookup"><span data-stu-id="144a4-385">Multiple methods with the same name can be defined within a type as long as their signatures differ.</span></span> <span data-ttu-id="144a4-386">При этом метод будет называться перегруженным.</span><span class="sxs-lookup"><span data-stu-id="144a4-386">When two or more methods with the same name are defined, the method is said to be overloaded.</span></span> <span data-ttu-id="144a4-387">Например, в [System.Char](xref:System.Char) метод `IsDigit` перегружен.</span><span class="sxs-lookup"><span data-stu-id="144a4-387">For example, in [System.Char](xref:System.Char), the `IsDigit` method is overloaded.</span></span> <span data-ttu-id="144a4-388">Один метод принимает параметр [Char](xref:System.Char).</span><span class="sxs-lookup"><span data-stu-id="144a4-388">One method takes a [Char](xref:System.Char).</span></span> <span data-ttu-id="144a4-389">Другой метод принимает [String](xref:System.String) и [Int32](xref:System.Int32).</span><span class="sxs-lookup"><span data-stu-id="144a4-389">The other method takes a [String](xref:System.String) and an [Int32](xref:System.Int32).</span></span> 

> [!NOTE]
> <span data-ttu-id="144a4-390">Тип возвращаемого значения не считается частью сигнатуры метода.</span><span class="sxs-lookup"><span data-stu-id="144a4-390">The return type is not considered part of a method's signature.</span></span> <span data-ttu-id="144a4-391">Это значит, что методы не могут быть перегружены, если они различаются только типом возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="144a4-391">That is, methods cannot be overloaded if they differ only by return type.</span></span>

### <a name="inheriting-overriding-and-hiding-members"></a><span data-ttu-id="144a4-392">Наследование, переопределение и скрытие членов</span><span class="sxs-lookup"><span data-stu-id="144a4-392">Inheriting, overriding, and hiding members</span></span>

<span data-ttu-id="144a4-393">Производный тип наследует все члены своего базового типа. Эти члены будут определены для производного типа и доступны в нем.</span><span class="sxs-lookup"><span data-stu-id="144a4-393">A derived type inherits all members of its base type; that is, these members are defined on, and available to, the derived type.</span></span> <span data-ttu-id="144a4-394">Поведение или характеристики наследуемых членов можно изменить двумя способами.</span><span class="sxs-lookup"><span data-stu-id="144a4-394">The behavior or qualities of inherited members can be modified in two ways:</span></span> 

* <span data-ttu-id="144a4-395">В производном типе можно скрыть наследуемый член, определив новый член с такой же сигнатурой.</span><span class="sxs-lookup"><span data-stu-id="144a4-395">A derived type can hide an inherited member by defining a new member with the same signature.</span></span> <span data-ttu-id="144a4-396">Это может понадобиться для того, чтобы сделать ранее открытый член закрытым или определить новое поведение для унаследованного метода, помеченного как `final`.</span><span class="sxs-lookup"><span data-stu-id="144a4-396">This might be done to make a previously public member private or to define new behavior for an inherited method that is marked as `final`.</span></span>

* <span data-ttu-id="144a4-397">Производный тип может переопределять наследуемый виртуальный метод.</span><span class="sxs-lookup"><span data-stu-id="144a4-397">A derived type can override an inherited virtual method.</span></span> <span data-ttu-id="144a4-398">Переопределяющий метод предоставляет новое определение метода, который будет вызываться, на основании типа значения во время выполнения, а не типа переменной, известной во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="144a4-398">The overriding method provides a new definition of the method that will be invoked based on the type of the value at run time rather than the type of the variable known at compile time.</span></span> <span data-ttu-id="144a4-399">Метод может переопределить виртуальный метод только в том случае, если виртуальный метод не помечен как `final`, и при этом уровень доступности нового метода не ниже уровня доступности виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="144a4-399">A method can override a virtual method only if the virtual method is not marked as `final` and the new method is at least as accessible as the virtual method.</span></span>

## <a name="see-also"></a><span data-ttu-id="144a4-400">См. также</span><span class="sxs-lookup"><span data-stu-id="144a4-400">See also</span></span>

[<span data-ttu-id="144a4-401">Преобразование типов в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="144a4-401">Type conversion in the .NET Framework</span></span>](type-conversion.md)
