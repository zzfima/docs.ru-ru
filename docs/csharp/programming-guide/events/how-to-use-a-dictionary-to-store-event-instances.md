---
title: "Практическое руководство. Использование словаря для хранения экземпляров событий (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
caps.latest.revision: 16
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
ms.openlocfilehash: bca140ee4d7519f67d6e896757b3187ac169de1f
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="7f642-102">Практическое руководство. Использование словаря для хранения экземпляров событий (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="7f642-102">How to: Use a Dictionary to Store Event Instances (C# Programming Guide)</span></span>
<span data-ttu-id="7f642-103">`accessor-declarations` можно применять для предоставления большого числа событий таким образом, что вместо отдельного поля для каждого события будет использоваться словарь для хранения экземпляров событий.</span><span class="sxs-lookup"><span data-stu-id="7f642-103">One use for `accessor-declarations` is to expose many events without allocating a field for each event, but instead using a Dictionary to store the event instances.</span></span> <span data-ttu-id="7f642-104">Такой подход эффективен только в том случае, если у вас будет большое число событий, большинство из которых не будет реализовано.</span><span class="sxs-lookup"><span data-stu-id="7f642-104">This is only useful if you have many events, but you expect most of the events will not be implemented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f642-105">Пример</span><span class="sxs-lookup"><span data-stu-id="7f642-105">Example</span></span>  
 <span data-ttu-id="7f642-106">[!code-cs[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7f642-106">[!code-cs[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f642-107">См. также</span><span class="sxs-lookup"><span data-stu-id="7f642-107">See Also</span></span>  
 <span data-ttu-id="7f642-108">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7f642-108">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="7f642-109">[События](../../../csharp/programming-guide/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="7f642-109">[Events](../../../csharp/programming-guide/events/index.md) </span></span>  
 [<span data-ttu-id="7f642-110">Делегаты</span><span class="sxs-lookup"><span data-stu-id="7f642-110">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)

