---
title: Постоянные выражения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9d98a7be-b110-4edb-8eba-bed10f250b6d
ms.openlocfilehash: c9d4fa345f708ab5997b03e4e9726875d041ca21
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565947"
---
# <a name="constant-expressions"></a><span data-ttu-id="4660d-102">Постоянные выражения</span><span class="sxs-lookup"><span data-stu-id="4660d-102">Constant Expressions</span></span>
<span data-ttu-id="4660d-103">Константное выражение состоит из постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="4660d-103">A constant expression consists of a constant value.</span></span> <span data-ttu-id="4660d-104">Постоянные значения непосредственно преобразуются в константные выражения дерева команд и не преобразуются на клиенте.</span><span class="sxs-lookup"><span data-stu-id="4660d-104">Constant values are directly converted to constant command tree expressions, without any translation on the client.</span></span> <span data-ttu-id="4660d-105">К ним относятся выражения, результатом которых является постоянное значение.</span><span class="sxs-lookup"><span data-stu-id="4660d-105">This includes expressions that result in a constant value.</span></span> <span data-ttu-id="4660d-106">Поэтому для всех выражений с константами следует ожидать поведения источника данных.</span><span class="sxs-lookup"><span data-stu-id="4660d-106">Therefore, data source behavior should be expected for all expressions involving constants.</span></span> <span data-ttu-id="4660d-107">Это поведение может отличаться от поведения среды CLR.</span><span class="sxs-lookup"><span data-stu-id="4660d-107">This can result in behavior that differs from CLR behavior.</span></span>  
  
 <span data-ttu-id="4660d-108">В следующем примере показано константное выражение, вычисляемое на сервере.</span><span class="sxs-lookup"><span data-stu-id="4660d-108">The following example shows a constant expression that is evaluated on the server.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 <span data-ttu-id="4660d-109">Технология [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] не поддерживает использование пользовательского класса в качестве константы.</span><span class="sxs-lookup"><span data-stu-id="4660d-109">[!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] does not support using a user class as a constant.</span></span> <span data-ttu-id="4660d-110">Однако ссылка на свойство пользовательского класса считается константой; она будет преобразована в константное выражение дерева команд и выполнена в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="4660d-110">However, a property reference on a user class is considered a constant, and will be converted to a command tree constant expression and executed on the data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4660d-111">См. также</span><span class="sxs-lookup"><span data-stu-id="4660d-111">See also</span></span>
- [<span data-ttu-id="4660d-112">Выражения в запросах LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="4660d-112">Expressions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
