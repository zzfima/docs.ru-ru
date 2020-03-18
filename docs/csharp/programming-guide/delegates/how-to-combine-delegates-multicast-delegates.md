---
title: Объединение делегатов (многоадресные делегаты) (руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: 7b5b9ba5c9bf70983fac9f869836b4c8c5449eca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705383"
---
# <a name="how-to-combine-delegates-multicast-delegates-c-programming-guide"></a><span data-ttu-id="9eee6-102">Практическое руководство. Объединение делегатов (многоадресные делегаты) (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="9eee6-102">How to combine delegates (Multicast Delegates) (C# Programming Guide)</span></span>
<span data-ttu-id="9eee6-103">В этом примере показано создание многоадресных делегатов.</span><span class="sxs-lookup"><span data-stu-id="9eee6-103">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="9eee6-104">Объекты [делегатов](../../language-reference/builtin-types/reference-types.md) обладают полезным свойством, благодаря которому одному экземпляру делегата с помощью оператора `+` можно присвоить несколько объектов.</span><span class="sxs-lookup"><span data-stu-id="9eee6-104">A useful property of [delegate](../../language-reference/builtin-types/reference-types.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="9eee6-105">Многоадресный делегат содержит список присвоенных ему делегатов.</span><span class="sxs-lookup"><span data-stu-id="9eee6-105">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="9eee6-106">При вызове многоадресного делегата поочередно вызываются представленные в его списке делегаты.</span><span class="sxs-lookup"><span data-stu-id="9eee6-106">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="9eee6-107">Объединять можно только делегаты одного типа.</span><span class="sxs-lookup"><span data-stu-id="9eee6-107">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="9eee6-108">С помощью оператора `-` можно удалить делегат, входящий в состав многоадресного делегата.</span><span class="sxs-lookup"><span data-stu-id="9eee6-108">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9eee6-109">Пример</span><span class="sxs-lookup"><span data-stu-id="9eee6-109">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="9eee6-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9eee6-110">See also</span></span>

- <xref:System.MulticastDelegate>
- [<span data-ttu-id="9eee6-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9eee6-111">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9eee6-112">События</span><span class="sxs-lookup"><span data-stu-id="9eee6-112">Events</span></span>](../events/index.md)
