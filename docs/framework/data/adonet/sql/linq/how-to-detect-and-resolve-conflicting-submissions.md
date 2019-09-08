---
title: Практическое руководство. Как обнаруживать и разрешать конфликты отправки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: 2de0182cc0b87768a9cff553b7ec6e77f8ccc7b8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793771"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a><span data-ttu-id="e4d6d-102">Практическое руководство. Как обнаруживать и разрешать конфликты отправки</span><span class="sxs-lookup"><span data-stu-id="e4d6d-102">How to: Detect and Resolve Conflicting Submissions</span></span>
<span data-ttu-id="e4d6d-103">Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] предоставляет целый ряд ресурсов для обнаружения и разрешения конфликтов, возникающих при внесении изменений в базу данных несколькими пользователями.</span><span class="sxs-lookup"><span data-stu-id="e4d6d-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides many resources for detecting and resolving conflicts that stem from multi-user changes to the database.</span></span> <span data-ttu-id="e4d6d-104">Дополнительные сведения см. в разделе [Практическое руководство. Управление конфликтами](how-to-manage-change-conflicts.md)изменений.</span><span class="sxs-lookup"><span data-stu-id="e4d6d-104">For more information, see [How to: Manage Change Conflicts](how-to-manage-change-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4d6d-105">Пример</span><span class="sxs-lookup"><span data-stu-id="e4d6d-105">Example</span></span>  
 <span data-ttu-id="e4d6d-106">`try` В следующем примере показан / `catch` блок, который перехватывает <xref:System.Data.Linq.ChangeConflictException> исключение.</span><span class="sxs-lookup"><span data-stu-id="e4d6d-106">The following example shows a `try`/`catch` block that catches a <xref:System.Data.Linq.ChangeConflictException> exception.</span></span> <span data-ttu-id="e4d6d-107">Сведения о сущностях и членах для каждого конфликта отображаются в окне «Консоль».</span><span class="sxs-lookup"><span data-stu-id="e4d6d-107">Entity and member information for each conflict is displayed in the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e4d6d-108">Для поддержки извлечения этих сведений необходимо включить директиву `using System.Reflection` (`Imports System.Reflection` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="e4d6d-108">You must include the `using System.Reflection` directive (`Imports System.Reflection` in Visual Basic) to support the information retrieval.</span></span> <span data-ttu-id="e4d6d-109">Дополнительные сведения см. в разделе <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="e4d6d-109">For more information, see <xref:System.Reflection>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e4d6d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="e4d6d-110">See also</span></span>

- [<span data-ttu-id="e4d6d-111">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="e4d6d-111">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
- [<span data-ttu-id="e4d6d-112">Практическое руководство. Управление конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="e4d6d-112">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
