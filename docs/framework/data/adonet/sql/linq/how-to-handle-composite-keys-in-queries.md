---
title: Как выполнить обрабатывать составные ключи в запросах
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ce2f14fd-1038-458a-91e3-a078c61f0d10
ms.openlocfilehash: 0ee0bda8c3ee46cb6e08ee415def68a4a9832617
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523485"
---
# <a name="how-to-handle-composite-keys-in-queries"></a><span data-ttu-id="e47d7-102">Как выполнить обрабатывать составные ключи в запросах</span><span class="sxs-lookup"><span data-stu-id="e47d7-102">How to: Handle Composite Keys in Queries</span></span>
<span data-ttu-id="e47d7-103">Некоторые операторы могут принимать только один аргумент.</span><span class="sxs-lookup"><span data-stu-id="e47d7-103">Some operators can take only one argument.</span></span> <span data-ttu-id="e47d7-104">Если аргумент должен содержать несколько столбцов базы данных, необходимо создать анонимный тип для представления комбинации столбцов.</span><span class="sxs-lookup"><span data-stu-id="e47d7-104">If your argument must include more than one column from the database, you must create an anonymous type to represent the combination.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e47d7-105">Пример</span><span class="sxs-lookup"><span data-stu-id="e47d7-105">Example</span></span>  
 <span data-ttu-id="e47d7-106">В следующем примере показан запрос, который вызывает оператор `GroupBy`, принимающий только один аргумент `key`.</span><span class="sxs-lookup"><span data-stu-id="e47d7-106">The following example shows a query that invokes the `GroupBy` operator, which can take only one `key` argument.</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#1)]
 [!code-vb[DLinqCompositeKeys#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="e47d7-107">Пример</span><span class="sxs-lookup"><span data-stu-id="e47d7-107">Example</span></span>  
 <span data-ttu-id="e47d7-108">Та же ситуация возникает в случае соединений, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e47d7-108">The same situation pertains to joins, as in the following example:</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#2)]
 [!code-vb[DLinqCompositeKeys#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e47d7-109">См. также</span><span class="sxs-lookup"><span data-stu-id="e47d7-109">See also</span></span>
- [<span data-ttu-id="e47d7-110">Основные принципы запросов</span><span class="sxs-lookup"><span data-stu-id="e47d7-110">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
