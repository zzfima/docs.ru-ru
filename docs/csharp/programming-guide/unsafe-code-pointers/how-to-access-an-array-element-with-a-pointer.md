---
title: "Практическое руководство. Доступ к элементу массива с использованием указателя (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 737c1d7fc0bc0a739de5c0a6cbc5dc09f813133e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a><span data-ttu-id="2b077-102">Практическое руководство. Доступ к элементу массива с использованием указателя (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="2b077-102">How to: Access an Array Element with a Pointer (C# Programming Guide)</span></span>
<span data-ttu-id="2b077-103">В небезопасном контексте для доступа к элементу в памяти можно использовать доступ к элементу указателя, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="2b077-103">In an unsafe context, you can access an element in memory by using pointer element access, as shown in the following example:</span></span>  
  
```  
 char* charPointer = stackalloc char[123];  
for (int i = 65; i < 123; i++)  
{  
    charPointer[i] = (char)i; //access array elements  
}  
```  
  
 <span data-ttu-id="2b077-104">Выражение в квадратных скобках должно допускать неявное преобразование в `int`, `uint`, `long` или `ulong`.</span><span class="sxs-lookup"><span data-stu-id="2b077-104">The expression in square brackets must be implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="2b077-105">Операция p[e] эквивалентна \*(p+e).</span><span class="sxs-lookup"><span data-stu-id="2b077-105">The operation p[e] is equivalent to \*(p+e).</span></span> <span data-ttu-id="2b077-106">Как и в C или C++, при доступе к элементу указателя не выполняется проверка на ошибки выхода за пределы диапазона.</span><span class="sxs-lookup"><span data-stu-id="2b077-106">Like C and C++, the pointer element access does not check for out-of-bounds errors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b077-107">Пример</span><span class="sxs-lookup"><span data-stu-id="2b077-107">Example</span></span>  
 <span data-ttu-id="2b077-108">В этом примере для массива символов `charPointer` выделено 123 расположения в памяти.</span><span class="sxs-lookup"><span data-stu-id="2b077-108">In this example, 123 memory locations are allocated to a character array, `charPointer`.</span></span> <span data-ttu-id="2b077-109">Этот массив использует два цикла [for](../../../csharp/language-reference/keywords/for.md) для отображения строчных и прописных букв.</span><span class="sxs-lookup"><span data-stu-id="2b077-109">The array is used to display the lowercase letters and the uppercase letters in two [for](../../../csharp/language-reference/keywords/for.md) loops.</span></span>  
  
 <span data-ttu-id="2b077-110">Обратите внимание, что выражение `charPointer[i]` эквивалентно выражению `*(charPointer + i)` и с помощью любого из них можно получить тот же результат.</span><span class="sxs-lookup"><span data-stu-id="2b077-110">Notice that the expression `charPointer[i]` is equivalent to the expression `*(charPointer + i)`, and you can obtain the same result by using either of the two expressions.</span></span>  
  
 [!code-csharp[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]  
  
 <span data-ttu-id="2b077-111">**Прописные буквы:**</span><span class="sxs-lookup"><span data-stu-id="2b077-111">**Uppercase letters:**</span></span>  
<span data-ttu-id="2b077-112">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span><span class="sxs-lookup"><span data-stu-id="2b077-112">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span></span>  
<span data-ttu-id="2b077-113">**Строчные буквы:**</span><span class="sxs-lookup"><span data-stu-id="2b077-113">**Lowercase letters:**</span></span>  
<span data-ttu-id="2b077-114">**abcdefghijklmnopqrstuvwxyz**</span><span class="sxs-lookup"><span data-stu-id="2b077-114">**abcdefghijklmnopqrstuvwxyz**</span></span>   
## <a name="see-also"></a><span data-ttu-id="2b077-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2b077-115">See Also</span></span>  
 [<span data-ttu-id="2b077-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2b077-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2b077-117">Выражения указателей</span><span class="sxs-lookup"><span data-stu-id="2b077-117">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="2b077-118">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="2b077-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="2b077-119">Типы</span><span class="sxs-lookup"><span data-stu-id="2b077-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="2b077-120">unsafe</span><span class="sxs-lookup"><span data-stu-id="2b077-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="2b077-121">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="2b077-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="2b077-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="2b077-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
