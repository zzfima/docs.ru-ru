---
title: Руководство по программированию на C#. Доступ к элементу с использованием указателя
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], member access
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
ms.openlocfilehash: 9762b9e2487c30b81b7ef6ae22827b64e3cb02e2
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200355"
---
# <a name="how-to-access-a-member-with-a-pointer-c-programming-guide"></a><span data-ttu-id="82185-102">Практическое руководство. Доступ к члену с использованием указателя (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="82185-102">How to: access a member with a pointer (C# Programming Guide)</span></span>
<span data-ttu-id="82185-103">Чтобы получить доступ к члену или структуре, которые объявлены в небезопасном контексте, можно использовать оператор доступа к члену, как показано в следующем примере, где `p` — это указатель на [структуру](../../../csharp/language-reference/keywords/struct.md), содержащую член `x`.</span><span class="sxs-lookup"><span data-stu-id="82185-103">To access a member of a struct that is declared in an unsafe context, you can use the member access operator as shown in the following example in which `p` is a pointer to a [struct](../../../csharp/language-reference/keywords/struct.md) that contains a member `x`.</span></span>  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## <a name="example"></a><span data-ttu-id="82185-104">Пример</span><span class="sxs-lookup"><span data-stu-id="82185-104">Example</span></span>  
 <span data-ttu-id="82185-105">В этом примере объявляется [структура](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, содержащая координаты `x` и `y`, а также создается ее экземпляр.</span><span class="sxs-lookup"><span data-stu-id="82185-105">In this example, a [struct](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, that contains the two coordinates `x` and `y` is declared and instantiated.</span></span> <span data-ttu-id="82185-106">С помощью оператора доступа к члену `->` и указателя на экземпляр `home` присваиваются значения `x` и `y`.</span><span class="sxs-lookup"><span data-stu-id="82185-106">By using the member access operator `->` and a pointer to the instance `home`, `x` and `y` are assigned values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82185-107">Обратите внимание, что выражение `p->x` эквивалентно выражению `(*p).x` и с помощью любого из них можно получить тот же результат.</span><span class="sxs-lookup"><span data-stu-id="82185-107">Notice that the expression `p->x` is equivalent to the expression `(*p).x`, and you can obtain the same result by using either of the two expressions.</span></span>  
  
 [!code-csharp[csProgGuidePointers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#9)]  
  
 [!code-csharp[csProgGuidePointers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#10)]  
  
## <a name="see-also"></a><span data-ttu-id="82185-108">См. также</span><span class="sxs-lookup"><span data-stu-id="82185-108">See also</span></span>

- [<span data-ttu-id="82185-109">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="82185-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="82185-110">Выражения указателей</span><span class="sxs-lookup"><span data-stu-id="82185-110">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="82185-111">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="82185-111">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="82185-112">Типы</span><span class="sxs-lookup"><span data-stu-id="82185-112">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="82185-113">unsafe</span><span class="sxs-lookup"><span data-stu-id="82185-113">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="82185-114">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="82185-114">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="82185-115">stackalloc</span><span class="sxs-lookup"><span data-stu-id="82185-115">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
