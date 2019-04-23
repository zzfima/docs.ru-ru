---
title: Практическое руководство. Как отключить отложенную загрузку
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: f82e347ecdb3c69cee3749855d1e4cb457a460f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112961"
---
# <a name="how-to-turn-off-deferred-loading"></a><span data-ttu-id="cfdf9-102">Практическое руководство. Как отключить отложенную загрузку</span><span class="sxs-lookup"><span data-stu-id="cfdf9-102">How to: Turn Off Deferred Loading</span></span>
<span data-ttu-id="cfdf9-103">Чтобы отключить отложенную загрузку, свойству <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> следует задать значение `false`.</span><span class="sxs-lookup"><span data-stu-id="cfdf9-103">You can turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span> <span data-ttu-id="cfdf9-104">Дополнительные сведения см. в разделе [отложенное или немедленное Загрузка](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="cfdf9-104">For more information, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cfdf9-105">Отложенная загрузка отключается при отключении отслеживания объекта.</span><span class="sxs-lookup"><span data-stu-id="cfdf9-105">Deferred loading is turned off by implication when object tracking is turned off.</span></span> <span data-ttu-id="cfdf9-106">Дополнительные сведения см. в разделе [Как Получение сведений как доступных только для чтения](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).</span><span class="sxs-lookup"><span data-stu-id="cfdf9-106">For more information, see [How to: Retrieve Information As Read-Only](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfdf9-107">Пример</span><span class="sxs-lookup"><span data-stu-id="cfdf9-107">Example</span></span>  
 <span data-ttu-id="cfdf9-108">В следующем примере показано отключение отложенной загрузки путем установки свойству <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> значения `false`.</span><span class="sxs-lookup"><span data-stu-id="cfdf9-108">The following example shows how to turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span>  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="cfdf9-109">См. также</span><span class="sxs-lookup"><span data-stu-id="cfdf9-109">See also</span></span>

- [<span data-ttu-id="cfdf9-110">Основные принципы запросов</span><span class="sxs-lookup"><span data-stu-id="cfdf9-110">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [<span data-ttu-id="cfdf9-111">Запрос к базе данных</span><span class="sxs-lookup"><span data-stu-id="cfdf9-111">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
