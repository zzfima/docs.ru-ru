---
title: "Подсчет количества элементов в последовательности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 060dec47169adccee10477e1c01d7afb02ab0973
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="count-the-number-of-elements-in-a-sequence"></a><span data-ttu-id="86c24-102">Подсчет количества элементов в последовательности</span><span class="sxs-lookup"><span data-stu-id="86c24-102">Count the Number of Elements in a Sequence</span></span>
<span data-ttu-id="86c24-103">Для подсчета числа элементов в последовательности используется оператор <xref:System.Linq.Enumerable.Count%2A>.</span><span class="sxs-lookup"><span data-stu-id="86c24-103">Use the <xref:System.Linq.Enumerable.Count%2A> operator to count the number of elements in a sequence.</span></span>  
  
 <span data-ttu-id="86c24-104">При выполнении данного запроса в учебной базе данных "Northwind" возвращается значение `91`.</span><span class="sxs-lookup"><span data-stu-id="86c24-104">Running this query against the Northwind sample database produces an output of `91`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86c24-105">Пример</span><span class="sxs-lookup"><span data-stu-id="86c24-105">Example</span></span>  
 <span data-ttu-id="86c24-106">В следующем примере подсчитывается количество клиентов (`Customers`) в базе данных.</span><span class="sxs-lookup"><span data-stu-id="86c24-106">The following example counts the number of `Customers` in the database.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="86c24-107">Пример</span><span class="sxs-lookup"><span data-stu-id="86c24-107">Example</span></span>  
 <span data-ttu-id="86c24-108">В следующем примере подсчитывается количество продуктов в базе данных, еще не снятых с производства.</span><span class="sxs-lookup"><span data-stu-id="86c24-108">The following example counts the number of products in the database that have not been discontinued.</span></span>  
  
 <span data-ttu-id="86c24-109">При выполнении данного примера в учебной базе данных "Northwind" возвращается значение `69`.</span><span class="sxs-lookup"><span data-stu-id="86c24-109">Running this example against the Northwind sample database produces an output of `69`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="86c24-110">См. также</span><span class="sxs-lookup"><span data-stu-id="86c24-110">See Also</span></span>  
 [<span data-ttu-id="86c24-111">Статистические запросы</span><span class="sxs-lookup"><span data-stu-id="86c24-111">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 [<span data-ttu-id="86c24-112">Загрузка примеров баз данных</span><span class="sxs-lookup"><span data-stu-id="86c24-112">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
