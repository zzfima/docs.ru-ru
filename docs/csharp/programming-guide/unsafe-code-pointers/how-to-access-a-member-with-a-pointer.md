---
title: "Практическое руководство. Доступ к члену с использованием указателя (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: pointers [C#], member access
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 622d9910b09c9197b7f4ccd5e54e2675fbbbbccb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-a-member-with-a-pointer-c-programming-guide"></a><span data-ttu-id="7d199-102">Практическое руководство. Доступ к члену с использованием указателя (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="7d199-102">How to: Access a Member with a Pointer (C# Programming Guide)</span></span>
<span data-ttu-id="7d199-103">Чтобы получить доступ к члену или структуре, которые объявлены в небезопасном контексте, можно использовать оператор доступа к члену, как показано в следующем примере, где `p` — это указатель на [структуру](../../../csharp/language-reference/keywords/struct.md), содержащую член `x`.</span><span class="sxs-lookup"><span data-stu-id="7d199-103">To access a member of a struct that is declared in an unsafe context, you can use the member access operator as shown in the following example in which `p` is a pointer to a [struct](../../../csharp/language-reference/keywords/struct.md) that contains a member `x`.</span></span>  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## <a name="example"></a><span data-ttu-id="7d199-104">Пример</span><span class="sxs-lookup"><span data-stu-id="7d199-104">Example</span></span>  
 <span data-ttu-id="7d199-105">В этом примере объявляется [структура](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, содержащая координаты `x` и `y`, а также создается ее экземпляр.</span><span class="sxs-lookup"><span data-stu-id="7d199-105">In this example, a [struct](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, that contains the two coordinates `x` and `y` is declared and instantiated.</span></span> <span data-ttu-id="7d199-106">С помощью оператора доступа к члену `->` и указателя на экземпляр `home` присваиваются значения `x` и `y`.</span><span class="sxs-lookup"><span data-stu-id="7d199-106">By using the member access operator `->` and a pointer to the instance `home`, `x` and `y` are assigned values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d199-107">Обратите внимание, что выражение `p->x` эквивалентно выражению `(*p).x` и с помощью любого из них можно получить тот же результат.</span><span class="sxs-lookup"><span data-stu-id="7d199-107">Notice that the expression `p->x` is equivalent to the expression `(*p).x`, and you can obtain the same result by using either of the two expressions.</span></span>  
  
 [!code-csharp[csProgGuidePointers#9](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#10](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="7d199-108">См. также</span><span class="sxs-lookup"><span data-stu-id="7d199-108">See Also</span></span>  
 [<span data-ttu-id="7d199-109">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7d199-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7d199-110">Выражения указателей</span><span class="sxs-lookup"><span data-stu-id="7d199-110">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="7d199-111">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="7d199-111">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="7d199-112">Типы</span><span class="sxs-lookup"><span data-stu-id="7d199-112">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="7d199-113">unsafe</span><span class="sxs-lookup"><span data-stu-id="7d199-113">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="7d199-114">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="7d199-114">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="7d199-115">stackalloc</span><span class="sxs-lookup"><span data-stu-id="7d199-115">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
