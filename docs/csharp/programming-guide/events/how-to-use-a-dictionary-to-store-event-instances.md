---
title: Практическое руководство. Использование словаря для хранения экземпляров событий (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: 97a7b0f168e4a1c81ec396f42b731dabb45b3516
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="22648-102">Практическое руководство. Использование словаря для хранения экземпляров событий (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="22648-102">How to: Use a Dictionary to Store Event Instances (C# Programming Guide)</span></span>
<span data-ttu-id="22648-103">`accessor-declarations` можно применять для предоставления большого числа событий таким образом, что вместо отдельного поля для каждого события будет использоваться словарь для хранения экземпляров событий.</span><span class="sxs-lookup"><span data-stu-id="22648-103">One use for `accessor-declarations` is to expose many events without allocating a field for each event, but instead using a Dictionary to store the event instances.</span></span> <span data-ttu-id="22648-104">Такой подход эффективен только в том случае, если у вас будет большое число событий, большинство из которых не будет реализовано.</span><span class="sxs-lookup"><span data-stu-id="22648-104">This is only useful if you have many events, but you expect most of the events will not be implemented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22648-105">Пример</span><span class="sxs-lookup"><span data-stu-id="22648-105">Example</span></span>  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="22648-106">См. также</span><span class="sxs-lookup"><span data-stu-id="22648-106">See Also</span></span>  
 [<span data-ttu-id="22648-107">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="22648-107">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="22648-108">События</span><span class="sxs-lookup"><span data-stu-id="22648-108">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
 [<span data-ttu-id="22648-109">Делегаты</span><span class="sxs-lookup"><span data-stu-id="22648-109">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
