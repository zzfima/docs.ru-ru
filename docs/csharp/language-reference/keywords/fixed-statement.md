---
title: Справочник по C#. Оператор fixed
ms.custom: seodec18
ms.date: 05/10/2018
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.openlocfilehash: d3c87f0e71095bbcc7c5a1d64b026e92838a6306
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433756"
---
# <a name="fixed-statement-c-reference"></a><span data-ttu-id="03cf9-102">Оператор fixed (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="03cf9-102">fixed Statement (C# Reference)</span></span>

<span data-ttu-id="03cf9-103">Оператор `fixed` не позволяет сборщику мусора переносить перемещаемую переменную.</span><span class="sxs-lookup"><span data-stu-id="03cf9-103">The `fixed` statement prevents the garbage collector from relocating a movable variable.</span></span> <span data-ttu-id="03cf9-104">Оператор `fixed` допускается только в [небезопасном](unsafe.md) контексте.</span><span class="sxs-lookup"><span data-stu-id="03cf9-104">The `fixed` statement is only permitted in an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="03cf9-105">Можно также использовать ключевое слово `fixed` для создания [буферов фиксированного размера](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span><span class="sxs-lookup"><span data-stu-id="03cf9-105">You can also use the `fixed` keyword to create [fixed size buffers](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>

<span data-ttu-id="03cf9-106">Оператор `fixed` задает указатель на управляемую переменную и "закрепляет" эту переменную во время выполнения оператора.</span><span class="sxs-lookup"><span data-stu-id="03cf9-106">The `fixed` statement sets a pointer to a managed variable and "pins" that variable during the execution of the statement.</span></span> <span data-ttu-id="03cf9-107">Указатели на перемещаемые управляемые переменные полезны только в контексте `fixed`.</span><span class="sxs-lookup"><span data-stu-id="03cf9-107">Pointers to movable managed variables are useful only in a `fixed` context.</span></span> <span data-ttu-id="03cf9-108">Без контекста `fixed` при сборке мусора эти переменные могут переноситься непредсказуемым образом.</span><span class="sxs-lookup"><span data-stu-id="03cf9-108">Without a `fixed` context, garbage collection could relocate the variables unpredictably.</span></span> <span data-ttu-id="03cf9-109">Компилятор C# позволяет присвоить указатель только управляемой переменной в операторе `fixed`.</span><span class="sxs-lookup"><span data-stu-id="03cf9-109">The C# compiler only lets you assign a pointer to a managed variable in a `fixed` statement.</span></span>

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#1)]

<span data-ttu-id="03cf9-110">Вы можете инициализировать указатель, используя массив, строку, буфер фиксированного размера или адрес переменной.</span><span class="sxs-lookup"><span data-stu-id="03cf9-110">You can initialize a pointer by using an array, a string, a fixed-size buffer, or the address of a variable.</span></span> <span data-ttu-id="03cf9-111">Следующий пример иллюстрирует использование переменных адресов, массивов и строк:</span><span class="sxs-lookup"><span data-stu-id="03cf9-111">The following example illustrates the use of variable addresses, arrays, and strings:</span></span>

[!code-csharp[Initializing fixed size buffers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#2)]

<span data-ttu-id="03cf9-112">Начиная с C# 7.3, оператор `fixed` работает с дополнительными типами, помимо массивов, строк, буферов фиксированного размера и неуправляемых переменных.</span><span class="sxs-lookup"><span data-stu-id="03cf9-112">Starting with C# 7.3, the `fixed` statement operates on additional types beyond arrays, strings, fixed size buffers, or unmanaged variables.</span></span> <span data-ttu-id="03cf9-113">Любой тип, реализующий метод `GetPinnableReference`, можно зафиксировать.</span><span class="sxs-lookup"><span data-stu-id="03cf9-113">Any type that implements a method named `GetPinnableReference` can be pinned.</span></span> <span data-ttu-id="03cf9-114">`GetPinnableReference` должен вернуть переменную `ref` [неуправляемого типа](../builtin-types/unmanaged-types.md).</span><span class="sxs-lookup"><span data-stu-id="03cf9-114">The `GetPinnableReference` must return a `ref` variable of an [unmanaged type](../builtin-types/unmanaged-types.md).</span></span> <span data-ttu-id="03cf9-115">Типы .NET <xref:System.Span%601?displayProperty=nameWithType> и <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, представленные в .NET Core 2.0, используют этот шаблон и могут быть зафиксированы.</span><span class="sxs-lookup"><span data-stu-id="03cf9-115">The .NET types <xref:System.Span%601?displayProperty=nameWithType> and <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> introduced in .NET Core 2.0 make use of this pattern and can be pinned.</span></span> <span data-ttu-id="03cf9-116">Это показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="03cf9-116">This is shown in the following example:</span></span>

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#FixedSpan)]

<span data-ttu-id="03cf9-117">При создании типов, которые должны участвовать в этом шаблоне, перейдите по ссылке <xref:System.Span%601.GetPinnableReference?displayProperty=nameWithType> для примера реализации шаблона.</span><span class="sxs-lookup"><span data-stu-id="03cf9-117">If you are creating types that should participate in this pattern, see <xref:System.Span%601.GetPinnableReference?displayProperty=nameWithType> for an example of implementing the pattern.</span></span>

<span data-ttu-id="03cf9-118">В одном операторе можно инициализировать несколько указателей одного типа.</span><span class="sxs-lookup"><span data-stu-id="03cf9-118">Multiple pointers can be initialized in one statement if they are all the same type:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}
```

<span data-ttu-id="03cf9-119">Чтобы инициализировать указатели разных типов, просто вложите операторы `fixed`, как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="03cf9-119">To initialize pointers of different types, simply nest `fixed` statements, as shown in the following example.</span></span>

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#3)]

<span data-ttu-id="03cf9-120">После выполнения кода в операторе закрепление всех переменных отменяется, и они могут пройти сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="03cf9-120">After the code in the statement is executed, any pinned variables are unpinned and subject to garbage collection.</span></span> <span data-ttu-id="03cf9-121">Таким образом, не следует использовать указатели на эти переменные за пределами оператора `fixed`.</span><span class="sxs-lookup"><span data-stu-id="03cf9-121">Therefore, do not point to those variables outside the `fixed` statement.</span></span> <span data-ttu-id="03cf9-122">Переменные, объявленные в операторе `fixed`, относятся к этому оператору, что упрощает выполнение следующего выражения.</span><span class="sxs-lookup"><span data-stu-id="03cf9-122">The variables declared in the `fixed` statement are scoped to that statement, making this easier:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
   ...
}
// ps and pd are no longer in scope here.
```

<span data-ttu-id="03cf9-123">Указатели, инициализированные в операторах `fixed`, являются переменными только для чтения.</span><span class="sxs-lookup"><span data-stu-id="03cf9-123">Pointers initialized in `fixed` statements are readonly variables.</span></span> <span data-ttu-id="03cf9-124">Чтобы изменить значение указателя, необходимо объявить переменную второго указателя и изменить ее.</span><span class="sxs-lookup"><span data-stu-id="03cf9-124">If you want to modify the pointer value, you must declare a second pointer variable, and modify that.</span></span> <span data-ttu-id="03cf9-125">Переменную, объявленную в операторе `fixed`, изменить невозможно.</span><span class="sxs-lookup"><span data-stu-id="03cf9-125">The variable declared in the `fixed` statement cannot be modified:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
    byte* pSourceCopy = ps;
    pSourceCopy++; // point to the next element.
    ps++; // invalid: cannot modify ps, as it is declared in the fixed statement.
}
```

<span data-ttu-id="03cf9-126">Вы можете выделить память в стеке, где на нее не будет распространяться сборка мусора, поэтому ее не нужно будет закреплять.</span><span class="sxs-lookup"><span data-stu-id="03cf9-126">You can allocate memory on the stack, where it is not subject to garbage collection and therefore does not need to be pinned.</span></span> <span data-ttu-id="03cf9-127">Для этого воспользуйтесь [оператором `stackalloc`](../operators/stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="03cf9-127">To do that use the [`stackalloc` operator](../operators/stackalloc.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="03cf9-128">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="03cf9-128">C# language specification</span></span>

<span data-ttu-id="03cf9-129">Подробные сведения см. в разделе [The fixed statement](~/_csharplang/spec/unsafe-code.md#the-fixed-statement) (Оператор fixed) [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="03cf9-129">For more information, see [The fixed statement](~/_csharplang/spec/unsafe-code.md#the-fixed-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="03cf9-130">См. также</span><span class="sxs-lookup"><span data-stu-id="03cf9-130">See also</span></span>

- [<span data-ttu-id="03cf9-131">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="03cf9-131">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="03cf9-132">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="03cf9-132">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="03cf9-133">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="03cf9-133">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="03cf9-134">unsafe</span><span class="sxs-lookup"><span data-stu-id="03cf9-134">unsafe</span></span>](unsafe.md)
- [<span data-ttu-id="03cf9-135">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="03cf9-135">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="03cf9-136">Буферы фиксированного размера</span><span class="sxs-lookup"><span data-stu-id="03cf9-136">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
