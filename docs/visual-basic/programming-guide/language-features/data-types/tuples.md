---
title: "Кортежи в Visual Basic"
ms.custom: 
ms.date: 04/23/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2653b9dc8a6ecbcb718c20be8bd6275edf4cfb6e
ms.sourcegitcommit: be1fb5d9447ad459bef22b91a91c72e3e0b2d916
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2018
---
# <a name="tuples-visual-basic"></a><span data-ttu-id="a62bb-102">Кортежи (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a62bb-102">Tuples (Visual Basic)</span></span>

<span data-ttu-id="a62bb-103">Начиная с Visual Basic 2017 г., в языке Visual Basic предлагает встроенную поддержку кортежей, который делает создание кортежей и доступ к элементам проще кортежей.</span><span class="sxs-lookup"><span data-stu-id="a62bb-103">Starting with Visual Basic 2017, the Visual Basic language offers built-in support for tuples that makes creating tuples and accessing the elements of tuples easier.</span></span> <span data-ttu-id="a62bb-104">Кортеж — это структура данных недоступно, с определенным номером и последовательность значений.</span><span class="sxs-lookup"><span data-stu-id="a62bb-104">A tuple is a light-weight data structure that has a specific number and sequence of values.</span></span> <span data-ttu-id="a62bb-105">При создании экземпляра кортежа, следует определить, количество и тип данных каждого значения (или элемент).</span><span class="sxs-lookup"><span data-stu-id="a62bb-105">When you instantiate the tuple, you define the number and the data type of each value (or element).</span></span> <span data-ttu-id="a62bb-106">Например кортеж (или пары) состоит из двух элементов.</span><span class="sxs-lookup"><span data-stu-id="a62bb-106">For example, a 2-tuple (or pair) has two elements.</span></span> <span data-ttu-id="a62bb-107">Возможно, первый `Boolean` значение, а второй — `String`.</span><span class="sxs-lookup"><span data-stu-id="a62bb-107">The first might be a `Boolean` value, while the second is a `String`.</span></span> <span data-ttu-id="a62bb-108">Поскольку кортежей упростить процесс сохранения нескольких значений в одном объекте, они часто используются как упрощенный способ возвращать несколько значений из метода.</span><span class="sxs-lookup"><span data-stu-id="a62bb-108">Because tuples make it easy to store multiple values in a single object, they are often used as a lightweight way to return multiple values from a method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a62bb-109">Поддержка кортежа требует <xref:System.ValueTuple> типа.</span><span class="sxs-lookup"><span data-stu-id="a62bb-109">Tuple support requires the <xref:System.ValueTuple> type.</span></span> <span data-ttu-id="a62bb-110">Если 4.7 .NET Framework не установлена, необходимо добавить пакет NuGet `System.ValueTuple`, который можно найти в коллекции NuGet.</span><span class="sxs-lookup"><span data-stu-id="a62bb-110">If the .NET Framework 4.7 is not installed, you must add the NuGet package `System.ValueTuple`, which is available on the NuGet Gallery.</span></span> <span data-ttu-id="a62bb-111">Без этого пакета может получить ошибку компиляции аналогично «Предопределенный тип «ValueTuple(Of,,,)» не определен и не импортирован.»</span><span class="sxs-lookup"><span data-stu-id="a62bb-111">Without this package, you may get a compilation error similar to, "Predefined type 'ValueTuple(Of,,,)' is not defined or imported."</span></span>

## <a name="instantiating-and-using-a-tuple"></a><span data-ttu-id="a62bb-112">Создание и использование кортежа</span><span class="sxs-lookup"><span data-stu-id="a62bb-112">Instantiating and using a tuple</span></span>

<span data-ttu-id="a62bb-113">Создать кортеж, заключив его круглые скобки обмена мгновенными сообщениями значений с разделителями запятыми.</span><span class="sxs-lookup"><span data-stu-id="a62bb-113">You instantiate a tuple by enclosing its comma-delimited values im parentheses.</span></span> <span data-ttu-id="a62bb-114">Затем каждый из этих значений становится полем кортежа.</span><span class="sxs-lookup"><span data-stu-id="a62bb-114">Each of those values then becomes a field of the tuple.</span></span> <span data-ttu-id="a62bb-115">Например, следующий код определяет triple (или кортежа 3) с помощью `Date` как значение его первого, `String` его вторым и `Boolean` как третьего.</span><span class="sxs-lookup"><span data-stu-id="a62bb-115">For example, the following code defines a triple (or 3-tuple) with a `Date` as its first value, a `String` as its second, and a `Boolean` as its third.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

<span data-ttu-id="a62bb-116">По умолчанию имя каждого поля в кортеж включает строку `Item` вместе с положением на основе одного поля в кортеже.</span><span class="sxs-lookup"><span data-stu-id="a62bb-116">By default, the name of each field in a tuple consists of the string `Item` along with the field's one-based position in the tuple.</span></span> <span data-ttu-id="a62bb-117">Для 3-кортежа `Date` поле является `Item1`, `String` поле является `Item2`и `Boolean` поле является `Item3`.</span><span class="sxs-lookup"><span data-stu-id="a62bb-117">For this 3-tuple, the `Date` field is `Item1`, the `String` field is `Item2`, and the `Boolean` field is `Item3`.</span></span> <span data-ttu-id="a62bb-118">Следующий пример отображает значения полей кортежа, созданный в предыдущей строке кода</span><span class="sxs-lookup"><span data-stu-id="a62bb-118">The following example displays the values of fields of the tuple instantiated in the previous line of code</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

<span data-ttu-id="a62bb-119">Поля кортеж Visual Basic, чтения и записи; После создания экземпляра кортеж его значения можно изменить.</span><span class="sxs-lookup"><span data-stu-id="a62bb-119">The fields of a Visual Basic tuple are read-write; after you've instantiated a tuple, you can modify its values.</span></span> <span data-ttu-id="a62bb-120">Следующий пример изменяет две из трех полей кортежа, созданные в предыдущем примере и отображает результат.</span><span class="sxs-lookup"><span data-stu-id="a62bb-120">The following example modifies two of the three fields of the tuple created in the previous example and displays the result.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a><span data-ttu-id="a62bb-121">Создание экземпляра и использование именованных кортежа</span><span class="sxs-lookup"><span data-stu-id="a62bb-121">Instantiating and using a named tuple</span></span>

<span data-ttu-id="a62bb-122">Вместо того чтобы использовать имена по умолчанию для полей кортежа, можно создать экземпляр *кортеж с именем* , назначив собственные имена элементов кортежа.</span><span class="sxs-lookup"><span data-stu-id="a62bb-122">Rather than using default names for a tuple's fields, you can instantiate a *named tuple* by assigning your own names to the tuple's elements.</span></span> <span data-ttu-id="a62bb-123">Поля кортежа может осуществляться по именам и назначенный *или* , их имена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a62bb-123">The tuple's fields can then be accessed by their assigned names *or* by their default names.</span></span> <span data-ttu-id="a62bb-124">В следующем примере создается же кортеж 3 как ранее, за исключением того, что она явно указана первое поле `EventDate`, второй `Name`, а в третьем `IsHoliday`.</span><span class="sxs-lookup"><span data-stu-id="a62bb-124">The following example instantiates the same 3-tuple as previously, except that it explicitly names the first field `EventDate`, the second `Name`, and the third `IsHoliday`.</span></span> <span data-ttu-id="a62bb-125">Затем он отображает значения полей, изменяет их и отображает значения полей еще раз.</span><span class="sxs-lookup"><span data-stu-id="a62bb-125">It then displays the field values, modifies them, and displays the field values again.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="a62bb-126">Имена элементов выводимых кортежа</span><span class="sxs-lookup"><span data-stu-id="a62bb-126">Inferred tuple element names</span></span>

<span data-ttu-id="a62bb-127">Начиная с 15,3 Visual Basic, Visual Basic могут выводить имена элементов кортежа; необходимо назначить их явно.</span><span class="sxs-lookup"><span data-stu-id="a62bb-127">Starting with Visual Basic 15.3, Visual Basic can infer the names of tuple elements; you do not have to assign them explicitly.</span></span> <span data-ttu-id="a62bb-128">Выводимый кортежа имена полезны в тех случаях, когда инициализировать кортежа из набора переменных, и требуется имя элемента кортежа должен совпадать с именем переменной.</span><span class="sxs-lookup"><span data-stu-id="a62bb-128">Inferred tuple names are useful when you initialize a tuple from a set of variables, and you want the tuple element name to be the same as the variable name.</span></span> 

<span data-ttu-id="a62bb-129">В следующем примере создается `stateInfo` кортеж, содержащий три явно именованные элементы, `state`, `stateName`, и `capital`.</span><span class="sxs-lookup"><span data-stu-id="a62bb-129">The following example creates a `stateInfo` tuple that contains three explicitly named elements, `state`, `stateName`, and `capital`.</span></span> <span data-ttu-id="a62bb-130">Обратите внимание, что при именовании элементы, оператор инициализации кортежа просто назначает именованных элементов значения переменных таким же именем.</span><span class="sxs-lookup"><span data-stu-id="a62bb-130">Note that, in naming the elements, the tuple initialization statement simply assigns the named elements the values of the identically named variables.</span></span>

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]
 
<span data-ttu-id="a62bb-131">Поскольку элементы и переменные имеют то же имя, компилятор Visual Basic может определить имена полей, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a62bb-131">Because elements and variables have the same name, the Visual Basic compiler can infer the names of the fields, as the following example shows.</span></span>

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

<span data-ttu-id="a62bb-132">Чтобы включить имена элементов interred кортеж, необходимо определить версии компилятора Visual Basic для использования в проекте Visual Basic (\*.vbproj) файла:</span><span class="sxs-lookup"><span data-stu-id="a62bb-132">To enable interred tuple element names, you must define the version of the Visual Basic compiler to use in your Visual Basic project (\*.vbproj) file:</span></span> 

```xml 
<PropertyGroup> 
  <LangVersion>15.3</LangVersion> 
</PropertyGroup> 

The version number can be any version of the Visual Basic compiler starting with 15.3. Rather than hard-coding a specific compiler version, you can also specify "Latest" as the value of `LangVersion` to compile with the most recent version of the Visual Basic compiler installed on your system.

In some cases, the Visual Basic compiler cannot infer the tuple element name from the candidate name, and the tuple field can only be referenced using its default name, such as `Item1`, `Item2`, etc. These include:

- The candidate name is the same as the name of a tuple member, such as `Item3`, `Rest`, or `ToString`.

- The candidate name is duplicated in the tuple.
 
When field name inference fails, Visual Basic does not generate a compiler error, nor is an exception thrown at runtime. Instead, tuple fields must be referenced by their predefined names, such as `Item1` and `Item2`. 
  
## Tuples versus structures

A Visual Basic tuple is a value type that is an instance of one of the a **System.ValueTuple** generic types. For example, the `holiday` tuple defined in the previous example is an instance of the <xref:System.ValueTuple%603> structure. It is designed to be a lightweight container for data. Since the tuple aims to make it easy to create an object with multiple data items, it lacks some of the features that a custom structure might have. These include:

- Customer members. You cannot define your own properties, methods, or events for a tuple.

- Validation. You cannot validate the data assigned to fields.

- Immutability. Visual Basic tuples are mutable. In contrast, a custom structure allows you to control whether an instance is mutable or immutable.

If custom members, property and field validation, or immutability are important, you should use the Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) statement to define a custom value type.

A Visual Basic tuple does inherit the members of its **ValueTuple** type. In addition to its fields, these include the following methods:

| Member | Description |
| ---|---|
| CompareTo | Compares the current tuple to another tuple with the same number of elements. |
| Equals | Determines whether the current tuple is equal to another tuple or object. |
| GetHashCode | Calculates the hash code for the current instance. |
| ToString | Returns the string representation of this tuple, which takes the form `(Item1, Item2...)`, where `Item1` and `Item2` represent the values of the tuple's fields. |

In addition, the **ValueTuple** types implement <xref:System.Collections.IStructuralComparable> and <xref:System.Collections.IStructuralEquatable> interfaces, which allow you to define customer comparers.

## Assignment and tuples

Visual Basic supports assignment between tuple types that have the same number of fields. The field types can be converted if one of the following is true:

- The source and target field are of the same type.

- A widening (or implicit) conversion of the source type to the target type is defined. 

- `Option Strict` is `On`, and a narrowing (or explicit) conversion of the source type to the target type is defined. This conversion can throw an exception if the source value is outside the range of the target type.

Other conversions are not considered for assignments. Let's look at the kinds of assignments that are allowed between tuple types.

Consider these variables used in the following examples:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

The first two variables, `unnamed` and `anonymous`, do not have semantic names provided for the fields. Their field names are the default `Item1` and `Item2`. The last two variables, `named` and `differentName` have semantic field names. Note that these two tuples have different names for the fields.

All four of these tuples have the same number of fields (referred to as 'arity'), and the types of those fields are identical. Therefore, all of these assignments work:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

Notice that the names of the tuples are not assigned. The values of the fields are assigned following the order of the fields in the tuple.

Finally, notice that we can assign the `named` tuple to the `conversion` tuple, even though the first field of `named` is an `Integer`, and the first field of `conversion` is a `Long`. This assignment succeeds because converting an `Integer` to a `Long` is a widening conversion.

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

Tuples with different numbers of fields are not assignable:

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a><span data-ttu-id="a62bb-133">Кортежи как возвращаемые значения методов</span><span class="sxs-lookup"><span data-stu-id="a62bb-133">Tuples as method return values</span></span>

<span data-ttu-id="a62bb-134">Метод может возвращать только одно значение.</span><span class="sxs-lookup"><span data-stu-id="a62bb-134">A method can return only a single value.</span></span> <span data-ttu-id="a62bb-135">Часто хотя вам бы хотелось вызов метода для возврата нескольких значений.</span><span class="sxs-lookup"><span data-stu-id="a62bb-135">Frequently, though, you'd like a method call to return multiple values.</span></span> <span data-ttu-id="a62bb-136">Чтобы обойти это ограничение несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="a62bb-136">There are several ways to work around this limitation:</span></span>

- <span data-ttu-id="a62bb-137">Можно создать пользовательский класс или структуру, свойства или поля представляют значения, возвращаемого методом.</span><span class="sxs-lookup"><span data-stu-id="a62bb-137">You can create a custom class or structure whose properties or fields represent values returned by the method.</span></span> <span data-ttu-id="a62bb-138">Таким образом — это решение высокой плотности; необходимо определить пользовательский тип которого предназначен только для извлечения значений из вызова метода.</span><span class="sxs-lookup"><span data-stu-id="a62bb-138">Thus is a heavyweight solution; it requires that you define a custom type whose only purpose is to retrieve values from a method call.</span></span>

- <span data-ttu-id="a62bb-139">Возвращает одно значение из метода и возврата оставшиеся значения, передавая их по ссылке в метод.</span><span class="sxs-lookup"><span data-stu-id="a62bb-139">You can return a single value from the method, and return the remaining values by passing them by reference to the method.</span></span> <span data-ttu-id="a62bb-140">Это включает в себя дополнительную нагрузку, связанную с создания экземпляра переменной и риски при перезаписи значение переменной, которая передается по ссылке.</span><span class="sxs-lookup"><span data-stu-id="a62bb-140">This involves the overhead of instantiating a variable and risks inadvertently overwriting the value of the variable that you pass by reference.</span></span>

- <span data-ttu-id="a62bb-141">Можно использовать кортеж, который предоставляет простое решение для извлечения с несколькими возвращаемыми значениями.</span><span class="sxs-lookup"><span data-stu-id="a62bb-141">You can use a tuple, which provides a lightweight solution to retrieving multiple return values.</span></span>

<span data-ttu-id="a62bb-142">Например **TryParse** методы возврата .NET `Boolean` значение, указывающее, успешно ли выполнена операция синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="a62bb-142">For example, the **TryParse** methods in .NET return a `Boolean` value that indicates whether the parsing operation succeeded.</span></span> <span data-ttu-id="a62bb-143">Результат операции анализа возвращается в переменную, передаваемый по ссылке в метод.</span><span class="sxs-lookup"><span data-stu-id="a62bb-143">The result of the parsing operation is returned in a variable passed by reference to the method.</span></span> <span data-ttu-id="a62bb-144">Как правило, вызов метода анализа, такие как <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a62bb-144">Normally, a call to the a parsing method such as <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> looks like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

<span data-ttu-id="a62bb-145">Мы можем вернуться кортеж из операции анализа, если мы программу-оболочку вызова <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> в нашей методе.</span><span class="sxs-lookup"><span data-stu-id="a62bb-145">We can return a tuple from the parsing operation if we wrap the call to the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method in our own method.</span></span> <span data-ttu-id="a62bb-146">В следующем примере `NumericLibrary.ParseInteger` вызовы <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> метод и возвращает кортеж, именованный с двумя элементами.</span><span class="sxs-lookup"><span data-stu-id="a62bb-146">In the following example, `NumericLibrary.ParseInteger` calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method and returns a named tuple with two elements.</span></span> 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

<span data-ttu-id="a62bb-147">Затем можно вызвать метод с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="a62bb-147">You can then call the method with code like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a><span data-ttu-id="a62bb-148">Visual Basic кортежи и кортежи в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a62bb-148">Visual Basic tuples and tuples in the .NET Framework</span></span>

<span data-ttu-id="a62bb-149">Visual Basic кортеж представляет собой экземпляр одного из **System.ValueTuple** универсальных типов, которые впервые появились в .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="a62bb-149">A Visual Basic tuple is an instance of one of the **System.ValueTuple** generic types, which were introduced in the .NET Framework 4.7.</span></span> <span data-ttu-id="a62bb-150">Платформа .NET Framework также включает набор универсального **System.Tuple** классы.</span><span class="sxs-lookup"><span data-stu-id="a62bb-150">The .NET Framework also includes a set of generic **System.Tuple** classes.</span></span> <span data-ttu-id="a62bb-151">Эти классы тем не менее, отличаются от кортежей Visual Basic и **System.ValueTuple** универсальных типов в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="a62bb-151">These classes, however, differ from Visual Basic tuples and the **System.ValueTuple** generic types in a number of ways:</span></span>

- <span data-ttu-id="a62bb-152">Элементы **кортежа** классы являются свойства с именем `Item1`, `Item2`, и т. д.</span><span class="sxs-lookup"><span data-stu-id="a62bb-152">The elements of the **Tuple** classes are properties named `Item1`, `Item2`, and so on.</span></span> <span data-ttu-id="a62bb-153">В Visual Basic кортежей и **ValueTuple** поля, типы элементов кортежа.</span><span class="sxs-lookup"><span data-stu-id="a62bb-153">In Visual Basic tuples and the **ValueTuple** types, tuple elements are fields.</span></span>

- <span data-ttu-id="a62bb-154">Элементы нельзя назначить значимые имена **кортежа** экземпляра или **ValueTuple** экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a62bb-154">You cannot assign meaningful names to the elements of a **Tuple** instance or of a **ValueTuple** instance.</span></span> <span data-ttu-id="a62bb-155">Visual Basic позволяет присваивать имена, которые смысловое значение поля.</span><span class="sxs-lookup"><span data-stu-id="a62bb-155">Visual Basic allows you to assign names that communicate the meaning of the fields.</span></span>

- <span data-ttu-id="a62bb-156">Свойства **кортежа** экземпляра доступны только для чтения; кортежи являются неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="a62bb-156">The properties of a **Tuple** instance are read-only; the tuples are immutable.</span></span> <span data-ttu-id="a62bb-157">В Visual Basic кортежей и **ValueTuple** типы, поля кортежа, чтения и записи; кортежи может изменяться.</span><span class="sxs-lookup"><span data-stu-id="a62bb-157">In Visual Basic tuples and the **ValueTuple** types, tuple fields are read-write; the tuples are mutable.</span></span>

- <span data-ttu-id="a62bb-158">Универсальный **кортежа** типы являются ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="a62bb-158">The generic **Tuple** types are reference types.</span></span> <span data-ttu-id="a62bb-159">Используя эти **кортежа** типы означает выделение объектов.</span><span class="sxs-lookup"><span data-stu-id="a62bb-159">Using these **Tuple** types means allocating objects.</span></span> <span data-ttu-id="a62bb-160">В критических путях это может заметно влиять на производительность приложения.</span><span class="sxs-lookup"><span data-stu-id="a62bb-160">On hot paths, this can have a measurable impact on your application's performance.</span></span> <span data-ttu-id="a62bb-161">Visual Basic кортежей и **ValueTuple** типы являются типами значений.</span><span class="sxs-lookup"><span data-stu-id="a62bb-161">Visual Basic tuples and the **ValueTuple** types are value types.</span></span>

<span data-ttu-id="a62bb-162">Методы расширения в <xref:System.TupleExtensions> класс облегчить преобразование между кортежи Visual Basic и .NET **кортежа** объектов.</span><span class="sxs-lookup"><span data-stu-id="a62bb-162">Extension methods in the <xref:System.TupleExtensions> class make it easy to convert between Visual Basic tuples and .NET **Tuple** objects.</span></span> <span data-ttu-id="a62bb-163">**ToTuple** метод преобразует кортеж Visual Basic .NET **кортежа** объекта и **ToValueTuple** метод преобразует .NET **кортежа** Объект кортежа Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a62bb-163">The **ToTuple** method converts a Visual Basic tuple to a .NET **Tuple** object, and the **ToValueTuple** method converts a .NET **Tuple** object to a Visual Basic tuple.</span></span>

<span data-ttu-id="a62bb-164">Следующий пример создает кортеж, преобразует его в .NET **кортежа** объекта и преобразует его обратно кортеж Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a62bb-164">The following example creates a tuple, converts it to a .NET **Tuple** object, and converts it back to a Visual Basic tuple.</span></span> <span data-ttu-id="a62bb-165">Затем в примере сравнивается этот кортеж исходной версией, чтобы убедиться, что они равны.</span><span class="sxs-lookup"><span data-stu-id="a62bb-165">The example then compares this tuple with the original one to ensure that they are equal.</span></span>

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a><span data-ttu-id="a62bb-166">См. также</span><span class="sxs-lookup"><span data-stu-id="a62bb-166">See also</span></span>

[<span data-ttu-id="a62bb-167">Справочник по языку Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a62bb-167">Visual Basic Language Reference</span></span>](index.md)  
