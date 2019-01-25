---
title: Как выполнить получить сведения о конфликтах сущностей
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9a02b608-e7bb-4041-a452-a7fed26fd008
ms.openlocfilehash: 1c2f9a5f822d8783f997c9c5c09ef508c2d8dca7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629037"
---
# <a name="how-to-retrieve-entity-conflict-information"></a><span data-ttu-id="71a2e-102">Как выполнить получить сведения о конфликтах сущностей</span><span class="sxs-lookup"><span data-stu-id="71a2e-102">How to: Retrieve Entity Conflict Information</span></span>
<span data-ttu-id="71a2e-103">Для предоставления сведений о конфликтах, обнаруженных посредством исключений <xref:System.Data.Linq.ObjectChangeConflict>, можно использовать объекты класса <xref:System.Data.Linq.ChangeConflictException>.</span><span class="sxs-lookup"><span data-stu-id="71a2e-103">You can use objects of the <xref:System.Data.Linq.ObjectChangeConflict> class to provide information about conflicts revealed by <xref:System.Data.Linq.ChangeConflictException> exceptions.</span></span> <span data-ttu-id="71a2e-104">Дополнительные сведения см. в разделе [оптимистичный параллелизм: Общие сведения о](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="71a2e-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="71a2e-105">Пример</span><span class="sxs-lookup"><span data-stu-id="71a2e-105">Example</span></span>  
 <span data-ttu-id="71a2e-106">В следующем примере выполняется итерация списка накопленных конфликтов.</span><span class="sxs-lookup"><span data-stu-id="71a2e-106">The following example iterates through a list of accumulated conflicts.</span></span>  
  
 [!code-csharp[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.objectchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.objectchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="71a2e-107">См. также</span><span class="sxs-lookup"><span data-stu-id="71a2e-107">See also</span></span>
- [<span data-ttu-id="71a2e-108">Практическое руководство. Управление конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="71a2e-108">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
