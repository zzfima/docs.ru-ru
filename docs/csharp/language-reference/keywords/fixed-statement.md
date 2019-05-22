---
title: Справочник по C#. Оператор fixed
ms.custom: seodec18
ms.date: 05/10/2018
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.openlocfilehash: a852f36c05075365ced8ec39457b15601ca3c3fb
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877082"
---
# <a name="fixed-statement-c-reference"></a><span data-ttu-id="f5d9d-102">Оператор fixed (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f5d9d-102">fixed Statement (C# Reference)</span></span>

<span data-ttu-id="f5d9d-103">Оператор `fixed` не позволяет сборщику мусора переносить перемещаемую переменную.</span><span class="sxs-lookup"><span data-stu-id="f5d9d-103">The `fixed` statement prevents the garbage collector from relocating a movable variable.</span></span> <span data-ttu-id="f5d9d-104">Оператор `fixed` допускается только в [небезопасном](unsafe.md) контексте.</span><span class="sxs-lookup"><span data-stu-id="f5d9d-104">The `fixed` statement is only permitted in an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="f5d9d-105">Можно также использовать ключевое слово `fixed` для создания [буферов фиксированного размера](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span><span class="sxs-lookup"><span data-stu-id="f5d9d-105">You can also use the `fixed` keyword to create [fixed size buffers](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>

<span data-ttu-id="f5d9d-106">Оператор `fixed` задает указатель на управляемую переменную и "закрепляет" эту переменную во время выполнения оператора.</span><span class="sxs-lookup"><span data-stu-id="f5d9d-106">The `fixed` statement sets a pointer to a managed variable and "pins" that variable during the execution of the statement.</span></span> <span data-ttu-id="f5d9d-107">Указатели на перемещаемые управляемые переменные полезны только в контексте `fixed`.</span><span class="sxs-lookup"><span data-stu-id="f5d9d-107">Pointers to movable managed variables are useful only in a `fixed` context.</span></span> <span data-ttu-id="f5d9d-108">Без контекста `fixed` при сборке мусора эти переменные могут переноситься непредсказуемым образом.</span><span class="sxs-lookup"><span data-stu-id="f5d9d-108">Without a `fixed` context, garbage collection could relocate the variables unpredictably.</span></span> <span data-ttu-id="f5d9d-109">Компилятор C# позволяет присвоить указатель только управляемой переменной в операторе `fixed`.</span><span class="sxs-lookup"><span data-stu-id="f5d9d-109">The C# compiler only lets you assign a pointer to a managed variable in a `fixed` statement.</span></span>

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#1)]

<span data-ttu-id="f5d9d-110">Вы можете инициализировать указатель, используя массив, строку, буфер фиксированного размера или адрес переменной.</span><span class="sxs-lookup"><span data-stu-id="f5d9d-110">You can initialize a pointer by using an array, a string, a fixed-size buffer, or the address of a variable.</span></span> <span data-ttu-id="f5d9d-111">Следующий пример иллюстрирует использование переменных адресов, массивов и строк:</span><span class="sxs-lookup"><span data-stu-id="f5d9d-111">The following example illustrates the use of variable addresses, arrays, and strings:</span></span>

[!code-csharp[Initializing fixed size buffers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#2)]

<span data-ttu-id="f5d9d-112">Начиная с C# 7.3, оператор `fixed` работает с дополнительными типами, помимо массивов, строк, буферов фиксированного размера и неуправляемых переменных.</span><span class="sxs-lookup"><span data-stu-id="f5d9d-112">Starting with C# 7.3, the `fixed` statement operates on additional types beyond arrays, strings, fixed-size buffers, or unmanaged variables.</span></span> <span data-ttu-id="f5d9d-113">Любой тип, реализующий метод `GetPinnableReference`, можно зафиксировать.</span><span class="sxs-lookup"><span data-stu-id="f5d9d-113">Any type that implements a method named `GetPinnableReference` can be pinned.</span></span> <span data-ttu-id="f5d9d-114">`GetPinnableReference` должен преобразовывать переменную `ref` в неуправляемый тип.</span><span class="sxs-lookup"><span data-stu-id="f5d9d-114">The `GetPinnableReference` must return a `ref` variable to an unmanaged type.</span></span> <span data-ttu-id="f5d9d-115">Дополнительные сведения см. в статье о [типах указателей](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="f5d9d-115">See the topic on [pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md) for more information.</span></span> <span data-ttu-id="f5d9d-116">Типы .NET <xref:System.Span%601?displayProperty=nameWithType> и <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, представленные в .NET Core 2.0, используют этот шаблон и могут быть зафиксированы.</span><span class="sxs-lookup"><span data-stu-id="f5d9d-116">The .NET types <xref:System.Span%601?displayProperty=nameWithType> and <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> introduced in .NET Core 2.0 make use of this pattern and can be pinned.</span></span> <span data-ttu-id="f5d9d-117">Это показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f5d9d-117">This is shown in the following example:</span></span>

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#FixedSpan)]

<span data-ttu-id="f5d9d-118">При создании типов, которые должны участвовать в этом шаблоне, перейдите по ссылке <xref:System.Span%601.GetPinnableReference?displayProperty=nameWithType> для примера реализации шаблона.</span><span class="sxs-lookup"><span data-stu-id="f5d9d-118">If you are creating types that should participate in this pattern, see <xref:System.Span%601.GetPinnableReference?displayProperty=nameWithType> for an example of implementing the pattern.</span></span>

<span data-ttu-id="f5d9d-119">В одном операторе можно инициализировать несколько указателей одного типа.</span><span class="sxs-lookup"><span data-stu-id="f5d9d-119">Multiple pointers can be initialized in one statement if they are all the same type:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}
```

<span data-ttu-id="f5d9d-120">Чтобы инициализировать указатели разных типов, просто вложите операторы `fixed`, как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="f5d9d-120">To initialize pointers of different types, simply nest `fixed` statements, as shown in the following example.</span></span>

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#3)]

<span data-ttu-id="f5d9d-121">После выполнения кода в операторе закрепление всех переменных отменяется, и они могут пройти сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="f5d9d-121">After the code in the statement is executed, any pinned variables are unpinned and subject to garbage collection.</span></span> <span data-ttu-id="f5d9d-122">Таким образом, не следует использовать указатели на эти переменные за пределами оператора `fixed`.</span><span class="sxs-lookup"><span data-stu-id="f5d9d-122">Therefore, do not point to those variables outside the `fixed` statement.</span></span> <span data-ttu-id="f5d9d-123">Переменные, объявленные в операторе `fixed`, относятся к этому оператору, что упрощает выполнение следующего выражения.</span><span class="sxs-lookup"><span data-stu-id="f5d9d-123">The variables declared in the `fixed` statement are scoped to that statement, making this easier:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
   ...
}
// ps and pd are no longer in scope here.
```

<span data-ttu-id="f5d9d-124">Указатели, инициализированные в операторах `fixed`, являются переменными только для чтения.</span><span class="sxs-lookup"><span data-stu-id="f5d9d-124">Pointers initialized in `fixed` statements are readonly variables.</span></span> <span data-ttu-id="f5d9d-125">Чтобы изменить значение указателя, необходимо объявить переменную второго указателя и изменить ее.</span><span class="sxs-lookup"><span data-stu-id="f5d9d-125">If you want to modify the pointer value, you must declare a second pointer variable, and modify that.</span></span> <span data-ttu-id="f5d9d-126">Переменную, объявленную в операторе `fixed`, изменить невозможно.</span><span class="sxs-lookup"><span data-stu-id="f5d9d-126">The variable declared in the `fixed` statement cannot be modified:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
    byte* pSourceCopy = ps;
    pSourceCopy++; // point to the next element.
    ps++; // invalid: cannot modify ps, as it is declared in the fixed statement.
}
```

<span data-ttu-id="f5d9d-127">Вы можете выделить память в стеке, где на нее не будет распространяться сборка мусора, поэтому ее не нужно будет закреплять.</span><span class="sxs-lookup"><span data-stu-id="f5d9d-127">You can allocate memory on the stack, where it is not subject to garbage collection and therefore does not need to be pinned.</span></span> <span data-ttu-id="f5d9d-128">Дополнительные сведения см. в разделе [stackalloc](stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="f5d9d-128">For more information, see [stackalloc](stackalloc.md).</span></span>

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="f5d9d-129">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f5d9d-129">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f5d9d-130">См. также</span><span class="sxs-lookup"><span data-stu-id="f5d9d-130">See also</span></span>

- [<span data-ttu-id="f5d9d-131">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f5d9d-131">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f5d9d-132">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f5d9d-132">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f5d9d-133">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="f5d9d-133">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f5d9d-134">unsafe</span><span class="sxs-lookup"><span data-stu-id="f5d9d-134">unsafe</span></span>](unsafe.md)
- [<span data-ttu-id="f5d9d-135">Буферы фиксированного размера</span><span class="sxs-lookup"><span data-stu-id="f5d9d-135">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
