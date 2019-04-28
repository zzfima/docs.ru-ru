---
title: Практическое руководство. Как обнаруживать и разрешать конфликты отправки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: 606231449263f1c26596ca8606a88053c6aded8e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61877283"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a><span data-ttu-id="e5e10-102">Практическое руководство. Как обнаруживать и разрешать конфликты отправки</span><span class="sxs-lookup"><span data-stu-id="e5e10-102">How to: Detect and Resolve Conflicting Submissions</span></span>
<span data-ttu-id="e5e10-103">Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] предоставляет целый ряд ресурсов для обнаружения и разрешения конфликтов, возникающих при внесении изменений в базу данных несколькими пользователями.</span><span class="sxs-lookup"><span data-stu-id="e5e10-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides many resources for detecting and resolving conflicts that stem from multi-user changes to the database.</span></span> <span data-ttu-id="e5e10-104">Дополнительные сведения см. в разделе [Как Управление конфликтами изменений](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span><span class="sxs-lookup"><span data-stu-id="e5e10-104">For more information, see [How to: Manage Change Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5e10-105">Пример</span><span class="sxs-lookup"><span data-stu-id="e5e10-105">Example</span></span>  
 <span data-ttu-id="e5e10-106">В следующем примере показан `try` / `catch` блок, который перехватывает <xref:System.Data.Linq.ChangeConflictException> исключения.</span><span class="sxs-lookup"><span data-stu-id="e5e10-106">The following example shows a `try`/`catch` block that catches a <xref:System.Data.Linq.ChangeConflictException> exception.</span></span> <span data-ttu-id="e5e10-107">Сведения о сущностях и членах для каждого конфликта отображаются в окне «Консоль».</span><span class="sxs-lookup"><span data-stu-id="e5e10-107">Entity and member information for each conflict is displayed in the console window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5e10-108">Для поддержки извлечения этих сведений необходимо включить директиву `using System.Reflection` (`Imports System.Reflection` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="e5e10-108">You must include the `using System.Reflection` directive (`Imports System.Reflection` in Visual Basic) to support the information retrieval.</span></span> <span data-ttu-id="e5e10-109">Дополнительные сведения см. в разделе <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="e5e10-109">For more information, see <xref:System.Reflection>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e5e10-110">См. также</span><span class="sxs-lookup"><span data-stu-id="e5e10-110">See also</span></span>

- [<span data-ttu-id="e5e10-111">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="e5e10-111">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [<span data-ttu-id="e5e10-112">Практическое руководство. Управление конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="e5e10-112">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
