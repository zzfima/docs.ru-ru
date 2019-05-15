---
title: Справочник по C#. Ключевое слово stackalloc
ms.custom: seodec18
ms.date: 04/10/2019
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.openlocfilehash: 654e225ef98b13aeb4f689e17b1ff378e6002d28
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063919"
---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="76387-102">stackalloc (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="76387-102">stackalloc (C# Reference)</span></span>

<span data-ttu-id="76387-103">Ключевое слово `stackalloc` используется для выделения блока памяти стеку.</span><span class="sxs-lookup"><span data-stu-id="76387-103">The `stackalloc` keyword is used to allocate a block of memory on the stack.</span></span>

```csharp
Span<int> block = stackalloc int[100];
```

<span data-ttu-id="76387-104">Назначение выделенного блока <xref:System.Span%601?displayName=nameWithType> вместо `int*` позволяет выделять память стеку в безопасном блоке.</span><span class="sxs-lookup"><span data-stu-id="76387-104">Assigning the allocated block to a <xref:System.Span%601?displayName=nameWithType> instead of an `int*` allows stack allocations in a safe block.</span></span> <span data-ttu-id="76387-105">Контекст `unsafe` не требуется.</span><span class="sxs-lookup"><span data-stu-id="76387-105">The `unsafe` context is not required.</span></span>

## <a name="remarks"></a><span data-ttu-id="76387-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="76387-106">Remarks</span></span>

<span data-ttu-id="76387-107">Это ключевое слово допустимо только в инициализаторах локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="76387-107">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="76387-108">Следующий код вызывает ошибки компилятора.</span><span class="sxs-lookup"><span data-stu-id="76387-108">The following code causes compiler errors.</span></span>

```csharp
int* block;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
block = stackalloc int[100];
Span<int> span;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
span = stackalloc int[100];
```

<span data-ttu-id="76387-109">Начиная с версии C# 7.3 для массивов `stackalloc` можно использовать синтаксис инициализатора массива.</span><span class="sxs-lookup"><span data-stu-id="76387-109">Beginning with C# 7.3, you can use array initializer syntax for `stackalloc` arrays.</span></span> <span data-ttu-id="76387-110">Во всех следующих примерах объявляется массив с тремя элементами, имеющими целочисленные значения `1`, `2` и `3`.</span><span class="sxs-lookup"><span data-stu-id="76387-110">All the following declarations declare an array with three elements whose values are the integers `1`, `2`, and `3`.</span></span> <span data-ttu-id="76387-111">Вторая инициализация назначает память <xref:System.ReadOnlySpan%601>, указывая на то, что память не может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="76387-111">The second initialization assigns the memory to a <xref:System.ReadOnlySpan%601>, indicating that the memory cannot be modified.</span></span>

```csharp
// Valid starting with C# 7.3
Span<int> first = stackalloc int[3] { 1, 2, 3 };
ReadOnlySpan<int> second = stackalloc int[] { 1, 2, 3 };
Span<int> third = stackalloc[] { 1, 2, 3 };
```

<span data-ttu-id="76387-112">Когда используются типы указателей, для `stackalloc` требуется [небезопасный](unsafe.md) контекст.</span><span class="sxs-lookup"><span data-stu-id="76387-112">When pointer types are involved, `stackalloc` requires an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="76387-113">Дополнительные сведения см. в разделе [Небезопасный код и указатели](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="76387-113">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>

<span data-ttu-id="76387-114">`stackalloc` действует как [_alloca](/cpp/c-runtime-library/reference/alloca) в библиотеке времени выполнения C.</span><span class="sxs-lookup"><span data-stu-id="76387-114">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>

## <a name="examples"></a><span data-ttu-id="76387-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="76387-115">Examples</span></span>

<span data-ttu-id="76387-116">Представленный ниже код вычисляет и отображает первые 20 чисел в последовательности Фибоначчи.</span><span class="sxs-lookup"><span data-stu-id="76387-116">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="76387-117">Каждое из них представляет собой сумму двух предыдущих чисел.</span><span class="sxs-lookup"><span data-stu-id="76387-117">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="76387-118">В этом коде блок памяти, размер которого позволяет сохранить 20 элементов типа `int`, выделяется не куче, а стеку.</span><span class="sxs-lookup"><span data-stu-id="76387-118">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="76387-119">Адрес блока хранится в `Span` `fib`.</span><span class="sxs-lookup"><span data-stu-id="76387-119">The address of the block is stored in the `Span` `fib`.</span></span> <span data-ttu-id="76387-120">Эта память не подвергаются сборке мусора, а значит, ее не нужно закреплять (с помощью атрибута [fixed](fixed-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="76387-120">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](fixed-statement.md)).</span></span> <span data-ttu-id="76387-121">Время существования блока памяти ограничивается временем существования метода, который его определяет.</span><span class="sxs-lookup"><span data-stu-id="76387-121">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="76387-122">Освободить эту память прежде, чем метод выдаст результат, невозможно.</span><span class="sxs-lookup"><span data-stu-id="76387-122">You cannot free the memory before the method returns.</span></span>

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#1)]

<span data-ttu-id="76387-123">В приведенном ниже примере массив целых чисел `stackalloc` инициализируется с использованием битовой маски, задающей один бит в каждом элементе.</span><span class="sxs-lookup"><span data-stu-id="76387-123">The following example initializes a `stackalloc` array of integers to a bit mask with one bit set in each element.</span></span> <span data-ttu-id="76387-124">Таким образом в нем демонстрируется использование нового синтаксиса инициализатора, доступного начиная с версии C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="76387-124">This demonstrates the new initializer syntax available starting in C# 7.3:</span></span>

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#2)]

## <a name="security"></a><span data-ttu-id="76387-125">Безопасность</span><span class="sxs-lookup"><span data-stu-id="76387-125">Security</span></span>

<span data-ttu-id="76387-126">По возможности следует использовать <xref:System.Span%601> или <xref:System.ReadOnlySpan%601>, так как неуправляемый код менее безопасен, чем безопасные аналоги.</span><span class="sxs-lookup"><span data-stu-id="76387-126">You should use <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> when possible because unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="76387-127">Но даже при работе с указателями при использовании `stackalloc` в среде CLR автоматически включается обнаружение переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="76387-127">Even when used with pointers, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="76387-128">Если буфер переполнен, процесс незамедлительно прерывается — это позволяет минимизировать риск исполнения вредоносного кода.</span><span class="sxs-lookup"><span data-stu-id="76387-128">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="76387-129">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="76387-129">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="76387-130">См. также</span><span class="sxs-lookup"><span data-stu-id="76387-130">See also</span></span>

- [<span data-ttu-id="76387-131">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="76387-131">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="76387-132">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="76387-132">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="76387-133">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="76387-133">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="76387-134">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="76387-134">Operator Keywords</span></span>](operator-keywords.md)
- [<span data-ttu-id="76387-135">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="76387-135">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
