---
title: Как выполнить Руководство по программированию на C#. Объединение делегатов (многоадресные делегаты)
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: 426b9f91d3e3328522ec5c7ab043d5074ececc43
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970118"
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a><span data-ttu-id="2975f-102">Как выполнить Руководство по программированию на C#. Объединение делегатов (многоадресные делегаты)</span><span class="sxs-lookup"><span data-stu-id="2975f-102">How to: Combine Delegates (Multicast Delegates)(C# Programming Guide)</span></span>
<span data-ttu-id="2975f-103">В этом примере показано создание многоадресных делегатов.</span><span class="sxs-lookup"><span data-stu-id="2975f-103">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="2975f-104">Объекты [делегатов](../../../csharp/language-reference/keywords/delegate.md) обладают полезным свойством, благодаря которому одному экземпляру делегата с помощью оператора `+` можно присвоить несколько объектов.</span><span class="sxs-lookup"><span data-stu-id="2975f-104">A useful property of [delegate](../../../csharp/language-reference/keywords/delegate.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="2975f-105">Многоадресный делегат содержит список присвоенных ему делегатов.</span><span class="sxs-lookup"><span data-stu-id="2975f-105">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="2975f-106">При вызове многоадресного делегата поочередно вызываются представленные в его списке делегаты.</span><span class="sxs-lookup"><span data-stu-id="2975f-106">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="2975f-107">Объединять можно только делегаты одного типа.</span><span class="sxs-lookup"><span data-stu-id="2975f-107">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="2975f-108">С помощью оператора `-` можно удалить делегат, входящий в состав многоадресного делегата.</span><span class="sxs-lookup"><span data-stu-id="2975f-108">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2975f-109">Пример</span><span class="sxs-lookup"><span data-stu-id="2975f-109">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="2975f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="2975f-110">See also</span></span>

- <xref:System.MulticastDelegate>
- [<span data-ttu-id="2975f-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2975f-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="2975f-112">События</span><span class="sxs-lookup"><span data-stu-id="2975f-112">Events</span></span>](../../../csharp/programming-guide/events/index.md)
