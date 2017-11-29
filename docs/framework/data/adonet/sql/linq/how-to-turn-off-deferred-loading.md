---
title: "Практическое руководство. Выключение отложенной загрузки"
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
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d98b190ef4454ff29318eb6ef0f20624c85b62a5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-turn-off-deferred-loading"></a><span data-ttu-id="61f16-102">Практическое руководство. Выключение отложенной загрузки</span><span class="sxs-lookup"><span data-stu-id="61f16-102">How to: Turn Off Deferred Loading</span></span>
<span data-ttu-id="61f16-103">Чтобы отключить отложенную загрузку, свойству <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> следует задать значение `false`.</span><span class="sxs-lookup"><span data-stu-id="61f16-103">You can turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span> <span data-ttu-id="61f16-104">Дополнительные сведения см. в разделе [отложенное или немедленное загрузки](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="61f16-104">For more information, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61f16-105">Отложенная загрузка отключается при отключении отслеживания объекта.</span><span class="sxs-lookup"><span data-stu-id="61f16-105">Deferred loading is turned off by implication when object tracking is turned off.</span></span> <span data-ttu-id="61f16-106">Дополнительные сведения см. в разделе [как: извлечения сведений как доступных только для чтения](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).</span><span class="sxs-lookup"><span data-stu-id="61f16-106">For more information, see [How to: Retrieve Information As Read-Only](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="61f16-107">Пример</span><span class="sxs-lookup"><span data-stu-id="61f16-107">Example</span></span>  
 <span data-ttu-id="61f16-108">В следующем примере показано отключение отложенной загрузки путем установки свойству <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> значения `false`.</span><span class="sxs-lookup"><span data-stu-id="61f16-108">The following example shows how to turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span>  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="61f16-109">См. также</span><span class="sxs-lookup"><span data-stu-id="61f16-109">See Also</span></span>  
 [<span data-ttu-id="61f16-110">Основные принципы запросов</span><span class="sxs-lookup"><span data-stu-id="61f16-110">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [<span data-ttu-id="61f16-111">Запросы к базе данных</span><span class="sxs-lookup"><span data-stu-id="61f16-111">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
