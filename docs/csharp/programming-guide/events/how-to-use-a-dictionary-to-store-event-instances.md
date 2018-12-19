---
title: Как выполнить Руководство по программированию на C#. Использование словаря для хранения экземпляров событий
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: 819c81aed3a6f09a20e51285058dcc77749dd33a
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245146"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="29ff9-102">Как выполнить Руководство по программированию на C#. Использование словаря для хранения экземпляров событий</span><span class="sxs-lookup"><span data-stu-id="29ff9-102">How to: Use a Dictionary to Store Event Instances (C# Programming Guide)</span></span>
<span data-ttu-id="29ff9-103">`accessor-declarations` можно применять для предоставления большого числа событий таким образом, что вместо отдельного поля для каждого события будет использоваться словарь для хранения экземпляров событий.</span><span class="sxs-lookup"><span data-stu-id="29ff9-103">One use for `accessor-declarations` is to expose many events without allocating a field for each event, but instead using a Dictionary to store the event instances.</span></span> <span data-ttu-id="29ff9-104">Такой подход эффективен только в том случае, если у вас будет большое число событий, большинство из которых не будет реализовано.</span><span class="sxs-lookup"><span data-stu-id="29ff9-104">This is only useful if you have many events, but you expect most of the events will not be implemented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29ff9-105">Пример</span><span class="sxs-lookup"><span data-stu-id="29ff9-105">Example</span></span>  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="29ff9-106">См. также</span><span class="sxs-lookup"><span data-stu-id="29ff9-106">See Also</span></span>

- [<span data-ttu-id="29ff9-107">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="29ff9-107">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="29ff9-108">События</span><span class="sxs-lookup"><span data-stu-id="29ff9-108">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
- [<span data-ttu-id="29ff9-109">Делегаты</span><span class="sxs-lookup"><span data-stu-id="29ff9-109">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
