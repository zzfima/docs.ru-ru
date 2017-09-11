---
title: "Упорядочение результатов предложения соединения"
description: "Упорядочение результатов предложения соединения."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6272181647bb200c18231c5fc836e3dd1a2d6d55
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="order-the-results-of-a-join-clause"></a><span data-ttu-id="abdf1-104">Упорядочение результатов предложения соединения</span><span class="sxs-lookup"><span data-stu-id="abdf1-104">Order the results of a join clause</span></span>
<span data-ttu-id="abdf1-105">В этом примере показано, как упорядочить результаты операции соединения.</span><span class="sxs-lookup"><span data-stu-id="abdf1-105">This example shows how to order the results of a join operation.</span></span> <span data-ttu-id="abdf1-106">Обратите внимание на то, что упорядочение выполняется после соединения.</span><span class="sxs-lookup"><span data-stu-id="abdf1-106">Note that the ordering is performed after the join.</span></span> <span data-ttu-id="abdf1-107">Несмотря на то, что предложение `orderby` с одним или несколькими исходными последовательностями использовать до соединения можно, обычно это не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="abdf1-107">Although you can use an `orderby` clause with one or more of the source sequences before the join, generally we do not recommend it.</span></span> <span data-ttu-id="abdf1-108">Некоторые поставщики LINQ могут не сохранять этот порядок после соединения.</span><span class="sxs-lookup"><span data-stu-id="abdf1-108">Some LINQ providers might not preserve that ordering after the join.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abdf1-109">Пример</span><span class="sxs-lookup"><span data-stu-id="abdf1-109">Example</span></span>  
 <span data-ttu-id="abdf1-110">Этот запрос создает группу соединения, а затем сортирует группы по элементу категории, который остается в области действия.</span><span class="sxs-lookup"><span data-stu-id="abdf1-110">This query creates a group join, and then sorts the groups based on the category element, which is still in scope.</span></span> <span data-ttu-id="abdf1-111">В инициализаторе анонимного типа подзапрос упорядочивает все соответствующие элементы из последовательности продуктов.</span><span class="sxs-lookup"><span data-stu-id="abdf1-111">Inside the anonymous type initializer, a sub-query orders all the matching elements from the products sequence.</span></span>  
  
 <span data-ttu-id="abdf1-112">[!code-cs[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="abdf1-112">[!code-cs[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="abdf1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="abdf1-113">See also</span></span>  
 <span data-ttu-id="abdf1-114">[Выражения запросов LINQ](index.md) </span><span class="sxs-lookup"><span data-stu-id="abdf1-114">[LINQ query expressions](index.md) </span></span>  
 <span data-ttu-id="abdf1-115">[предложение orderby](../language-reference/keywords/orderby-clause.md) </span><span class="sxs-lookup"><span data-stu-id="abdf1-115">[orderby clause](../language-reference/keywords/orderby-clause.md) </span></span>  
 [<span data-ttu-id="abdf1-116">предложение join</span><span class="sxs-lookup"><span data-stu-id="abdf1-116">join clause</span></span>](../language-reference/keywords/join-clause.md) 

