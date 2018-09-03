---
title: stackalloc (Справочник по C#)
ms.date: 04/12/2018
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.openlocfilehash: 5926550eea1f5a2f8fb74645f22ca54c2bed3136
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484058"
---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="f7a4d-102">stackalloc (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f7a4d-102">stackalloc (C# Reference)</span></span>
<span data-ttu-id="f7a4d-103">Ключевое слово `stackalloc` используется в контексте небезопасного кода для выделения блока памяти стеку.</span><span class="sxs-lookup"><span data-stu-id="f7a4d-103">The `stackalloc` keyword is used in an unsafe code context to allocate a block of memory on the stack.</span></span>

```csharp
int* block = stackalloc int[100];
```

## <a name="remarks"></a><span data-ttu-id="f7a4d-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="f7a4d-104">Remarks</span></span>

<span data-ttu-id="f7a4d-105">Это ключевое слово допустимо только в инициализаторах локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="f7a4d-105">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="f7a4d-106">Следующий код вызывает ошибки компилятора.</span><span class="sxs-lookup"><span data-stu-id="f7a4d-106">The following code causes compiler errors.</span></span>

```csharp
int* block;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
block = stackalloc int[100];
```

<span data-ttu-id="f7a4d-107">Начиная с версии C# 7.3 для массивов `stackalloc` можно использовать синтаксис инициализатора массива.</span><span class="sxs-lookup"><span data-stu-id="f7a4d-107">Beginning with C# 7.3, you can use array initializer syntax for `stackalloc` arrays.</span></span> <span data-ttu-id="f7a4d-108">Во всех следующих примерах объявляется массив с тремя элементами, имеющими целочисленные значения `1`, `2` и `3`:</span><span class="sxs-lookup"><span data-stu-id="f7a4d-108">All the following declarations declare an array with three elements whose values are the integers `1`, `2`, and `3`:</span></span>

```csharp
// Valid starting with C# 7.3
int* first = stackalloc int[3] { 1, 2, 3 };
int* second = stackalloc int[] { 1, 2, 3 };
int* third = stackalloc[] { 1, 2, 3 };
```

<span data-ttu-id="f7a4d-109">Так как задаются типы указателей, `stackalloc` требует [небезопасного](unsafe.md) контекста.</span><span class="sxs-lookup"><span data-stu-id="f7a4d-109">Because pointer types are involved, `stackalloc` requires an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="f7a4d-110">Дополнительные сведения см. в разделе [Небезопасный код и указатели](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="f7a4d-110">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md)</span></span> 

<span data-ttu-id="f7a4d-111">`stackalloc` действует как [_alloca](/cpp/c-runtime-library/reference/alloca) в библиотеке времени выполнения C.</span><span class="sxs-lookup"><span data-stu-id="f7a4d-111">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>

## <a name="examples"></a><span data-ttu-id="f7a4d-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="f7a4d-112">Examples</span></span>

<span data-ttu-id="f7a4d-113">Представленный ниже код вычисляет и отображает первые 20 чисел в последовательности Фибоначчи.</span><span class="sxs-lookup"><span data-stu-id="f7a4d-113">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="f7a4d-114">Каждое из них представляет собой сумму двух предыдущих чисел.</span><span class="sxs-lookup"><span data-stu-id="f7a4d-114">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="f7a4d-115">В этом коде блок памяти, размер которого позволяет сохранить 20 элементов типа `int`, выделяется не куче, а стеку.</span><span class="sxs-lookup"><span data-stu-id="f7a4d-115">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="f7a4d-116">Адрес блока хранится в указателе `fib`.</span><span class="sxs-lookup"><span data-stu-id="f7a4d-116">The address of the block is stored in the pointer `fib`.</span></span> <span data-ttu-id="f7a4d-117">Эта память не подвергаются сборке мусора, а значит, ее не нужно закреплять (с помощью атрибута [fixed](fixed-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="f7a4d-117">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](fixed-statement.md)).</span></span> <span data-ttu-id="f7a4d-118">Время существования блока памяти ограничивается временем существования метода, который его определяет.</span><span class="sxs-lookup"><span data-stu-id="f7a4d-118">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="f7a4d-119">Освободить эту память прежде, чем метод выдаст результат, невозможно.</span><span class="sxs-lookup"><span data-stu-id="f7a4d-119">You cannot free the memory before the method returns.</span></span>

[!code-csharp[csrefKeywordsOperator#15](../../../../samples/snippets/csharp/keywords/StackAllocExamples.cs#1)]

<span data-ttu-id="f7a4d-120">В приведенном ниже примере массив целых чисел `stackalloc` инициализируется с использованием битовой маски, задающей один бит в каждом элементе.</span><span class="sxs-lookup"><span data-stu-id="f7a4d-120">The following example initializes a `stackalloc` array of integers to a bit mask with one bit set in each element.</span></span> <span data-ttu-id="f7a4d-121">Таким образом в нем демонстрируется использование нового синтаксиса инициализатора, доступного начиная с версии C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="f7a4d-121">This demonstrates the new initializer syntax available starting in C# 7.3:</span></span>

[!code-csharp[csrefKeywordsOperator#15](../../../../samples/snippets/csharp/keywords/StackAllocExamples.cs#2)]

## <a name="security"></a><span data-ttu-id="f7a4d-122">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f7a4d-122">Security</span></span>

<span data-ttu-id="f7a4d-123">Небезопасный код менее безопасен, чем безопасные аналоги.</span><span class="sxs-lookup"><span data-stu-id="f7a4d-123">Unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="f7a4d-124">В то же время при использовании `stackalloc` в среде CLR автоматически включается обнаружение переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="f7a4d-124">However, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="f7a4d-125">Если буфер переполнен, процесс незамедлительно прерывается — это позволяет минимизировать риск исполнения вредоносного кода.</span><span class="sxs-lookup"><span data-stu-id="f7a4d-125">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f7a4d-126">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f7a4d-126">C# Language Specification</span></span>
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f7a4d-127">См. также</span><span class="sxs-lookup"><span data-stu-id="f7a4d-127">See Also</span></span>

- [<span data-ttu-id="f7a4d-128">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f7a4d-128">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="f7a4d-129">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f7a4d-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="f7a4d-130">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="f7a4d-130">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="f7a4d-131">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="f7a4d-131">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
- [<span data-ttu-id="f7a4d-132">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="f7a4d-132">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
