---
title: Практическое руководство. Как обнаруживать и разрешать конфликты отправки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: ff33196f83e2c0d8d759e4ffc3fb7442e8ba0e3b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940099"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a><span data-ttu-id="9c13a-102">Практическое руководство. Как обнаруживать и разрешать конфликты отправки</span><span class="sxs-lookup"><span data-stu-id="9c13a-102">How to: Detect and Resolve Conflicting Submissions</span></span>
<span data-ttu-id="9c13a-103">Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] предоставляет целый ряд ресурсов для обнаружения и разрешения конфликтов, возникающих при внесении изменений в базу данных несколькими пользователями.</span><span class="sxs-lookup"><span data-stu-id="9c13a-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides many resources for detecting and resolving conflicts that stem from multi-user changes to the database.</span></span> <span data-ttu-id="9c13a-104">Дополнительные сведения см. в разделе [Практическое руководство. Управление конфликтами](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)изменений.</span><span class="sxs-lookup"><span data-stu-id="9c13a-104">For more information, see [How to: Manage Change Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c13a-105">Пример</span><span class="sxs-lookup"><span data-stu-id="9c13a-105">Example</span></span>  
 <span data-ttu-id="9c13a-106">`try` В следующем примере показан / `catch` блок, который перехватывает <xref:System.Data.Linq.ChangeConflictException> исключение.</span><span class="sxs-lookup"><span data-stu-id="9c13a-106">The following example shows a `try`/`catch` block that catches a <xref:System.Data.Linq.ChangeConflictException> exception.</span></span> <span data-ttu-id="9c13a-107">Сведения о сущностях и членах для каждого конфликта отображаются в окне «Консоль».</span><span class="sxs-lookup"><span data-stu-id="9c13a-107">Entity and member information for each conflict is displayed in the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c13a-108">Для поддержки извлечения этих сведений необходимо включить директиву `using System.Reflection` (`Imports System.Reflection` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="9c13a-108">You must include the `using System.Reflection` directive (`Imports System.Reflection` in Visual Basic) to support the information retrieval.</span></span> <span data-ttu-id="9c13a-109">Дополнительные сведения см. в разделе <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="9c13a-109">For more information, see <xref:System.Reflection>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9c13a-110">См. также</span><span class="sxs-lookup"><span data-stu-id="9c13a-110">See also</span></span>

- [<span data-ttu-id="9c13a-111">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="9c13a-111">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [<span data-ttu-id="9c13a-112">Практическое руководство. Управление конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="9c13a-112">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
