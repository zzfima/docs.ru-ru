---
title: "Нахождение минимального значения в числовой последовательности"
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
ms.assetid: 78203093-f242-4572-9b31-9495b10926aa
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c040b2a9a4c806d6e0f82ea2b22113b44df7d4c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="find-the-minimum-value-in-a-numeric-sequence"></a><span data-ttu-id="9d9e4-102">Нахождение минимального значения в числовой последовательности</span><span class="sxs-lookup"><span data-stu-id="9d9e4-102">Find the Minimum Value in a Numeric Sequence</span></span>
<span data-ttu-id="9d9e4-103">Для возвращения минимального значения из последовательности числовых значений используется оператор <xref:System.Linq.Enumerable.Min%2A>.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-103">Use the <xref:System.Linq.Enumerable.Min%2A> operator to return the minimum value from a sequence of numeric values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d9e4-104">Пример</span><span class="sxs-lookup"><span data-stu-id="9d9e4-104">Example</span></span>  
 <span data-ttu-id="9d9e4-105">В следующем примере выполняется поиск минимальной цены продукта.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-105">The following example finds the lowest unit price of any product.</span></span>  
  
 <span data-ttu-id="9d9e4-106">Если выполнить этот запрос в образце базы данных Northwind, то будут получены следующие выходные данные: `2.5000`.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-106">If you run this query against the Northwind sample database, the output is: `2.5000`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#9)]
 [!code-vb[DLinqQueryExamples#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="9d9e4-107">Пример</span><span class="sxs-lookup"><span data-stu-id="9d9e4-107">Example</span></span>  
 <span data-ttu-id="9d9e4-108">В следующем примере выполняется поиск минимального объема доставки для заказа.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-108">The following example finds the lowest freight amount for any order.</span></span>  
  
 <span data-ttu-id="9d9e4-109">Если выполнить этот запрос в образце базы данных Northwind, то будут получены следующие выходные данные: `0.0200`.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-109">If you run this query against the Northwind sample database, the output is: `0.0200`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#10)]
 [!code-vb[DLinqQueryExamples#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="9d9e4-110">Пример</span><span class="sxs-lookup"><span data-stu-id="9d9e4-110">Example</span></span>  
 <span data-ttu-id="9d9e4-111">В следующем примере для поиска `Products`, имеющего минимальную цену за единицу в каждой категории используется функция Min.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-111">The following example uses Min to find the `Products` that have the lowest unit price in each category.</span></span> <span data-ttu-id="9d9e4-112">Результат упорядочивается по категории.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-112">The output is arranged by category.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#11](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#11)]
 [!code-vb[DLinqQueryExamples#11](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#11)]  
  
 <span data-ttu-id="9d9e4-113">Если выполнить предыдущий запрос для учебной базы данных "Northwind", результаты будут выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-113">If you run the previous query against the Northwind sample database, your results will resemble the following:</span></span>  
  
 `1`  
  
 `Guaraná Fantástica`  
  
 `2`  
  
 `Aniseed Syrup`  
  
 `3`  
  
 `Teatime Chocolate Biscuits`  
  
 `4`  
  
 `Geitost`  
  
 `5`  
  
 `Filo Mix`  
  
 `6`  
  
 `Tourtière`  
  
 `7`  
  
 `Longlife Tofu`  
  
 `8`  
  
 `Konbu`  
  
## <a name="see-also"></a><span data-ttu-id="9d9e4-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9d9e4-114">See Also</span></span>  
 [<span data-ttu-id="9d9e4-115">Статистические запросы</span><span class="sxs-lookup"><span data-stu-id="9d9e4-115">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 [<span data-ttu-id="9d9e4-116">Загрузка примеров баз данных</span><span class="sxs-lookup"><span data-stu-id="9d9e4-116">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
