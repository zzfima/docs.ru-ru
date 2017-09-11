---
title: "Практическое руководство. Объединение делегатов (многоадресные делегаты) (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
caps.latest.revision: 17
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
ms.openlocfilehash: 617af10d3fb5f9371d5893b87a91a48639d44a53
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a><span data-ttu-id="2e51a-102">Практическое руководство. Объединение делегатов (многоадресные делегаты) (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="2e51a-102">How to: Combine Delegates (Multicast Delegates)(C# Programming Guide)</span></span>
<span data-ttu-id="2e51a-103">В этом примере показано создание многоадресных делегатов.</span><span class="sxs-lookup"><span data-stu-id="2e51a-103">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="2e51a-104">Объекты [делегатов](../../../csharp/language-reference/keywords/delegate.md) обладают полезным свойством, благодаря которому одному экземпляру делегата с помощью оператора `+` можно присвоить несколько объектов.</span><span class="sxs-lookup"><span data-stu-id="2e51a-104">A useful property of [delegate](../../../csharp/language-reference/keywords/delegate.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="2e51a-105">Многоадресный делегат содержит список присвоенных ему делегатов.</span><span class="sxs-lookup"><span data-stu-id="2e51a-105">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="2e51a-106">При вызове многоадресного делегата поочередно вызываются представленные в его списке делегаты.</span><span class="sxs-lookup"><span data-stu-id="2e51a-106">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="2e51a-107">Объединять можно только делегаты одного типа.</span><span class="sxs-lookup"><span data-stu-id="2e51a-107">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="2e51a-108">С помощью оператора `-` можно удалить делегат, входящий в состав многоадресного делегата.</span><span class="sxs-lookup"><span data-stu-id="2e51a-108">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e51a-109">Пример</span><span class="sxs-lookup"><span data-stu-id="2e51a-109">Example</span></span>  
 <span data-ttu-id="2e51a-110">[!code-cs[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2e51a-110">[!code-cs[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e51a-111">См. также</span><span class="sxs-lookup"><span data-stu-id="2e51a-111">See Also</span></span>  
 <span data-ttu-id="2e51a-112"><xref:System.MulticastDelegate></span><span class="sxs-lookup"><span data-stu-id="2e51a-112"><xref:System.MulticastDelegate></span></span>   
 <span data-ttu-id="2e51a-113">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2e51a-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="2e51a-114">События</span><span class="sxs-lookup"><span data-stu-id="2e51a-114">Events</span></span>](../../../csharp/programming-guide/events/index.md)

