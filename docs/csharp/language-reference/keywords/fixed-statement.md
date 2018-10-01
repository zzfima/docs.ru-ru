---
title: Оператор fixed (Справочник по C#)
ms.date: 05/10/2018
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.openlocfilehash: 021fc3bd63922394bd70495bd4335b068fc51cdd
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2018
ms.locfileid: "47237154"
---
# <a name="fixed-statement-c-reference"></a><span data-ttu-id="7db6e-102">Оператор fixed (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="7db6e-102">fixed Statement (C# Reference)</span></span>

<span data-ttu-id="7db6e-103">Оператор `fixed` не позволяет сборщику мусора переносить перемещаемую переменную.</span><span class="sxs-lookup"><span data-stu-id="7db6e-103">The `fixed` statement prevents the garbage collector from relocating a movable variable.</span></span> <span data-ttu-id="7db6e-104">Оператор `fixed` допускается только в [небезопасном](unsafe.md) контексте.</span><span class="sxs-lookup"><span data-stu-id="7db6e-104">The `fixed` statement is only permitted in an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="7db6e-105">`fixed` также можно использовать для создания [буферов фиксированного размера](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span><span class="sxs-lookup"><span data-stu-id="7db6e-105">`fixed` can also be used to create [fixed size buffers](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>

<span data-ttu-id="7db6e-106">Оператор `fixed` задает указатель на управляемую переменную и "закрепляет" эту переменную во время выполнения оператора.</span><span class="sxs-lookup"><span data-stu-id="7db6e-106">The `fixed` statement sets a pointer to a managed variable and "pins" that variable during the execution of the statement.</span></span> <span data-ttu-id="7db6e-107">Указатели на перемещаемые управляемые переменные полезны только в контексте `fixed`.</span><span class="sxs-lookup"><span data-stu-id="7db6e-107">Pointers to movable managed variables are useful only in a `fixed` context.</span></span> <span data-ttu-id="7db6e-108">Без контекста `fixed` при сборке мусора эти переменные могут переноситься непредсказуемым образом.</span><span class="sxs-lookup"><span data-stu-id="7db6e-108">Without a `fixed` context, garbage collection could relocate the variables unpredictably.</span></span> <span data-ttu-id="7db6e-109">Компилятор C# позволяет присвоить указатель только управляемой переменной в операторе `fixed`.</span><span class="sxs-lookup"><span data-stu-id="7db6e-109">The C# compiler only lets you assign a pointer to a managed variable in a `fixed` statement.</span></span>

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#1)]

<span data-ttu-id="7db6e-110">Вы можете инициализировать указатель, используя массив, строку, буфер фиксированного размера или адрес переменной.</span><span class="sxs-lookup"><span data-stu-id="7db6e-110">You can initialize a pointer by using an array, a string, a fixed-size buffer, or the address of a variable.</span></span> <span data-ttu-id="7db6e-111">В приведенном ниже примере демонстрируется использование переменных адресов, массивов и строк.</span><span class="sxs-lookup"><span data-stu-id="7db6e-111">The following example illustrates the use of variable addresses, arrays, and strings.</span></span> <span data-ttu-id="7db6e-112">Дополнительные сведения о буферах фиксированного размера см. в разделе [Буферы фиксированного размера](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span><span class="sxs-lookup"><span data-stu-id="7db6e-112">For more information about fixed-size buffers, see [Fixed Size Buffers](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>

[!code-csharp[Initializing fixed size buffers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#2)]

<span data-ttu-id="7db6e-113">Начиная с C# 7.3, оператор `fixed` работает с дополнительными типами, помимо массивов, строк, буферов фиксированного размера и неуправляемых переменных.</span><span class="sxs-lookup"><span data-stu-id="7db6e-113">Starting with C# 7.3, the `fixed` statement operates on additional types beyond arrays, strings, fixed-size buffers, or unmanaged variables.</span></span> <span data-ttu-id="7db6e-114">Любой тип, реализующий метод `GetPinnableReference`, можно зафиксировать.</span><span class="sxs-lookup"><span data-stu-id="7db6e-114">Any type that implements a method named `GetPinnableReference` can be pinned.</span></span> <span data-ttu-id="7db6e-115">`GetPinnableReference` должен преобразовывать переменную `ref` в неуправляемый тип.</span><span class="sxs-lookup"><span data-stu-id="7db6e-115">The `GetPinnableReference` must return a `ref` variable to an unmanaged type.</span></span> <span data-ttu-id="7db6e-116">Дополнительные сведения см. в статье о [типах указателей](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="7db6e-116">See the topic on [pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md) for more information.</span></span> <span data-ttu-id="7db6e-117">Типы .NET <xref:System.Span%601?displayProperty=nameWithType> и <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, представленные в .NET Core 2.0, используют этот шаблон и могут быть зафиксированы.</span><span class="sxs-lookup"><span data-stu-id="7db6e-117">The .NET types <xref:System.Span%601?displayProperty=nameWithType> and <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> introduced in .NET Core 2.0 make use of this pattern and can be pinned.</span></span> <span data-ttu-id="7db6e-118">Это показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="7db6e-118">This is shown in the following example:</span></span>

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#FixedSpan)]

<span data-ttu-id="7db6e-119">При создании типов, которые должны участвовать в этом шаблоне, перейдите по ссылке <xref:System.Span%601.GetPinnableReference?displayProperty=nameWithType> для примера реализации шаблона.</span><span class="sxs-lookup"><span data-stu-id="7db6e-119">If you are creating types that should participate in this pattern, see <xref:System.Span%601.GetPinnableReference?displayProperty=nameWithType> for an example of implementing the pattern.</span></span>

<span data-ttu-id="7db6e-120">В одном операторе можно инициализировать несколько указателей одного типа.</span><span class="sxs-lookup"><span data-stu-id="7db6e-120">Multiple pointers can be initialized in one statement if they are all the same type:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}
```

<span data-ttu-id="7db6e-121">Чтобы инициализировать указатели разных типов, просто вложите операторы `fixed`, как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="7db6e-121">To initialize pointers of different types, simply nest `fixed` statements, as shown in the following example.</span></span>

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#3)]

<span data-ttu-id="7db6e-122">После выполнения кода в операторе закрепление всех переменных отменяется, и они могут пройти сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="7db6e-122">After the code in the statement is executed, any pinned variables are unpinned and subject to garbage collection.</span></span> <span data-ttu-id="7db6e-123">Таким образом, не следует использовать указатели на эти переменные за пределами оператора `fixed`.</span><span class="sxs-lookup"><span data-stu-id="7db6e-123">Therefore, do not point to those variables outside the `fixed` statement.</span></span> <span data-ttu-id="7db6e-124">Переменные, объявленные в операторе `fixed`, относятся к этому оператору, что упрощает выполнение следующего выражения.</span><span class="sxs-lookup"><span data-stu-id="7db6e-124">The variables declared in the `fixed` statement are scoped to that statement, making this easier:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
   ...
}
// ps and pd are no longer in scope here.
```

<span data-ttu-id="7db6e-125">Указатели, инициализированные в операторах `fixed`, являются переменными только для чтения.</span><span class="sxs-lookup"><span data-stu-id="7db6e-125">Pointers initialized in `fixed` statements are readonly variables.</span></span> <span data-ttu-id="7db6e-126">Чтобы изменить значение указателя, необходимо объявить переменную второго указателя и изменить ее.</span><span class="sxs-lookup"><span data-stu-id="7db6e-126">If you want to modify the pointer value, you must declare a second pointer variable, and modify that.</span></span> <span data-ttu-id="7db6e-127">Переменную, объявленную в операторе `fixed`, изменить невозможно.</span><span class="sxs-lookup"><span data-stu-id="7db6e-127">The variable declared in the `fixed` statement cannot be modified:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
    byte* pSourceCopy = ps;
    pSourceCopy++; // point to the next element.
    ps++; // invalid: cannot modify ps, as it is declared in the fixed statement.
}
```


<span data-ttu-id="7db6e-128">В небезопасном режиме вы можете выделить память в стеке, где сборка мусора не производится и, соответственно, закрепление не требуется.</span><span class="sxs-lookup"><span data-stu-id="7db6e-128">In unsafe mode, you can allocate memory on the stack, where it is not subject to garbage collection and therefore does not need to be pinned.</span></span> <span data-ttu-id="7db6e-129">Дополнительные сведения см. в разделе [stackalloc](stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="7db6e-129">For more information, see [stackalloc](stackalloc.md).</span></span>

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="7db6e-130">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="7db6e-130">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7db6e-131">См. также</span><span class="sxs-lookup"><span data-stu-id="7db6e-131">See Also</span></span>

- [<span data-ttu-id="7db6e-132">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="7db6e-132">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="7db6e-133">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7db6e-133">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="7db6e-134">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="7db6e-134">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="7db6e-135">unsafe</span><span class="sxs-lookup"><span data-stu-id="7db6e-135">unsafe</span></span>](unsafe.md)  
- [<span data-ttu-id="7db6e-136">Буферы фиксированного размера</span><span class="sxs-lookup"><span data-stu-id="7db6e-136">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
