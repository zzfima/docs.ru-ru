---
title: Практическое руководство. Преобразование типа в универсальный интерфейс IEnumerable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
ms.openlocfilehash: d75c9b9123b52b3e241bea1bbd1d302c406715e8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190384"
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a><span data-ttu-id="cf4a9-102">Практическое руководство. Преобразование типа в универсальный интерфейс IEnumerable</span><span class="sxs-lookup"><span data-stu-id="cf4a9-102">Convert a Type to a Generic IEnumerable</span></span>
<span data-ttu-id="cf4a9-103">Для возвращения аргумента с типом универсальный <xref:System.Linq.Enumerable.AsEnumerable%2A> используется `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-103">Use <xref:System.Linq.Enumerable.AsEnumerable%2A> to return the argument typed as a generic `IEnumerable`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf4a9-104">Пример</span><span class="sxs-lookup"><span data-stu-id="cf4a9-104">Example</span></span>  
 <span data-ttu-id="cf4a9-105">В этом примере [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (с помощью заданного по умолчанию универсального `Query`) предпримет попытку преобразовать запрос в SQL и выполнить его на сервере.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-105">In this example, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (using the default generic `Query`) would try to convert the query to SQL and execute it on the server.</span></span> <span data-ttu-id="cf4a9-106">Однако предложение `where` ссылается на пользовательский метод на стороне клиента (`isValidProduct`), который не может быть преобразован в SQL.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-106">But the `where` clause references a user-defined client-side method (`isValidProduct`), which cannot be converted to SQL.</span></span>  
  
 <span data-ttu-id="cf4a9-107">Решением является задание клиентской универсальной реализации <xref:System.Collections.Generic.IEnumerable%601> предложения `where` для замены универсального <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-107">The solution is to specify the client-side generic <xref:System.Collections.Generic.IEnumerable%601> implementation of `where` to replace the generic <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="cf4a9-108">Для этого следует вызвать оператор <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-108">You do this by invoking the <xref:System.Linq.Enumerable.AsEnumerable%2A> operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="cf4a9-109">См. также</span><span class="sxs-lookup"><span data-stu-id="cf4a9-109">See also</span></span>

- [<span data-ttu-id="cf4a9-110">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="cf4a9-110">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
