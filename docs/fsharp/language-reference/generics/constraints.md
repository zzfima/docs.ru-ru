---
title: Ограничения (F#)
description: 'Дополнительные сведения о F # ограничений, относящихся к параметров универсального типа для задания требований к аргументу типа в универсальном типе или функции.'
ms.date: 05/16/2016
ms.openlocfilehash: 9534db4ffd195022366af8c993658bd94f375f53
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2018
ms.locfileid: "45675890"
---
# <a name="constraints"></a><span data-ttu-id="9af5c-103">Ограничения</span><span class="sxs-lookup"><span data-stu-id="9af5c-103">Constraints</span></span>

<span data-ttu-id="9af5c-104">В этом разделе описываются ограничения, которые можно применять к универсальным введите параметры для задания требований к аргументу типа в универсальном типе или функции.</span><span class="sxs-lookup"><span data-stu-id="9af5c-104">This topic describes constraints that you can apply to generic type parameters to specify the requirements for a type argument in a generic type or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="9af5c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9af5c-105">Syntax</span></span>

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a><span data-ttu-id="9af5c-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="9af5c-106">Remarks</span></span>

<span data-ttu-id="9af5c-107">Существует несколько ограничений, которые можно применить ограничивает типы, которые могут использоваться в универсальном типе.</span><span class="sxs-lookup"><span data-stu-id="9af5c-107">There are several different constraints you can apply to limit the types that can be used in a generic type.</span></span> <span data-ttu-id="9af5c-108">В следующей таблице перечислены и описаны эти ограничения.</span><span class="sxs-lookup"><span data-stu-id="9af5c-108">The following table lists and describes these constraints.</span></span>

|<span data-ttu-id="9af5c-109">Ограничение</span><span class="sxs-lookup"><span data-stu-id="9af5c-109">Constraint</span></span>|<span data-ttu-id="9af5c-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9af5c-110">Syntax</span></span>|<span data-ttu-id="9af5c-111">Описание</span><span class="sxs-lookup"><span data-stu-id="9af5c-111">Description</span></span>|
|----------|------|-----------|
|<span data-ttu-id="9af5c-112">Ограничения типа</span><span class="sxs-lookup"><span data-stu-id="9af5c-112">Type Constraint</span></span>|<span data-ttu-id="9af5c-113">*параметр типа* :&gt; *типа*</span><span class="sxs-lookup"><span data-stu-id="9af5c-113">*type-parameter* :&gt; *type*</span></span>|<span data-ttu-id="9af5c-114">Указанный тип должен быть равным или быть производным от указанного типа или, если тип является интерфейсом, предоставленный тип должен реализовывать интерфейс.</span><span class="sxs-lookup"><span data-stu-id="9af5c-114">The provided type must be equal to or derived from the type specified, or, if the type is an interface, the provided type must implement the interface.</span></span>|
|<span data-ttu-id="9af5c-115">Ограничение NULL</span><span class="sxs-lookup"><span data-stu-id="9af5c-115">Null Constraint</span></span>|<span data-ttu-id="9af5c-116">*параметр типа* : null</span><span class="sxs-lookup"><span data-stu-id="9af5c-116">*type-parameter* : null</span></span>|<span data-ttu-id="9af5c-117">Переданный тип должен поддерживать литерал null.</span><span class="sxs-lookup"><span data-stu-id="9af5c-117">The provided type must support the null literal.</span></span> <span data-ttu-id="9af5c-118">Сюда входят все типы объектов .NET, но не F # список, кортежа, функции, класса, записи или типы объединений.</span><span class="sxs-lookup"><span data-stu-id="9af5c-118">This includes all .NET object types but not F# list, tuple, function, class, record, or union types.</span></span>|
|<span data-ttu-id="9af5c-119">Ограничение явных членов</span><span class="sxs-lookup"><span data-stu-id="9af5c-119">Explicit Member Constraint</span></span>|<span data-ttu-id="9af5c-120">[(]*параметр типа* [или... или *параметр типа*)]: (*сигнатура члена*)</span><span class="sxs-lookup"><span data-stu-id="9af5c-120">[(]*type-parameter* [or ... or *type-parameter*)] : (*member-signature*)</span></span>|<span data-ttu-id="9af5c-121">Хотя бы один из переданных аргументов типа должен иметь член, имеющий указанную подпись; не предназначен для общего пользования.</span><span class="sxs-lookup"><span data-stu-id="9af5c-121">At least one of the type arguments provided must have a member that has the specified signature; not intended for common use.</span></span> <span data-ttu-id="9af5c-122">Члены должны быть либо явно определены в тип или частью неявный тип расширения, чтобы быть допустимыми целевыми объектами для явное ограничение члена.</span><span class="sxs-lookup"><span data-stu-id="9af5c-122">Members must be either explicitly defined on the type or part of an implicit type extension to be valid targets for an Explicit Member Constraint.</span></span>|
|<span data-ttu-id="9af5c-123">Ограничение конструктора</span><span class="sxs-lookup"><span data-stu-id="9af5c-123">Constructor Constraint</span></span>|<span data-ttu-id="9af5c-124">*параметр типа* : (новых: единица -&gt; ")</span><span class="sxs-lookup"><span data-stu-id="9af5c-124">*type-parameter* : ( new : unit -&gt; 'a )</span></span>|<span data-ttu-id="9af5c-125">Указанный тип должен иметь конструктор по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9af5c-125">The provided type must have a default constructor.</span></span>|
|<span data-ttu-id="9af5c-126">Ограничение типа значения</span><span class="sxs-lookup"><span data-stu-id="9af5c-126">Value Type Constraint</span></span>|<span data-ttu-id="9af5c-127">: структура</span><span class="sxs-lookup"><span data-stu-id="9af5c-127">: struct</span></span>|<span data-ttu-id="9af5c-128">Указанный тип должен быть типом значения .NET.</span><span class="sxs-lookup"><span data-stu-id="9af5c-128">The provided type must be a .NET value type.</span></span>|
|<span data-ttu-id="9af5c-129">Ограничение ссылочного типа</span><span class="sxs-lookup"><span data-stu-id="9af5c-129">Reference Type Constraint</span></span>|<span data-ttu-id="9af5c-130">: не структуры</span><span class="sxs-lookup"><span data-stu-id="9af5c-130">: not struct</span></span>|<span data-ttu-id="9af5c-131">Переданный тип должен быть ссылочным типом .NET.</span><span class="sxs-lookup"><span data-stu-id="9af5c-131">The provided type must be a .NET reference type.</span></span>|
|<span data-ttu-id="9af5c-132">Ограничение типа перечисления</span><span class="sxs-lookup"><span data-stu-id="9af5c-132">Enumeration Type Constraint</span></span>|<span data-ttu-id="9af5c-133">: перечисление&lt;*базовый тип*&gt;</span><span class="sxs-lookup"><span data-stu-id="9af5c-133">: enum&lt;*underlying-type*&gt;</span></span>|<span data-ttu-id="9af5c-134">Указанный тип должен быть перечислимый тип с указанным базовым типом; не предназначен для общего пользования.</span><span class="sxs-lookup"><span data-stu-id="9af5c-134">The provided type must be an enumerated type that has the specified underlying type; not intended for common use.</span></span>|
|<span data-ttu-id="9af5c-135">Ограничения делегата</span><span class="sxs-lookup"><span data-stu-id="9af5c-135">Delegate Constraint</span></span>|<span data-ttu-id="9af5c-136">: делегировать&lt;*параметра типа кортежа*, *типа возвращаемого значения*&gt;</span><span class="sxs-lookup"><span data-stu-id="9af5c-136">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span></span>|<span data-ttu-id="9af5c-137">Указанный тип должен быть типом делегата, с заданными аргументами и возвращаемое значение; не предназначен для общего пользования.</span><span class="sxs-lookup"><span data-stu-id="9af5c-137">The provided type must be a delegate type that has the specified arguments and return value; not intended for common use.</span></span>|
|<span data-ttu-id="9af5c-138">Ограничение по сравнению</span><span class="sxs-lookup"><span data-stu-id="9af5c-138">Comparison Constraint</span></span>|<span data-ttu-id="9af5c-139">: сравнение</span><span class="sxs-lookup"><span data-stu-id="9af5c-139">: comparison</span></span>|<span data-ttu-id="9af5c-140">Переданный тип должен поддерживать сравнение.</span><span class="sxs-lookup"><span data-stu-id="9af5c-140">The provided type must support comparison.</span></span>|
|<span data-ttu-id="9af5c-141">Ограничения равенства</span><span class="sxs-lookup"><span data-stu-id="9af5c-141">Equality Constraint</span></span>|<span data-ttu-id="9af5c-142">: на равенство</span><span class="sxs-lookup"><span data-stu-id="9af5c-142">: equality</span></span>|<span data-ttu-id="9af5c-143">Переданный тип должен поддерживать на равенство.</span><span class="sxs-lookup"><span data-stu-id="9af5c-143">The provided type must support equality.</span></span>|
|<span data-ttu-id="9af5c-144">Неуправляемое ограничение</span><span class="sxs-lookup"><span data-stu-id="9af5c-144">Unmanaged Constraint</span></span>|<span data-ttu-id="9af5c-145">: неуправляемые</span><span class="sxs-lookup"><span data-stu-id="9af5c-145">: unmanaged</span></span>|<span data-ttu-id="9af5c-146">Переданный тип должен быть неуправляемого типа.</span><span class="sxs-lookup"><span data-stu-id="9af5c-146">The provided type must be an unmanaged type.</span></span> <span data-ttu-id="9af5c-147">Неуправляемые типы являются определенных примитивных типов (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, или `decimal`), типы перечисления `nativeptr<_>`, или к неуниверсальным структуры, поля которого предназначены всех неуправляемых типов.</span><span class="sxs-lookup"><span data-stu-id="9af5c-147">Unmanaged types are either certain primitive types (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, or `decimal`), enumeration types, `nativeptr<_>`, or a non-generic structure whose fields are all unmanaged types.</span></span>|
<span data-ttu-id="9af5c-148">Необходимо добавить ограничение в том случае, если код должен использовать функцию, которая доступна на тип ограничения, но не для типов в целом.</span><span class="sxs-lookup"><span data-stu-id="9af5c-148">You have to add a constraint when your code has to use a feature that is available on the constraint type but not on types in general.</span></span> <span data-ttu-id="9af5c-149">Например если ограничение типа используется для указания типа класса, можно использовать одного из методов этого класса в универсальной функции или типа.</span><span class="sxs-lookup"><span data-stu-id="9af5c-149">For example, if you use the type constraint to specify a class type, you can use any one of the methods of that class in the generic function or type.</span></span>

<span data-ttu-id="9af5c-150">Указание ограничений иногда это необходимо при написании параметры типа явно, так как без ограничения, компилятор не может проверить, что функции, которые вы используете, будут доступны для любого типа, может потребоваться указать во время выполнения для типа параметр.</span><span class="sxs-lookup"><span data-stu-id="9af5c-150">Specifying constraints is sometimes required when writing type parameters explicitly, because without a constraint, the compiler has no way of verifying that the features that you are using will be available on any type that might be supplied at run time for the type parameter.</span></span>

<span data-ttu-id="9af5c-151">Наиболее распространенных ограничений, используемых в коде F # являются ограничения типа, которые задают базовые классы или интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="9af5c-151">The most common constraints you use in F# code are type constraints that specify base classes or interfaces.</span></span> <span data-ttu-id="9af5c-152">Другие ограничения используются библиотекой F # для реализации определенных функций, таких как ограничения явных членов, которое используется для реализации перегрузки операторов для арифметических операторов или предоставляются в основном потому, что F # поддерживает полный набор ограничений, поддерживаемый средой CLR.</span><span class="sxs-lookup"><span data-stu-id="9af5c-152">The other constraints are either used by the F# library to implement certain functionality, such as the explicit member constraint, which is used to implement operator overloading for arithmetic operators, or are provided mainly because F# supports the complete set of constraints that is supported by the common language runtime.</span></span>

<span data-ttu-id="9af5c-153">В процессе вывода типа некоторые ограничения автоматически выводятся компилятором.</span><span class="sxs-lookup"><span data-stu-id="9af5c-153">During the type inference process, some constraints are inferred automatically by the compiler.</span></span> <span data-ttu-id="9af5c-154">Например, если вы используете `+` оператор в функции, компилятор выводит явных членов ограничения на типы переменных, которые используются в выражении.</span><span class="sxs-lookup"><span data-stu-id="9af5c-154">For example, if you use the `+` operator in a function, the compiler infers an explicit member constraint on variable types that are used in the expression.</span></span>

<span data-ttu-id="9af5c-155">Следующий код иллюстрирует некоторые объявления ограничение.</span><span class="sxs-lookup"><span data-stu-id="9af5c-155">The following code illustrates some constraint declarations.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9af5c-156">См. также</span><span class="sxs-lookup"><span data-stu-id="9af5c-156">See also</span></span>

- [<span data-ttu-id="9af5c-157">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="9af5c-157">Generics</span></span>](index.md)
- [<span data-ttu-id="9af5c-158">Ограничения</span><span class="sxs-lookup"><span data-stu-id="9af5c-158">Constraints</span></span>](constraints.md)
