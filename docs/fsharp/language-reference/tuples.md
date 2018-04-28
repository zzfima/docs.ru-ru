---
title: Кортежи (F#)
description: 'Дополнительные сведения о кортежа, группирование неименованных, но упорядоченных значений, возможно различных типов F #.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 9710f4996a952fdeaab07a30916215f27969e1a3
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="tuples"></a><span data-ttu-id="aae08-103">Кортежи</span><span class="sxs-lookup"><span data-stu-id="aae08-103">Tuples</span></span>

<span data-ttu-id="aae08-104">Объект *кортежа* — это группа неименованных, но упорядоченных значений, возможно различных типов.</span><span class="sxs-lookup"><span data-stu-id="aae08-104">A *tuple* is a grouping of unnamed but ordered values, possibly of different types.</span></span>  <span data-ttu-id="aae08-105">Кортежей может быть ссылочными типами или структуры.</span><span class="sxs-lookup"><span data-stu-id="aae08-105">Tuples can either be reference types or structs.</span></span>

## <a name="syntax"></a><span data-ttu-id="aae08-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aae08-106">Syntax</span></span>

```fsharp
(element, ... , element)
struct(element, ... ,element )
```
## <a name="remarks"></a><span data-ttu-id="aae08-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="aae08-107">Remarks</span></span>
<span data-ttu-id="aae08-108">Каждый *элемент* в предыдущем синтаксисе может быть любое допустимое выражение F #.</span><span class="sxs-lookup"><span data-stu-id="aae08-108">Each *element* in the previous syntax can be any valid F# expression.</span></span>

## <a name="examples"></a><span data-ttu-id="aae08-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="aae08-109">Examples</span></span>
<span data-ttu-id="aae08-110">Примерами кортежей являются пары, тройки и т. д., из одной или разных типов.</span><span class="sxs-lookup"><span data-stu-id="aae08-110">Examples of tuples include pairs, triples, and so on, of the same or different types.</span></span> <span data-ttu-id="aae08-111">В следующем коде показаны некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="aae08-111">Some examples are illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]
    
## <a name="obtaining-individual-values"></a><span data-ttu-id="aae08-112">Получение отдельных значений</span><span class="sxs-lookup"><span data-stu-id="aae08-112">Obtaining Individual Values</span></span>
<span data-ttu-id="aae08-113">Можно использовать сопоставление шаблонов для доступа и присвоения имен элементов кортежа, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="aae08-113">You can use pattern matching to access and assign names for tuple elements, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

<span data-ttu-id="aae08-114">Можно также деконструирования кортеж через сопоставление шаблонов за пределами `match` выражение через `let` привязки:</span><span class="sxs-lookup"><span data-stu-id="aae08-114">You can also deconstruct a tuple via pattern matching outside of a `match` expression via  `let` binding:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

<span data-ttu-id="aae08-115">Или можно шаблонов сопоставления кортежи в качестве входных данных для функции:</span><span class="sxs-lookup"><span data-stu-id="aae08-115">Or you can pattern match on tuples as inputs to functions:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

<span data-ttu-id="aae08-116">Если вам требуется только один элемент кортежа, чтобы избежать создания новое имя для значения, которое не обязательно используется подстановочный знак (символ подчеркивания).</span><span class="sxs-lookup"><span data-stu-id="aae08-116">If you need only one element of the tuple, the wildcard character (the underscore) can be used to avoid creating a new name for a value that you do not need.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

<span data-ttu-id="aae08-117">Копирование элементов кортежа ссылку на кортеж структуры также довольно простой.</span><span class="sxs-lookup"><span data-stu-id="aae08-117">Copying elements from a reference tuple into a struct tuple is also simple:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

<span data-ttu-id="aae08-118">Функции `fst` и `snd` (ссылаться только кортежей) возвращают первый и второй элементы кортежа, соответственно.</span><span class="sxs-lookup"><span data-stu-id="aae08-118">The functions `fst` and `snd` (reference tuples only) return the first and second elements of a tuple, respectively.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

<span data-ttu-id="aae08-119">Встроенные функции, возвращающей третий элемент тройки не существует, но можно легко написать следующим образом.</span><span class="sxs-lookup"><span data-stu-id="aae08-119">There is no built-in function that returns the third element of a triple, but you can easily write one as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

<span data-ttu-id="aae08-120">Как правило лучше использовать сопоставление шаблонов для доступа к отдельным элементам кортежа.</span><span class="sxs-lookup"><span data-stu-id="aae08-120">Generally, it is better to use pattern matching to access individual tuple elements.</span></span>

## <a name="using-tuples"></a><span data-ttu-id="aae08-121">Использование кортежей</span><span class="sxs-lookup"><span data-stu-id="aae08-121">Using Tuples</span></span>
<span data-ttu-id="aae08-122">Кортежи — удобный способ возвращать несколько значений из функции, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="aae08-122">Tuples provide a convenient way to return multiple values from a function, as shown in the following example.</span></span> <span data-ttu-id="aae08-123">В этом примере выполняется целочисленное деление и возвращает округленный результат операцию, так как первый элемент пары кортежа и остаток в качестве второго элемента пары.</span><span class="sxs-lookup"><span data-stu-id="aae08-123">This example performs integer division and returns the rounded result of the operation as a first member of a tuple pair and the remainder as a second member of the pair.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

<span data-ttu-id="aae08-124">Кортежи может также использоваться как аргументы функции, если вы хотите избежать неявного каррирования аргументов функции, что подразумевается обычным синтаксисом функций.</span><span class="sxs-lookup"><span data-stu-id="aae08-124">Tuples can also be used as function arguments when you want to avoid the implicit currying of function arguments that is implied by the usual function syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

<span data-ttu-id="aae08-125">Обычный синтаксис определения функции `let sum a b = a + b` позволяет определить функцию, являющуюся частичного применения первого аргумента функции, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="aae08-125">The usual syntax for defining the function `let sum a b = a + b` enables you to define a function that is the partial application of the first argument of the function, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

<span data-ttu-id="aae08-126">Используя в качестве параметра кортеж каррирование.</span><span class="sxs-lookup"><span data-stu-id="aae08-126">Using a tuple as the parameter disables currying.</span></span> <span data-ttu-id="aae08-127">Дополнительные сведения см. «Частичное приложения из аргументы» в [функции](functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="aae08-127">For more information, see "Partial Application of Arguments" in [Functions](functions/index.md).</span></span>

## <a name="names-of-tuple-types"></a><span data-ttu-id="aae08-128">Имена типов кортежа</span><span class="sxs-lookup"><span data-stu-id="aae08-128">Names of Tuple Types</span></span>
<span data-ttu-id="aae08-129">При записи имя типа, который является кортежем, используется `*` символ для разделения элементов.</span><span class="sxs-lookup"><span data-stu-id="aae08-129">When you write out the name of a type that is a tuple, you use the `*` symbol to separate elements.</span></span> <span data-ttu-id="aae08-130">Для кортеж, состоящий из `int`, `float`и `string`, такие как `(10, 10.0, "ten")`, тип будет записан следующим образом.</span><span class="sxs-lookup"><span data-stu-id="aae08-130">For a tuple that consists of an `int`, a `float`, and a `string`, such as `(10, 10.0, "ten")`, the type would be written as follows.</span></span>

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a><span data-ttu-id="aae08-131">Взаимодействие с C# кортежи</span><span class="sxs-lookup"><span data-stu-id="aae08-131">Interoperation with C# Tuples</span></span>

<span data-ttu-id="aae08-132">Язык C# 7.0 введены кортежей.</span><span class="sxs-lookup"><span data-stu-id="aae08-132">C# 7.0 introduced tuples to the language.</span></span>  <span data-ttu-id="aae08-133">Кортежи в C# являются структурами и эквивалентны кортежей структуры в языке F #.</span><span class="sxs-lookup"><span data-stu-id="aae08-133">Tuples in C# are structs, and are equivalent to struct tuples in F#.</span></span>  <span data-ttu-id="aae08-134">Если требуется взаимодействие с C#, необходимо использовать структуры кортежей.</span><span class="sxs-lookup"><span data-stu-id="aae08-134">If you need to interoperate with C#, you must use struct tuples.</span></span>

<span data-ttu-id="aae08-135">Это легко сделать.</span><span class="sxs-lookup"><span data-stu-id="aae08-135">This is easy to do.</span></span>  <span data-ttu-id="aae08-136">Например предположим, что у вас есть передать кортеж класса C# и затем использовать его результат, который также является кортеж:</span><span class="sxs-lookup"><span data-stu-id="aae08-136">For example, imagine you have to pass a tuple to a C# class and then consume its result, which is also a tuple:</span></span>

```csharp
namespace CSharpTupleInterop
{
    public static class Example
    {
        public static (int, int) AddOneToXAndY((int x, int y) a) =>
            (a.x + 1, a.y + 1);
    }
}
```

<span data-ttu-id="aae08-137">В коде F # можно передать в качестве параметра кортеж структуры и потреблять результат в виде кортежа структуры.</span><span class="sxs-lookup"><span data-stu-id="aae08-137">In your F# code, you can then pass a struct tuple as the parameter and consume the result as a struct tuple.</span></span>

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a><span data-ttu-id="aae08-138">Преобразование между ссылку кортежи и кортежи, структура</span><span class="sxs-lookup"><span data-stu-id="aae08-138">Converting between Reference Tuples and Struct Tuples</span></span>

<span data-ttu-id="aae08-139">Поскольку ссылка кортежи и кортежи, структуры имеют совершенно другим представлением, они не могут быть неявно преобразованы.</span><span class="sxs-lookup"><span data-stu-id="aae08-139">Because Reference Tuples and Struct Tuples have a completely different underlying representation, they are not implicitly convertible.</span></span>  <span data-ttu-id="aae08-140">То есть не скомпилируется следующий код:</span><span class="sxs-lookup"><span data-stu-id="aae08-140">That is, code such as the following won't compile:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

<span data-ttu-id="aae08-141">Необходимо шаблон соответствия одного кортежа и создать другой составных частей.</span><span class="sxs-lookup"><span data-stu-id="aae08-141">You must pattern match on one tuple and construct the other with the constituent parts.</span></span>  <span data-ttu-id="aae08-142">Пример:</span><span class="sxs-lookup"><span data-stu-id="aae08-142">For example:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a><span data-ttu-id="aae08-143">Скомпилированные формы кортежей ссылки</span><span class="sxs-lookup"><span data-stu-id="aae08-143">Compiled Form of Reference Tuples</span></span>
<span data-ttu-id="aae08-144">В этом разделе объясняются формы кортежей являетесь скомпилированы.</span><span class="sxs-lookup"><span data-stu-id="aae08-144">This section explains the form of tuples when they're compiled.</span></span>  <span data-ttu-id="aae08-145">В приведенной здесь информации не требуется читать, если вы используете .NET Framework 3.5 или ниже.</span><span class="sxs-lookup"><span data-stu-id="aae08-145">The information here isn't necessary to read unless you are targeting .NET Framework 3.5 or lower.</span></span>

<span data-ttu-id="aae08-146">Кортежи компилируются в объекты одного из нескольких универсальных типов, все именованные `System.Tuple`, которые перегружаются на арность или число параметров типа.</span><span class="sxs-lookup"><span data-stu-id="aae08-146">Tuples are compiled into objects of one of several generic types, all named `System.Tuple`, that are overloaded on the arity, or number of type parameters.</span></span> <span data-ttu-id="aae08-147">Типы кортежей видны в этой форме, при просмотре из другого языка, например C# или Visual Basic, или при использовании средства, не поддерживающего конструкций F #.</span><span class="sxs-lookup"><span data-stu-id="aae08-147">Tuple types appear in this form when you view them from another language, such as C# or Visual Basic, or when you are using a tool that is not aware of F# constructs.</span></span> <span data-ttu-id="aae08-148">`Tuple` Типы, которые появились в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="aae08-148">The `Tuple` types were introduced in .NET Framework 4.</span></span> <span data-ttu-id="aae08-149">Если вы используете более ранней версии платформы .NET Framework, компилятор использует версии [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) из версии 2.0 библиотеки ядра F #.</span><span class="sxs-lookup"><span data-stu-id="aae08-149">If you are targeting an earlier version of the .NET Framework, the compiler uses versions of [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) from the 2.0 version of the F# Core Library.</span></span> <span data-ttu-id="aae08-150">Типы из этой библиотеки используются только для приложений, предназначенных для платформы 2.0, 3.0 и 3.5 версий платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="aae08-150">The types in this library are used only for applications that target the 2.0, 3.0, and 3.5 versions of the .NET Framework.</span></span> <span data-ttu-id="aae08-151">Перенаправление типа используется для обеспечения совместимости с двоичными данными между компонентами .NET Framework 2.0 и .NET Framework 4 F #.</span><span class="sxs-lookup"><span data-stu-id="aae08-151">Type forwarding is used to ensure binary compatibility between .NET Framework 2.0 and .NET Framework 4 F# components.</span></span>

### <a name="compiled-form-of-struct-tuples"></a><span data-ttu-id="aae08-152">Скомпилированные формы кортежей структуры</span><span class="sxs-lookup"><span data-stu-id="aae08-152">Compiled Form of Struct Tuples</span></span>

<span data-ttu-id="aae08-153">Кортежи структуры (например, `struct (x, y)`), существенно отличающуюся от кортежей ссылки.</span><span class="sxs-lookup"><span data-stu-id="aae08-153">Struct tuples (for example, `struct (x, y)`), are fundamentally different from reference tuples.</span></span>  <span data-ttu-id="aae08-154">Они компилируются в <xref:System.ValueTuple> типа, перегружены арность или число параметров типа.</span><span class="sxs-lookup"><span data-stu-id="aae08-154">They are compiled into the <xref:System.ValueTuple> type, overloaded by arity, or the number of type parameters.</span></span>  <span data-ttu-id="aae08-155">Они эквивалентны [кортежей 7.0 C#](../../csharp/tuples.md) и [кортежей 2017 г. Visual Basic](../../visual-basic/programming-guide/language-features/data-types/tuples.md)и взаимодействовать в обоих направлениях.</span><span class="sxs-lookup"><span data-stu-id="aae08-155">They are equivalent to [C# 7.0 Tuples](../../csharp/tuples.md) and [Visual Basic 2017 Tuples](../../visual-basic/programming-guide/language-features/data-types/tuples.md), and interoperate bidirectionally.</span></span>

## <a name="see-also"></a><span data-ttu-id="aae08-156">См. также</span><span class="sxs-lookup"><span data-stu-id="aae08-156">See Also</span></span>
[<span data-ttu-id="aae08-157">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="aae08-157">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="aae08-158">Типы языка F#</span><span class="sxs-lookup"><span data-stu-id="aae08-158">F# Types</span></span>](fsharp-types.md)
