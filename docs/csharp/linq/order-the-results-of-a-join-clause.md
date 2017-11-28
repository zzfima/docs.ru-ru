---
title: "Упорядочение результатов предложения соединения"
description: "Упорядочение результатов предложения соединения."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: f948c18fb16a4f3ac02945b4a63583f1b01cad40
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="order-the-results-of-a-join-clause"></a><span data-ttu-id="54e34-104">Упорядочение результатов предложения соединения</span><span class="sxs-lookup"><span data-stu-id="54e34-104">Order the results of a join clause</span></span>
<span data-ttu-id="54e34-105">В этом примере показано, как упорядочить результаты операции соединения.</span><span class="sxs-lookup"><span data-stu-id="54e34-105">This example shows how to order the results of a join operation.</span></span> <span data-ttu-id="54e34-106">Обратите внимание на то, что упорядочение выполняется после соединения.</span><span class="sxs-lookup"><span data-stu-id="54e34-106">Note that the ordering is performed after the join.</span></span> <span data-ttu-id="54e34-107">Несмотря на то, что предложение `orderby` с одним или несколькими исходными последовательностями использовать до соединения можно, обычно это не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="54e34-107">Although you can use an `orderby` clause with one or more of the source sequences before the join, generally we do not recommend it.</span></span> <span data-ttu-id="54e34-108">Некоторые поставщики LINQ могут не сохранять этот порядок после соединения.</span><span class="sxs-lookup"><span data-stu-id="54e34-108">Some LINQ providers might not preserve that ordering after the join.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54e34-109">Пример</span><span class="sxs-lookup"><span data-stu-id="54e34-109">Example</span></span>  
 <span data-ttu-id="54e34-110">Этот запрос создает группу соединения, а затем сортирует группы по элементу категории, который остается в области действия.</span><span class="sxs-lookup"><span data-stu-id="54e34-110">This query creates a group join, and then sorts the groups based on the category element, which is still in scope.</span></span> <span data-ttu-id="54e34-111">В инициализаторе анонимного типа подзапрос упорядочивает все соответствующие элементы из последовательности продуктов.</span><span class="sxs-lookup"><span data-stu-id="54e34-111">Inside the anonymous type initializer, a sub-query orders all the matching elements from the products sequence.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]  
 
## <a name="see-also"></a><span data-ttu-id="54e34-112">См. также</span><span class="sxs-lookup"><span data-stu-id="54e34-112">See also</span></span>  
 [<span data-ttu-id="54e34-113">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="54e34-113">LINQ query expressions</span></span>](index.md)  
 [<span data-ttu-id="54e34-114">предложение orderby</span><span class="sxs-lookup"><span data-stu-id="54e34-114">orderby clause</span></span>](../language-reference/keywords/orderby-clause.md)  
 [<span data-ttu-id="54e34-115">предложение join</span><span class="sxs-lookup"><span data-stu-id="54e34-115">join clause</span></span>](../language-reference/keywords/join-clause.md) 
