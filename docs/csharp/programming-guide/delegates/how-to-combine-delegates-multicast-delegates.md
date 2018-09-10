---
title: Практическое руководство. Объединение делегатов (многоадресные делегаты) (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: e3cc3f9082bd86004a7821b64c01253408c07641
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44083281"
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a><span data-ttu-id="fb1f3-102">Практическое руководство. Объединение делегатов (многоадресные делегаты) (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="fb1f3-102">How to: Combine Delegates (Multicast Delegates)(C# Programming Guide)</span></span>
<span data-ttu-id="fb1f3-103">В этом примере показано создание многоадресных делегатов.</span><span class="sxs-lookup"><span data-stu-id="fb1f3-103">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="fb1f3-104">Объекты [делегатов](../../../csharp/language-reference/keywords/delegate.md) обладают полезным свойством, благодаря которому одному экземпляру делегата с помощью оператора `+` можно присвоить несколько объектов.</span><span class="sxs-lookup"><span data-stu-id="fb1f3-104">A useful property of [delegate](../../../csharp/language-reference/keywords/delegate.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="fb1f3-105">Многоадресный делегат содержит список присвоенных ему делегатов.</span><span class="sxs-lookup"><span data-stu-id="fb1f3-105">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="fb1f3-106">При вызове многоадресного делегата поочередно вызываются представленные в его списке делегаты.</span><span class="sxs-lookup"><span data-stu-id="fb1f3-106">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="fb1f3-107">Объединять можно только делегаты одного типа.</span><span class="sxs-lookup"><span data-stu-id="fb1f3-107">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="fb1f3-108">С помощью оператора `-` можно удалить делегат, входящий в состав многоадресного делегата.</span><span class="sxs-lookup"><span data-stu-id="fb1f3-108">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb1f3-109">Пример</span><span class="sxs-lookup"><span data-stu-id="fb1f3-109">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="fb1f3-110">См. также</span><span class="sxs-lookup"><span data-stu-id="fb1f3-110">See Also</span></span>

- <xref:System.MulticastDelegate>  
- [<span data-ttu-id="fb1f3-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="fb1f3-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="fb1f3-112">События</span><span class="sxs-lookup"><span data-stu-id="fb1f3-112">Events</span></span>](../../../csharp/programming-guide/events/index.md)
