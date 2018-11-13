---
title: Кортежи (F#)
description: Дополнительные сведения о кортежа F#, группирования неименованных, но упорядоченных значений, возможно различных типов.
ms.date: 05/16/2016
ms.openlocfilehash: e7628e4c4b538c2fe52fca25d2597b10fec28d1c
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "43749227"
---
# <a name="tuples"></a><span data-ttu-id="2a85c-103">Кортежи</span><span class="sxs-lookup"><span data-stu-id="2a85c-103">Tuples</span></span>

<span data-ttu-id="2a85c-104">Объект *кортежа* представляет собой способ группирования неименованных, но упорядоченных значений, возможно различных типов.</span><span class="sxs-lookup"><span data-stu-id="2a85c-104">A *tuple* is a grouping of unnamed but ordered values, possibly of different types.</span></span>  <span data-ttu-id="2a85c-105">Кортежей может быть ссылочными типами или структуры.</span><span class="sxs-lookup"><span data-stu-id="2a85c-105">Tuples can either be reference types or structs.</span></span>

## <a name="syntax"></a><span data-ttu-id="2a85c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a85c-106">Syntax</span></span>

```fsharp
(element, ... , element)
struct(element, ... ,element )
```

## <a name="remarks"></a><span data-ttu-id="2a85c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="2a85c-107">Remarks</span></span>

<span data-ttu-id="2a85c-108">Каждый *элемент* в предыдущем синтаксисе может быть любое допустимое выражение F#.</span><span class="sxs-lookup"><span data-stu-id="2a85c-108">Each *element* in the previous syntax can be any valid F# expression.</span></span>

## <a name="examples"></a><span data-ttu-id="2a85c-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="2a85c-109">Examples</span></span>

<span data-ttu-id="2a85c-110">Кортежи примеры пары, тройки и т. д., из одной или разных типов.</span><span class="sxs-lookup"><span data-stu-id="2a85c-110">Examples of tuples include pairs, triples, and so on, of the same or different types.</span></span> <span data-ttu-id="2a85c-111">В следующем коде показаны некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="2a85c-111">Some examples are illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]

## <a name="obtaining-individual-values"></a><span data-ttu-id="2a85c-112">Получение отдельных значений</span><span class="sxs-lookup"><span data-stu-id="2a85c-112">Obtaining Individual Values</span></span>

<span data-ttu-id="2a85c-113">Можно использовать сопоставление шаблонов для доступа и назначения имен для элементов кортежа, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="2a85c-113">You can use pattern matching to access and assign names for tuple elements, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

<span data-ttu-id="2a85c-114">Можно также деконструкции кортежа с помощью сопоставления шаблонов за пределами `match` выражения через `let` привязки:</span><span class="sxs-lookup"><span data-stu-id="2a85c-114">You can also deconstruct a tuple via pattern matching outside of a `match` expression via  `let` binding:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

<span data-ttu-id="2a85c-115">Или можно шаблонов соответствуют по кортежей в качестве входных аргументов функций:</span><span class="sxs-lookup"><span data-stu-id="2a85c-115">Or you can pattern match on tuples as inputs to functions:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

<span data-ttu-id="2a85c-116">Если вам требуется только один элемент кортежа, можно использовать подстановочный знак (символ подчеркивания), чтобы не создавать новое имя для значения, которое не обязательно.</span><span class="sxs-lookup"><span data-stu-id="2a85c-116">If you need only one element of the tuple, the wildcard character (the underscore) can be used to avoid creating a new name for a value that you do not need.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

<span data-ttu-id="2a85c-117">Копирование элементов из кортежа ссылку на кортеж структуры также выполняется очень просто:</span><span class="sxs-lookup"><span data-stu-id="2a85c-117">Copying elements from a reference tuple into a struct tuple is also simple:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

<span data-ttu-id="2a85c-118">Функции `fst` и `snd` (ссылаться только кортежей) возвращают первый и второй элементы кортежа, соответственно.</span><span class="sxs-lookup"><span data-stu-id="2a85c-118">The functions `fst` and `snd` (reference tuples only) return the first and second elements of a tuple, respectively.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

<span data-ttu-id="2a85c-119">Нет встроенной функции, который возвращает третий элемент тройки, но вы легко написать следующим образом.</span><span class="sxs-lookup"><span data-stu-id="2a85c-119">There is no built-in function that returns the third element of a triple, but you can easily write one as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

<span data-ttu-id="2a85c-120">Как правило лучше использовать сопоставление шаблонов для доступа к отдельным элементам кортежа.</span><span class="sxs-lookup"><span data-stu-id="2a85c-120">Generally, it is better to use pattern matching to access individual tuple elements.</span></span>

## <a name="using-tuples"></a><span data-ttu-id="2a85c-121">Использование кортежей</span><span class="sxs-lookup"><span data-stu-id="2a85c-121">Using Tuples</span></span>

<span data-ttu-id="2a85c-122">Кортежи — удобный способ для возврата нескольких значений из функции, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2a85c-122">Tuples provide a convenient way to return multiple values from a function, as shown in the following example.</span></span> <span data-ttu-id="2a85c-123">В этом примере выполняет целочисленное деление и возвращает округленный результат операцию, так как первый элемент пары кортежа и остаток в качестве второго элемента пары.</span><span class="sxs-lookup"><span data-stu-id="2a85c-123">This example performs integer division and returns the rounded result of the operation as a first member of a tuple pair and the remainder as a second member of the pair.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

<span data-ttu-id="2a85c-124">Кортежи можно также использоваться как аргументы функции, если вы хотите избежать неявное каррирование аргументов функции, которые выражается обычным синтаксисом функций.</span><span class="sxs-lookup"><span data-stu-id="2a85c-124">Tuples can also be used as function arguments when you want to avoid the implicit currying of function arguments that is implied by the usual function syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

<span data-ttu-id="2a85c-125">Обычный синтаксис определения функции `let sum a b = a + b` позволяет определить функцию, представляющую собой частичное применение первого аргумента функции, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="2a85c-125">The usual syntax for defining the function `let sum a b = a + b` enables you to define a function that is the partial application of the first argument of the function, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

<span data-ttu-id="2a85c-126">Используя в качестве параметра кортеж каррирование.</span><span class="sxs-lookup"><span data-stu-id="2a85c-126">Using a tuple as the parameter disables currying.</span></span> <span data-ttu-id="2a85c-127">Дополнительные сведения см. в разделе «Частичное приложения из аргументы» в [функции](functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="2a85c-127">For more information, see "Partial Application of Arguments" in [Functions](functions/index.md).</span></span>

## <a name="names-of-tuple-types"></a><span data-ttu-id="2a85c-128">Имена типов кортежей</span><span class="sxs-lookup"><span data-stu-id="2a85c-128">Names of Tuple Types</span></span>

<span data-ttu-id="2a85c-129">При написании имени типа, который представляет собой кортеж, использовании `*` символ для разделения элементов.</span><span class="sxs-lookup"><span data-stu-id="2a85c-129">When you write out the name of a type that is a tuple, you use the `*` symbol to separate elements.</span></span> <span data-ttu-id="2a85c-130">Для кортеж, состоящий из `int`, `float`и `string`, такие как `(10, 10.0, "ten")`, тип будет записан следующим образом.</span><span class="sxs-lookup"><span data-stu-id="2a85c-130">For a tuple that consists of an `int`, a `float`, and a `string`, such as `(10, 10.0, "ten")`, the type would be written as follows.</span></span>

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a><span data-ttu-id="2a85c-131">Взаимодействие с кортежами на C#</span><span class="sxs-lookup"><span data-stu-id="2a85c-131">Interoperation with C# Tuples</span></span>

<span data-ttu-id="2a85c-132">Язык C# 7.0 введены кортежей.</span><span class="sxs-lookup"><span data-stu-id="2a85c-132">C# 7.0 introduced tuples to the language.</span></span>  <span data-ttu-id="2a85c-133">Кортежи в C# являются структурами и эквивалентные структурных кортежей в F#.</span><span class="sxs-lookup"><span data-stu-id="2a85c-133">Tuples in C# are structs, and are equivalent to struct tuples in F#.</span></span>  <span data-ttu-id="2a85c-134">Если вам нужно взаимодействовать с C#, необходимо использовать структурных кортежей.</span><span class="sxs-lookup"><span data-stu-id="2a85c-134">If you need to interoperate with C#, you must use struct tuples.</span></span>

<span data-ttu-id="2a85c-135">Это легко сделать.</span><span class="sxs-lookup"><span data-stu-id="2a85c-135">This is easy to do.</span></span>  <span data-ttu-id="2a85c-136">Например представьте, что вам нужно передать кортеж класса C#, а затем использовать его результат, который также является кортеж:</span><span class="sxs-lookup"><span data-stu-id="2a85c-136">For example, imagine you have to pass a tuple to a C# class and then consume its result, which is also a tuple:</span></span>

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

<span data-ttu-id="2a85c-137">В коде F# можно передать в качестве параметра кортеж структуры и использовать результат в виде структуры кортежа.</span><span class="sxs-lookup"><span data-stu-id="2a85c-137">In your F# code, you can then pass a struct tuple as the parameter and consume the result as a struct tuple.</span></span>

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a><span data-ttu-id="2a85c-138">Преобразование между ссылку кортежи и кортежи, структура</span><span class="sxs-lookup"><span data-stu-id="2a85c-138">Converting between Reference Tuples and Struct Tuples</span></span>

<span data-ttu-id="2a85c-139">Так как ссылка кортежи и кортежи, структуры имеют совершенно другим базовым представлением, они не могут быть неявно преобразованы.</span><span class="sxs-lookup"><span data-stu-id="2a85c-139">Because Reference Tuples and Struct Tuples have a completely different underlying representation, they are not implicitly convertible.</span></span>  <span data-ttu-id="2a85c-140">То есть не будет компилироваться следующий код:</span><span class="sxs-lookup"><span data-stu-id="2a85c-140">That is, code such as the following won't compile:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

<span data-ttu-id="2a85c-141">Необходимо шаблон соответствует на один кортеж, а также создание на другом ― составных частей.</span><span class="sxs-lookup"><span data-stu-id="2a85c-141">You must pattern match on one tuple and construct the other with the constituent parts.</span></span>  <span data-ttu-id="2a85c-142">Пример:</span><span class="sxs-lookup"><span data-stu-id="2a85c-142">For example:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a><span data-ttu-id="2a85c-143">Скомпилированные формы кортежей ссылки</span><span class="sxs-lookup"><span data-stu-id="2a85c-143">Compiled Form of Reference Tuples</span></span>

<span data-ttu-id="2a85c-144">В этом разделе объясняется виде кортежей, когда они компилируются.</span><span class="sxs-lookup"><span data-stu-id="2a85c-144">This section explains the form of tuples when they're compiled.</span></span>  <span data-ttu-id="2a85c-145">Приведенные здесь сведения не требуется читать, если вы ориентируетесь на .NET Framework 3.5 или ниже.</span><span class="sxs-lookup"><span data-stu-id="2a85c-145">The information here isn't necessary to read unless you are targeting .NET Framework 3.5 or lower.</span></span>

<span data-ttu-id="2a85c-146">Кортежи компилируются в объекты одного из нескольких универсальных типов, все именованные `System.Tuple`, являются перегруженными арность или количество параметров типа.</span><span class="sxs-lookup"><span data-stu-id="2a85c-146">Tuples are compiled into objects of one of several generic types, all named `System.Tuple`, that are overloaded on the arity, or number of type parameters.</span></span> <span data-ttu-id="2a85c-147">Типы кортежей появляются в этой форме, при их просмотре из другого языка, например C# или Visual Basic, или при использовании средства, которые не поддерживают конструкций F#.</span><span class="sxs-lookup"><span data-stu-id="2a85c-147">Tuple types appear in this form when you view them from another language, such as C# or Visual Basic, or when you are using a tool that is not aware of F# constructs.</span></span> <span data-ttu-id="2a85c-148">`Tuple` Типы, которые появились в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="2a85c-148">The `Tuple` types were introduced in .NET Framework 4.</span></span> <span data-ttu-id="2a85c-149">Если вы используете более раннюю версию платформы .NET Framework, компилятор использует версии [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) из версии 2.0 основной библиотеки F#.</span><span class="sxs-lookup"><span data-stu-id="2a85c-149">If you are targeting an earlier version of the .NET Framework, the compiler uses versions of [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) from the 2.0 version of the F# Core Library.</span></span> <span data-ttu-id="2a85c-150">Типы в этой библиотеке, используется только для приложений, предназначенных для 2.0, 3.0 и 3.5 версий платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2a85c-150">The types in this library are used only for applications that target the 2.0, 3.0, and 3.5 versions of the .NET Framework.</span></span> <span data-ttu-id="2a85c-151">Перенаправление типа позволяет обеспечить совместимость двоичных файлов между компонентами .NET Framework 2.0 и .NET Framework 4 F#.</span><span class="sxs-lookup"><span data-stu-id="2a85c-151">Type forwarding is used to ensure binary compatibility between .NET Framework 2.0 and .NET Framework 4 F# components.</span></span>

### <a name="compiled-form-of-struct-tuples"></a><span data-ttu-id="2a85c-152">Скомпилированная форма структурных кортежей</span><span class="sxs-lookup"><span data-stu-id="2a85c-152">Compiled Form of Struct Tuples</span></span>

<span data-ttu-id="2a85c-153">Структурных кортежей (например, `struct (x, y)`), существенно отличающуюся от кортежей ссылку.</span><span class="sxs-lookup"><span data-stu-id="2a85c-153">Struct tuples (for example, `struct (x, y)`), are fundamentally different from reference tuples.</span></span>  <span data-ttu-id="2a85c-154">Они компилируются в <xref:System.ValueTuple> типа, перегруженные арность или количество параметров типа.</span><span class="sxs-lookup"><span data-stu-id="2a85c-154">They are compiled into the <xref:System.ValueTuple> type, overloaded by arity, or the number of type parameters.</span></span>  <span data-ttu-id="2a85c-155">Они эквивалентны [кортежи в C# 7.0](../../csharp/tuples.md) и [Visual Basic 2017 кортежей](../../visual-basic/programming-guide/language-features/data-types/tuples.md)и взаимодействовать в обоих направлениях.</span><span class="sxs-lookup"><span data-stu-id="2a85c-155">They are equivalent to [C# 7.0 Tuples](../../csharp/tuples.md) and [Visual Basic 2017 Tuples](../../visual-basic/programming-guide/language-features/data-types/tuples.md), and interoperate bidirectionally.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a85c-156">См. также</span><span class="sxs-lookup"><span data-stu-id="2a85c-156">See also</span></span>

- [<span data-ttu-id="2a85c-157">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="2a85c-157">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="2a85c-158">Типы языка F#</span><span class="sxs-lookup"><span data-stu-id="2a85c-158">F# Types</span></span>](fsharp-types.md)
