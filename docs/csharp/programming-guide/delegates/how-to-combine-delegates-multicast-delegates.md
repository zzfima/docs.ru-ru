---
title: Практическое руководство. Руководство по программированию на C#. Объединение делегатов (многоадресные делегаты)
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: d9430021e6a9b438822f1a6dc201f64adf4fdb0f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69590667"
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a><span data-ttu-id="a388a-102">Практическое руководство. Руководство по программированию на C#. Объединение делегатов (многоадресные делегаты)</span><span class="sxs-lookup"><span data-stu-id="a388a-102">How to: Combine Delegates (Multicast Delegates)(C# Programming Guide)</span></span>
<span data-ttu-id="a388a-103">В этом примере показано создание многоадресных делегатов.</span><span class="sxs-lookup"><span data-stu-id="a388a-103">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="a388a-104">Объекты [делегатов](../../language-reference/keywords/delegate.md) обладают полезным свойством, благодаря которому одному экземпляру делегата с помощью оператора `+` можно присвоить несколько объектов.</span><span class="sxs-lookup"><span data-stu-id="a388a-104">A useful property of [delegate](../../language-reference/keywords/delegate.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="a388a-105">Многоадресный делегат содержит список присвоенных ему делегатов.</span><span class="sxs-lookup"><span data-stu-id="a388a-105">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="a388a-106">При вызове многоадресного делегата поочередно вызываются представленные в его списке делегаты.</span><span class="sxs-lookup"><span data-stu-id="a388a-106">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="a388a-107">Объединять можно только делегаты одного типа.</span><span class="sxs-lookup"><span data-stu-id="a388a-107">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="a388a-108">С помощью оператора `-` можно удалить делегат, входящий в состав многоадресного делегата.</span><span class="sxs-lookup"><span data-stu-id="a388a-108">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a388a-109">Пример</span><span class="sxs-lookup"><span data-stu-id="a388a-109">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="a388a-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a388a-110">See also</span></span>

- <xref:System.MulticastDelegate>
- [<span data-ttu-id="a388a-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a388a-111">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a388a-112">События</span><span class="sxs-lookup"><span data-stu-id="a388a-112">Events</span></span>](../events/index.md)
