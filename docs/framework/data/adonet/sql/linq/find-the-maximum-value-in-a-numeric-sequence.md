---
title: Нахождение максимального значения в числовой последовательности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 70d7c058-0280-4815-a008-6f290093591a
ms.openlocfilehash: ebef8cb373da4021fd68fd7ce38de8cb06eb81ec
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782174"
---
# <a name="find-the-maximum-value-in-a-numeric-sequence"></a><span data-ttu-id="86092-102">Нахождение максимального значения в числовой последовательности</span><span class="sxs-lookup"><span data-stu-id="86092-102">Find the Maximum Value in a Numeric Sequence</span></span>
<span data-ttu-id="86092-103">Используйте оператор <xref:System.Linq.Enumerable.Max%2A> для нахождения максимального значения в числовой последовательности.</span><span class="sxs-lookup"><span data-stu-id="86092-103">Use the <xref:System.Linq.Enumerable.Max%2A> operator to find the highest value in a sequence of numeric values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86092-104">Пример</span><span class="sxs-lookup"><span data-stu-id="86092-104">Example</span></span>  
 <span data-ttu-id="86092-105">В следующем примере выполняется поиск самой последней даты приема сотрудника на работу.</span><span class="sxs-lookup"><span data-stu-id="86092-105">The following example finds the latest date of hire for any employee.</span></span>  
  
 <span data-ttu-id="86092-106">Если этот запрос запустить в образце базы данных Northwind, то будут получены следующие выходные данные: `11/15/1994 12:00:00 AM`.</span><span class="sxs-lookup"><span data-stu-id="86092-106">If you run this query against the sample Northwind database, the output is: `11/15/1994 12:00:00 AM`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#6)]
 [!code-vb[DLinqQueryExamples#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="86092-107">Пример</span><span class="sxs-lookup"><span data-stu-id="86092-107">Example</span></span>  
 <span data-ttu-id="86092-108">В следующем примере выполняется максимальное количество единиц продукта на складе.</span><span class="sxs-lookup"><span data-stu-id="86092-108">The following example finds the most units in stock for any product.</span></span>  
  
 <span data-ttu-id="86092-109">Если этот пример запустить в образце базы данных Northwind, то будут получены следующие выходные данные: `125`.</span><span class="sxs-lookup"><span data-stu-id="86092-109">If you run this example against the sample Northwind database, the output is: `125`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#7)]
 [!code-vb[DLinqQueryExamples#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#7)]  
  
## <a name="example"></a><span data-ttu-id="86092-110">Пример</span><span class="sxs-lookup"><span data-stu-id="86092-110">Example</span></span>  
 <span data-ttu-id="86092-111">В следующем примере для поиска `Products`, имеющего максимальную цену за единицу в каждой категории используется функция Max.</span><span class="sxs-lookup"><span data-stu-id="86092-111">The following example uses Max to find the `Products` that have the highest unit price in each category.</span></span> <span data-ttu-id="86092-112">Результаты упорядочиваются по категории.</span><span class="sxs-lookup"><span data-stu-id="86092-112">The output then lists the results by category.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#8)]
 [!code-vb[DLinqQueryExamples#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#8)]  
  
 <span data-ttu-id="86092-113">Если выполнить предыдущий запрос для учебной базы данных "Northwind", результаты будут выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="86092-113">If you run the previous query against the Northwind sample database, your results will resemble the following:</span></span>  
  
 `1`  
  
 `Côte de Blaye`  
  
 `2`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `4`  
  
 `Raclette Courdavault`  
  
 `5`  
  
 `Gnocchi di nonna Alice`  
  
 `6`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Carnarvon Tigers`  
  
## <a name="see-also"></a><span data-ttu-id="86092-114">См. также</span><span class="sxs-lookup"><span data-stu-id="86092-114">See also</span></span>

- [<span data-ttu-id="86092-115">Статистические запросы</span><span class="sxs-lookup"><span data-stu-id="86092-115">Aggregate Queries</span></span>](aggregate-queries.md)
- [<span data-ttu-id="86092-116">Загрузка примеров баз данных</span><span class="sxs-lookup"><span data-stu-id="86092-116">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
