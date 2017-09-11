---
title: "stackalloc (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
dev_langs:
- CSharp
helpviewer_keywords:
- stackalloc keyword [C#]
ms.assetid: adc04c28-3ed2-4326-807a-7545df92b852
caps.latest.revision: 27
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 53d61cfdcf4d356a28881c57ad923017c2b479ae
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="5e56f-102">stackalloc (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5e56f-102">stackalloc (C# Reference)</span></span>
<span data-ttu-id="5e56f-103">Ключевое слово `stackalloc` используется в контексте небезопасного кода для выделения блока памяти стеку.</span><span class="sxs-lookup"><span data-stu-id="5e56f-103">The `stackalloc` keyword is used in an unsafe code context to allocate a block of memory on the stack.</span></span>  
  
```  
int* block = stackalloc int[100];  
```  
  
## <a name="remarks"></a><span data-ttu-id="5e56f-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="5e56f-104">Remarks</span></span>  
 <span data-ttu-id="5e56f-105">Это ключевое слово допустимо только в инициализаторах локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="5e56f-105">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="5e56f-106">Следующий код вызывает ошибки компилятора.</span><span class="sxs-lookup"><span data-stu-id="5e56f-106">The following code causes compiler errors.</span></span>  
  
```  
int* block;  
// The following assignment statement causes compiler errors. You  
// can use stackalloc only when declaring and initializing a local   
// variable.  
block = stackalloc int[100];  
```  
  
 <span data-ttu-id="5e56f-107">Поскольку задаются типы указателей, `stackalloc` требует [небезопасного](../../../csharp/language-reference/keywords/unsafe.md) контекста.</span><span class="sxs-lookup"><span data-stu-id="5e56f-107">Because pointer types are involved, `stackalloc` requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context.</span></span> <span data-ttu-id="5e56f-108">Дополнительные сведения см. в разделе [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="5e56f-108">For more information, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
 <span data-ttu-id="5e56f-109">`stackalloc` действует как [_alloca](/cpp/c-runtime-library/reference/alloca) в библиотеке времени выполнения C.</span><span class="sxs-lookup"><span data-stu-id="5e56f-109">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>  
  
 <span data-ttu-id="5e56f-110">Представленный ниже код вычисляет и отображает первые 20 чисел в последовательности Фибоначчи.</span><span class="sxs-lookup"><span data-stu-id="5e56f-110">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="5e56f-111">Каждое из них представляет собой сумму двух предыдущих чисел.</span><span class="sxs-lookup"><span data-stu-id="5e56f-111">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="5e56f-112">В этом коде блок памяти, размер которого позволяет сохранить 20 элементов типа `int`, выделяется не куче, а стеку.</span><span class="sxs-lookup"><span data-stu-id="5e56f-112">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="5e56f-113">Адрес блока хранится в указателе `fib`.</span><span class="sxs-lookup"><span data-stu-id="5e56f-113">The address of the block is stored in the pointer `fib`.</span></span> <span data-ttu-id="5e56f-114">Эта память не подвергаются сборке мусора, а значит, ее не нужно закреплять (с помощью атрибута [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="5e56f-114">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)).</span></span> <span data-ttu-id="5e56f-115">Время существования блока памяти ограничивается временем существования метода, который его определяет.</span><span class="sxs-lookup"><span data-stu-id="5e56f-115">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="5e56f-116">Освободить эту память прежде, чем метод выдаст результат, невозможно.</span><span class="sxs-lookup"><span data-stu-id="5e56f-116">You cannot free the memory before the method returns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e56f-117">Пример</span><span class="sxs-lookup"><span data-stu-id="5e56f-117">Example</span></span>  
 <span data-ttu-id="5e56f-118">[!code-cs[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5e56f-118">[!code-cs[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]</span></span>  
  
## <a name="security"></a><span data-ttu-id="5e56f-119">Безопасность</span><span class="sxs-lookup"><span data-stu-id="5e56f-119">Security</span></span>  
 <span data-ttu-id="5e56f-120">Небезопасный код менее безопасен, чем безопасные аналоги.</span><span class="sxs-lookup"><span data-stu-id="5e56f-120">Unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="5e56f-121">В то же время при использовании `stackalloc` в среде CLR автоматически включается обнаружение переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="5e56f-121">However, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="5e56f-122">Если буфер переполнен, процесс незамедлительно прерывается — это позволяет минимизировать риск исполнения вредоносного кода.</span><span class="sxs-lookup"><span data-stu-id="5e56f-122">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5e56f-123">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="5e56f-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5e56f-124">См. также</span><span class="sxs-lookup"><span data-stu-id="5e56f-124">See Also</span></span>  
 <span data-ttu-id="5e56f-125">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="5e56f-125">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="5e56f-126">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5e56f-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5e56f-127">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="5e56f-127">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="5e56f-128">[Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="5e56f-128">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md) </span></span>  
 [<span data-ttu-id="5e56f-129">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="5e56f-129">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)

