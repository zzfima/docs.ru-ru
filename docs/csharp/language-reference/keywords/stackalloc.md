---
title: "stackalloc (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords: stackalloc keyword [C#]
ms.assetid: adc04c28-3ed2-4326-807a-7545df92b852
caps.latest.revision: "27"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ad4453f889a344fcd44dfad44a30fef07380b6a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="d3972-102">stackalloc (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="d3972-102">stackalloc (C# Reference)</span></span>
<span data-ttu-id="d3972-103">Ключевое слово `stackalloc` используется в контексте небезопасного кода для выделения блока памяти стеку.</span><span class="sxs-lookup"><span data-stu-id="d3972-103">The `stackalloc` keyword is used in an unsafe code context to allocate a block of memory on the stack.</span></span>  
  
```  
int* block = stackalloc int[100];  
```  
  
## <a name="remarks"></a><span data-ttu-id="d3972-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="d3972-104">Remarks</span></span>  
 <span data-ttu-id="d3972-105">Это ключевое слово допустимо только в инициализаторах локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="d3972-105">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="d3972-106">Следующий код вызывает ошибки компилятора.</span><span class="sxs-lookup"><span data-stu-id="d3972-106">The following code causes compiler errors.</span></span>  
  
```  
int* block;  
// The following assignment statement causes compiler errors. You  
// can use stackalloc only when declaring and initializing a local   
// variable.  
block = stackalloc int[100];  
```  
  
 <span data-ttu-id="d3972-107">Поскольку задаются типы указателей, `stackalloc` требует [небезопасного](../../../csharp/language-reference/keywords/unsafe.md) контекста.</span><span class="sxs-lookup"><span data-stu-id="d3972-107">Because pointer types are involved, `stackalloc` requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context.</span></span> <span data-ttu-id="d3972-108">Дополнительные сведения см. в разделе [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="d3972-108">For more information, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
 <span data-ttu-id="d3972-109">`stackalloc` действует как [_alloca](/cpp/c-runtime-library/reference/alloca) в библиотеке времени выполнения C.</span><span class="sxs-lookup"><span data-stu-id="d3972-109">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>  
  
 <span data-ttu-id="d3972-110">Представленный ниже код вычисляет и отображает первые 20 чисел в последовательности Фибоначчи.</span><span class="sxs-lookup"><span data-stu-id="d3972-110">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="d3972-111">Каждое из них представляет собой сумму двух предыдущих чисел.</span><span class="sxs-lookup"><span data-stu-id="d3972-111">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="d3972-112">В этом коде блок памяти, размер которого позволяет сохранить 20 элементов типа `int`, выделяется не куче, а стеку.</span><span class="sxs-lookup"><span data-stu-id="d3972-112">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="d3972-113">Адрес блока хранится в указателе `fib`.</span><span class="sxs-lookup"><span data-stu-id="d3972-113">The address of the block is stored in the pointer `fib`.</span></span> <span data-ttu-id="d3972-114">Эта память не подвергаются сборке мусора, а значит, ее не нужно закреплять (с помощью атрибута [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="d3972-114">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)).</span></span> <span data-ttu-id="d3972-115">Время существования блока памяти ограничивается временем существования метода, который его определяет.</span><span class="sxs-lookup"><span data-stu-id="d3972-115">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="d3972-116">Освободить эту память прежде, чем метод выдаст результат, невозможно.</span><span class="sxs-lookup"><span data-stu-id="d3972-116">You cannot free the memory before the method returns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3972-117">Пример</span><span class="sxs-lookup"><span data-stu-id="d3972-117">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]  
  
## <a name="security"></a><span data-ttu-id="d3972-118">Безопасность</span><span class="sxs-lookup"><span data-stu-id="d3972-118">Security</span></span>  
 <span data-ttu-id="d3972-119">Небезопасный код менее безопасен, чем безопасные аналоги.</span><span class="sxs-lookup"><span data-stu-id="d3972-119">Unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="d3972-120">В то же время при использовании `stackalloc` в среде CLR автоматически включается обнаружение переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="d3972-120">However, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="d3972-121">Если буфер переполнен, процесс незамедлительно прерывается — это позволяет минимизировать риск исполнения вредоносного кода.</span><span class="sxs-lookup"><span data-stu-id="d3972-121">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d3972-122">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="d3972-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d3972-123">См. также</span><span class="sxs-lookup"><span data-stu-id="d3972-123">See Also</span></span>  
 [<span data-ttu-id="d3972-124">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="d3972-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d3972-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d3972-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d3972-126">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="d3972-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="d3972-127">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="d3972-127">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="d3972-128">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="d3972-128">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
