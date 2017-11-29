---
title: "Практическое руководство. Обнаружение и разрешение отправок, вызывающих конфликты"
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
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8eb2e27ab034d464ba6978d9ddc063e623812619
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a><span data-ttu-id="c5428-102">Практическое руководство. Обнаружение и разрешение отправок, вызывающих конфликты</span><span class="sxs-lookup"><span data-stu-id="c5428-102">How to: Detect and Resolve Conflicting Submissions</span></span>
<span data-ttu-id="c5428-103">Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] предоставляет целый ряд ресурсов для обнаружения и разрешения конфликтов, возникающих при внесении изменений в базу данных несколькими пользователями.</span><span class="sxs-lookup"><span data-stu-id="c5428-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides many resources for detecting and resolving conflicts that stem from multi-user changes to the database.</span></span> <span data-ttu-id="c5428-104">Дополнительные сведения см. в разделе [как: управление конфликтами изменений](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span><span class="sxs-lookup"><span data-stu-id="c5428-104">For more information, see [How to: Manage Change Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5428-105">Пример</span><span class="sxs-lookup"><span data-stu-id="c5428-105">Example</span></span>  
 <span data-ttu-id="c5428-106">В следующем примере показан `try` / `catch` блок, который перехватывает <xref:System.Data.Linq.ChangeConflictException> исключения.</span><span class="sxs-lookup"><span data-stu-id="c5428-106">The following example shows a `try`/`catch` block that catches a <xref:System.Data.Linq.ChangeConflictException> exception.</span></span> <span data-ttu-id="c5428-107">Сведения о сущностях и членах для каждого конфликта отображаются в окне «Консоль».</span><span class="sxs-lookup"><span data-stu-id="c5428-107">Entity and member information for each conflict is displayed in the console window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5428-108">Для поддержки извлечения этих сведений необходимо включить директиву `using System.Reflection` (`Imports System.Reflection` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="c5428-108">You must include the `using System.Reflection` directive (`Imports System.Reflection` in Visual Basic) to support the information retrieval.</span></span> <span data-ttu-id="c5428-109">Для получения дополнительной информации см. <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="c5428-109">For more information, see <xref:System.Reflection>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c5428-110">См. также</span><span class="sxs-lookup"><span data-stu-id="c5428-110">See Also</span></span>  
 [<span data-ttu-id="c5428-111">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="c5428-111">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [<span data-ttu-id="c5428-112">Как: управление конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="c5428-112">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
