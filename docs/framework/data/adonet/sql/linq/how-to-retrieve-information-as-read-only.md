---
title: "Практическое руководство. Получение сведений как доступных только для чтения"
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
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 04a20a06cd8ed8785b37bdc604a817b475f93873
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-retrieve-information-as-read-only"></a><span data-ttu-id="0965b-102">Практическое руководство. Получение сведений как доступных только для чтения</span><span class="sxs-lookup"><span data-stu-id="0965b-102">How to: Retrieve Information As Read-Only</span></span>
<span data-ttu-id="0965b-103">Если не планируется изменять данные, можно повысить производительность запросов за счет поиска результатов, предназначенных только для чтения.</span><span class="sxs-lookup"><span data-stu-id="0965b-103">When you do not intend to change the data, you can increase the performance of queries by seeking read-only results.</span></span>  
  
 <span data-ttu-id="0965b-104">Чтобы реализовать обработку запросов только для чтения, установите для свойства <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="0965b-104">You implement read-only processing by setting <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0965b-105">Если для свойства <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> установлено значение `false`, то для свойства <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> неявно устанавливается значение `false`.</span><span class="sxs-lookup"><span data-stu-id="0965b-105">When <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> is set to `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> is implicitly set to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0965b-106">Пример</span><span class="sxs-lookup"><span data-stu-id="0965b-106">Example</span></span>  
 <span data-ttu-id="0965b-107">В следующем примере кода извлекается коллекция дат приема на работу сотрудников, предназначенная только для чтения.</span><span class="sxs-lookup"><span data-stu-id="0965b-107">The following code retrieves a read-only collection of employee hire dates.</span></span>  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="0965b-108">См. также</span><span class="sxs-lookup"><span data-stu-id="0965b-108">See Also</span></span>  
 [<span data-ttu-id="0965b-109">Основные принципы запросов</span><span class="sxs-lookup"><span data-stu-id="0965b-109">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [<span data-ttu-id="0965b-110">Запрос к базе данных</span><span class="sxs-lookup"><span data-stu-id="0965b-110">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)  
 [<span data-ttu-id="0965b-111">Отложенная и немедленная загрузка</span><span class="sxs-lookup"><span data-stu-id="0965b-111">Deferred versus Immediate Loading</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)
