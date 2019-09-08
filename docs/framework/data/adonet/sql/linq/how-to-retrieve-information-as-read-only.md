---
title: Практическое руководство. Как получать информацию в режиме только для чтения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
ms.openlocfilehash: 399bf44ef5536a9adebf1cad590439741df998f0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793313"
---
# <a name="how-to-retrieve-information-as-read-only"></a><span data-ttu-id="44e3a-102">Практическое руководство. Как получать информацию в режиме только для чтения</span><span class="sxs-lookup"><span data-stu-id="44e3a-102">How to: Retrieve Information As Read-Only</span></span>
<span data-ttu-id="44e3a-103">Если не планируется изменять данные, можно повысить производительность запросов за счет поиска результатов, предназначенных только для чтения.</span><span class="sxs-lookup"><span data-stu-id="44e3a-103">When you do not intend to change the data, you can increase the performance of queries by seeking read-only results.</span></span>  
  
 <span data-ttu-id="44e3a-104">Чтобы реализовать обработку запросов только для чтения, установите для свойства <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="44e3a-104">You implement read-only processing by setting <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to `false`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="44e3a-105">Если для свойства <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> установлено значение `false`, то для свойства <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> неявно устанавливается значение `false`.</span><span class="sxs-lookup"><span data-stu-id="44e3a-105">When <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> is set to `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> is implicitly set to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44e3a-106">Пример</span><span class="sxs-lookup"><span data-stu-id="44e3a-106">Example</span></span>  
 <span data-ttu-id="44e3a-107">В следующем примере кода извлекается коллекция дат приема на работу сотрудников, предназначенная только для чтения.</span><span class="sxs-lookup"><span data-stu-id="44e3a-107">The following code retrieves a read-only collection of employee hire dates.</span></span>  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="44e3a-108">См. также</span><span class="sxs-lookup"><span data-stu-id="44e3a-108">See also</span></span>

- [<span data-ttu-id="44e3a-109">Основные принципы запросов</span><span class="sxs-lookup"><span data-stu-id="44e3a-109">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="44e3a-110">Запрос к базе данных</span><span class="sxs-lookup"><span data-stu-id="44e3a-110">Querying the Database</span></span>](querying-the-database.md)
- [<span data-ttu-id="44e3a-111">Отложенная и немедленная загрузка</span><span class="sxs-lookup"><span data-stu-id="44e3a-111">Deferred versus Immediate Loading</span></span>](deferred-versus-immediate-loading.md)
