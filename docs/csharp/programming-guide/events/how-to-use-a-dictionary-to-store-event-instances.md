---
title: Как выполнить Руководство по программированию на C#. Использование словаря для хранения экземпляров событий
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: f3b8e313bd0b1bd3973102caebb9bbc9da620ae6
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57203036"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="972ee-102">Как выполнить Руководство по программированию на C#. Использование словаря для хранения экземпляров событий</span><span class="sxs-lookup"><span data-stu-id="972ee-102">How to: Use a Dictionary to Store Event Instances (C# Programming Guide)</span></span>
<span data-ttu-id="972ee-103">`accessor-declarations` можно применять для предоставления большого числа событий таким образом, что вместо отдельного поля для каждого события будет использоваться словарь для хранения экземпляров событий.</span><span class="sxs-lookup"><span data-stu-id="972ee-103">One use for `accessor-declarations` is to expose many events without allocating a field for each event, but instead using a Dictionary to store the event instances.</span></span> <span data-ttu-id="972ee-104">Такой подход эффективен только в том случае, если у вас будет большое число событий, большинство из которых не будет реализовано.</span><span class="sxs-lookup"><span data-stu-id="972ee-104">This is only useful if you have many events, but you expect most of the events will not be implemented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="972ee-105">Пример</span><span class="sxs-lookup"><span data-stu-id="972ee-105">Example</span></span>  
 [!code-csharp[csProgGuideEvents#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="972ee-106">См. также</span><span class="sxs-lookup"><span data-stu-id="972ee-106">See also</span></span>

- [<span data-ttu-id="972ee-107">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="972ee-107">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="972ee-108">События</span><span class="sxs-lookup"><span data-stu-id="972ee-108">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="972ee-109">Делегаты</span><span class="sxs-lookup"><span data-stu-id="972ee-109">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
