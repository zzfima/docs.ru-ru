---
title: "Ограничения (F#)"
description: "Дополнительные сведения об ограничениях F #, которые применяются для параметров универсального типа для задания требований к аргументу типа в универсальном типе или функции."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2f232a3a-9486-48fb-9759-f23404ed4b52
ms.openlocfilehash: 91854fd2f692688e0f1c27aba1422eff64156048
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="constraints"></a><span data-ttu-id="dc32e-104">Ограничения</span><span class="sxs-lookup"><span data-stu-id="dc32e-104">Constraints</span></span>

<span data-ttu-id="dc32e-105">В этом разделе описываются ограничения, которые можно применить к универсальным параметрам типа для укажите требования для аргумента типа в универсальном типе или функции.</span><span class="sxs-lookup"><span data-stu-id="dc32e-105">This topic describes constraints that you can apply to generic type parameters to specify the requirements for a type argument in a generic type or function.</span></span>


## <a name="syntax"></a><span data-ttu-id="dc32e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc32e-106">Syntax</span></span>

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a><span data-ttu-id="dc32e-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="dc32e-107">Remarks</span></span>
<span data-ttu-id="dc32e-108">Существует несколько различных ограничений, которые можно применять для ограничения типов, которые могут использоваться в универсальном типе.</span><span class="sxs-lookup"><span data-stu-id="dc32e-108">There are several different constraints you can apply to limit the types that can be used in a generic type.</span></span> <span data-ttu-id="dc32e-109">В следующей таблице перечислены и описаны эти ограничения.</span><span class="sxs-lookup"><span data-stu-id="dc32e-109">The following table lists and describes these constraints.</span></span>

|<span data-ttu-id="dc32e-110">Ограничение</span><span class="sxs-lookup"><span data-stu-id="dc32e-110">Constraint</span></span>|<span data-ttu-id="dc32e-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc32e-111">Syntax</span></span>|<span data-ttu-id="dc32e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="dc32e-112">Description</span></span>|
|----------|------|-----------|
|<span data-ttu-id="dc32e-113">Ограничения типа</span><span class="sxs-lookup"><span data-stu-id="dc32e-113">Type Constraint</span></span>|<span data-ttu-id="dc32e-114">*параметр типа* :&gt; *типа*</span><span class="sxs-lookup"><span data-stu-id="dc32e-114">*type-parameter* :&gt; *type*</span></span>|<span data-ttu-id="dc32e-115">Переданный тип должен быть равен или быть производным от типа, указанного или, если тип является интерфейсом, переданный тип должен реализовывать интерфейс.</span><span class="sxs-lookup"><span data-stu-id="dc32e-115">The provided type must be equal to or derived from the type specified, or, if the type is an interface, the provided type must implement the interface.</span></span>|
|<span data-ttu-id="dc32e-116">Ограничение NULL</span><span class="sxs-lookup"><span data-stu-id="dc32e-116">Null Constraint</span></span>|<span data-ttu-id="dc32e-117">*параметр типа* : значение null</span><span class="sxs-lookup"><span data-stu-id="dc32e-117">*type-parameter* : null</span></span>|<span data-ttu-id="dc32e-118">Переданный тип должен поддерживать литералом null.</span><span class="sxs-lookup"><span data-stu-id="dc32e-118">The provided type must support the null literal.</span></span> <span data-ttu-id="dc32e-119">Сюда входят все типы .NET объектов, но не F # список, кортеж, функции, класса, записи или типы объединений.</span><span class="sxs-lookup"><span data-stu-id="dc32e-119">This includes all .NET object types but not F# list, tuple, function, class, record, or union types.</span></span>|
|<span data-ttu-id="dc32e-120">Ограничение явных членов</span><span class="sxs-lookup"><span data-stu-id="dc32e-120">Explicit Member Constraint</span></span>|<span data-ttu-id="dc32e-121">[()]*параметр типа* [или... или *параметр типа*)]: (* сигнатура элемента *)</span><span class="sxs-lookup"><span data-stu-id="dc32e-121">[(]*type-parameter* [or ... or *type-parameter*)] : (*member-signature *)</span></span>|<span data-ttu-id="dc32e-122">Хотя бы один из передаваемых методу аргументов типа должен иметь член, имеющий заданную сигнатуру; не предназначен для широкого использования.</span><span class="sxs-lookup"><span data-stu-id="dc32e-122">At least one of the type arguments provided must have a member that has the specified signature; not intended for common use.</span></span> <span data-ttu-id="dc32e-123">Члены должны быть либо явно определены на быть допустимых целевых объектов для явное ограничение член типа или часть неявный тип расширения.</span><span class="sxs-lookup"><span data-stu-id="dc32e-123">Members must be either explicitly defined on the type or part of an implicit type extension to be valid targets for an Explicit Member Constraint.</span></span>|
|<span data-ttu-id="dc32e-124">Ограничение конструктора</span><span class="sxs-lookup"><span data-stu-id="dc32e-124">Constructor Constraint</span></span>|<span data-ttu-id="dc32e-125">*параметр типа* : (new: единицы -&gt; ")</span><span class="sxs-lookup"><span data-stu-id="dc32e-125">*type-parameter* : ( new : unit -&gt; 'a )</span></span>|<span data-ttu-id="dc32e-126">Переданный тип должен иметь конструктор по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dc32e-126">The provided type must have a default constructor.</span></span>|
|<span data-ttu-id="dc32e-127">Ограничение типа значения</span><span class="sxs-lookup"><span data-stu-id="dc32e-127">Value Type Constraint</span></span>|<span data-ttu-id="dc32e-128">: структура</span><span class="sxs-lookup"><span data-stu-id="dc32e-128">: struct</span></span>|<span data-ttu-id="dc32e-129">Переданный тип должен быть типом значения .NET.</span><span class="sxs-lookup"><span data-stu-id="dc32e-129">The provided type must be a .NET value type.</span></span>|
|<span data-ttu-id="dc32e-130">Ограничение ссылочного типа</span><span class="sxs-lookup"><span data-stu-id="dc32e-130">Reference Type Constraint</span></span>|<span data-ttu-id="dc32e-131">: не структуры</span><span class="sxs-lookup"><span data-stu-id="dc32e-131">: not struct</span></span>|<span data-ttu-id="dc32e-132">Переданный тип должен быть ссылочным типом .NET.</span><span class="sxs-lookup"><span data-stu-id="dc32e-132">The provided type must be a .NET reference type.</span></span>|
|<span data-ttu-id="dc32e-133">Ограничение типа перечисления</span><span class="sxs-lookup"><span data-stu-id="dc32e-133">Enumeration Type Constraint</span></span>|<span data-ttu-id="dc32e-134">: перечисление&lt;*базовый тип*&gt;</span><span class="sxs-lookup"><span data-stu-id="dc32e-134">: enum&lt;*underlying-type*&gt;</span></span>|<span data-ttu-id="dc32e-135">Переданный тип должен быть перечислимый тип с помощью заданного базового типа. не предназначен для широкого использования.</span><span class="sxs-lookup"><span data-stu-id="dc32e-135">The provided type must be an enumerated type that has the specified underlying type; not intended for common use.</span></span>|
|<span data-ttu-id="dc32e-136">Ограничение по делегату</span><span class="sxs-lookup"><span data-stu-id="dc32e-136">Delegate Constraint</span></span>|<span data-ttu-id="dc32e-137">: делегировать&lt;*параметра типа кортежа*, *типа возвращаемого значения*&gt;</span><span class="sxs-lookup"><span data-stu-id="dc32e-137">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span></span>|<span data-ttu-id="dc32e-138">Предоставленный тип должен быть тип делегата, который имеет указанные аргументы и возвращаемое значение; не предназначен для широкого использования.</span><span class="sxs-lookup"><span data-stu-id="dc32e-138">The provided type must be a delegate type that has the specified arguments and return value; not intended for common use.</span></span>|
|<span data-ttu-id="dc32e-139">Ограничение по сравнению</span><span class="sxs-lookup"><span data-stu-id="dc32e-139">Comparison Constraint</span></span>|<span data-ttu-id="dc32e-140">: сравнение</span><span class="sxs-lookup"><span data-stu-id="dc32e-140">: comparison</span></span>|<span data-ttu-id="dc32e-141">Переданный тип должен поддерживать сравнение.</span><span class="sxs-lookup"><span data-stu-id="dc32e-141">The provided type must support comparison.</span></span>|
|<span data-ttu-id="dc32e-142">Ограничение равенства</span><span class="sxs-lookup"><span data-stu-id="dc32e-142">Equality Constraint</span></span>|<span data-ttu-id="dc32e-143">: равенства</span><span class="sxs-lookup"><span data-stu-id="dc32e-143">: equality</span></span>|<span data-ttu-id="dc32e-144">Переданный тип должен поддерживать равенство.</span><span class="sxs-lookup"><span data-stu-id="dc32e-144">The provided type must support equality.</span></span>|
|<span data-ttu-id="dc32e-145">Неуправляемые ограничения</span><span class="sxs-lookup"><span data-stu-id="dc32e-145">Unmanaged Constraint</span></span>|<span data-ttu-id="dc32e-146">: неуправляемые</span><span class="sxs-lookup"><span data-stu-id="dc32e-146">: unmanaged</span></span>|<span data-ttu-id="dc32e-147">Переданный тип должен быть неуправляемого типа.</span><span class="sxs-lookup"><span data-stu-id="dc32e-147">The provided type must be an unmanaged type.</span></span> <span data-ttu-id="dc32e-148">Неуправляемые типы являются некоторых простых типов (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, или `decimal`), типы перечисления `nativeptr&lt;_&gt;`, или не являющимися универсальными структуры, поля которого являются все неуправляемые типы.</span><span class="sxs-lookup"><span data-stu-id="dc32e-148">Unmanaged types are either certain primitive types (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, or `decimal`), enumeration types, `nativeptr&lt;_&gt;`, or a non-generic structure whose fields are all unmanaged types.</span></span>|
<span data-ttu-id="dc32e-149">Необходимо добавить ограничение, когда нужно использовать функцию, которая доступна на тип ограничения, но не для типов в общем коде.</span><span class="sxs-lookup"><span data-stu-id="dc32e-149">You have to add a constraint when your code has to use a feature that is available on the constraint type but not on types in general.</span></span> <span data-ttu-id="dc32e-150">Например при использовании ограничение типа для указания типа класса можно использовать один из методов этого класса в универсальной функции или типа.</span><span class="sxs-lookup"><span data-stu-id="dc32e-150">For example, if you use the type constraint to specify a class type, you can use any one of the methods of that class in the generic function or type.</span></span>

<span data-ttu-id="dc32e-151">Указание ограничений иногда является необходимым при написании параметры типа явно, так как без ограничения, компилятор не может проверить, что компоненты, которые вы используете будут доступны на любой тип, который может быть передан во время выполнения для типа параметр.</span><span class="sxs-lookup"><span data-stu-id="dc32e-151">Specifying constraints is sometimes required when writing type parameters explicitly, because without a constraint, the compiler has no way of verifying that the features that you are using will be available on any type that might be supplied at run time for the type parameter.</span></span>

<span data-ttu-id="dc32e-152">Наиболее распространенные ограничения, которые использовать в коде F # — это ограничения типа, которые задают базовые классы или интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="dc32e-152">The most common constraints you use in F# code are type constraints that specify base classes or interfaces.</span></span> <span data-ttu-id="dc32e-153">Другие ограничения используются в библиотеке F # для реализации определенных функций, таких как ограничения явных членов, которое используется для реализации перегрузки операторов для арифметических операторов, или потому, что F # поддерживает полный предоставляются набор ограничений, поддерживаемый средой CLR.</span><span class="sxs-lookup"><span data-stu-id="dc32e-153">The other constraints are either used by the F# library to implement certain functionality, such as the explicit member constraint, which is used to implement operator overloading for arithmetic operators, or are provided mainly because F# supports the complete set of constraints that is supported by the common language runtime.</span></span>

<span data-ttu-id="dc32e-154">В процессе определения типа некоторые ограничения автоматически выводятся компилятором.</span><span class="sxs-lookup"><span data-stu-id="dc32e-154">During the type inference process, some constraints are inferred automatically by the compiler.</span></span> <span data-ttu-id="dc32e-155">Например, если вы используете `+` оператор в функции, компилятор выводит явных членов ограничения на типы переменных, которые используются в выражении.</span><span class="sxs-lookup"><span data-stu-id="dc32e-155">For example, if you use the `+` operator in a function, the compiler infers an explicit member constraint on variable types that are used in the expression.</span></span>

<span data-ttu-id="dc32e-156">Следующий код иллюстрирует объявления некоторых ограничений.</span><span class="sxs-lookup"><span data-stu-id="dc32e-156">The following code illustrates some constraint declarations.</span></span>

```fsharp
// Base Type Constraint
type Class1<'T when 'T :> System.Exception> =
class end

// Interface Type Constraint
type Class2<'T when 'T :> System.IComparable> = 
class end

// Null constraint
type Class3<'T when 'T : null> =
class end

// Member constraint with static member
type Class4<'T when 'T : (static member staticMethod1 : unit -> 'T) > =
class end

// Member constraint with instance member
type Class5<'T when 'T : (member Method1 : 'T -> int)> =
class end

// Member constraint with property
type Class6<'T when 'T : (member Property1 : int)> =
class end

// Constructor constraint
type Class7<'T when 'T : (new : unit -> 'T)>() =
member val Field = new 'T()

// Reference type constraint
type Class8<'T when 'T : not struct> =
class end

// Enumeration constraint with underlying value specified
type Class9<'T when 'T : enum<uint32>> =
class end

// 'T must implement IComparable, or be an array type with comparable
// elements, or be System.IntPtr or System.UIntPtr. Also, 'T must not have
// the NoComparison attribute.
type Class10<'T when 'T : comparison> =
class end

// 'T must support equality. This is true for any type that does not
// have the NoEquality attribute.
type Class11<'T when 'T : equality> =
class end

type Class12<'T when 'T : delegate<obj * System.EventArgs, unit>> =
class end

type Class13<'T when 'T : unmanaged> =
class end

// Member constraints with two type parameters
// Most often used with static type parameters in inline functions
let inline add(value1 : ^T when ^T : (static member (+) : ^T * ^T -> ^T), value2: ^T) =
value1 + value2

// ^T and ^U must support operator +
let inline heterogenousAdd(value1 : ^T when (^T or ^U) : (static member (+) : ^T * ^U -> ^T), value2 : ^U) =
value1 + value2

// If there are multiple constraints, use the and keyword to separate them.
type Class14<'T,'U when 'T : equality and 'U : equality> =
class end
```

## <a name="see-also"></a><span data-ttu-id="dc32e-157">См. также</span><span class="sxs-lookup"><span data-stu-id="dc32e-157">See Also</span></span>
[<span data-ttu-id="dc32e-158">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="dc32e-158">Generics</span></span>](index.md)

[<span data-ttu-id="dc32e-159">Ограничения</span><span class="sxs-lookup"><span data-stu-id="dc32e-159">Constraints</span></span>](constraints.md)
