---
title: Действия по обработке ошибок в WF
ms.date: 03/30/2017
ms.assetid: 24b68bd3-cef5-4413-ab82-2e2625f209aa
ms.openlocfilehash: 51431e367f0ec8874588a52cb4dbd76d714768fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="error-handling-activities-in-wf"></a><span data-ttu-id="3eb5b-102">Действия по обработке ошибок в WF</span><span class="sxs-lookup"><span data-stu-id="3eb5b-102">Error Handling Activities in WF</span></span>
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]<span data-ttu-id="3eb5b-103"> содержит несколько предоставляемых системой действий для реализации обработки ошибок и восстановления.</span><span class="sxs-lookup"><span data-stu-id="3eb5b-103"> provides several system-provided activities for implementing error handling and recovery.</span></span> <span data-ttu-id="3eb5b-104">Дополнительные сведения см. в разделе [исключения](../../../docs/framework/windows-workflow-foundation/exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="3eb5b-104">For more information, see [Exceptions](../../../docs/framework/windows-workflow-foundation/exceptions.md).</span></span>  
  
## <a name="error-handling-activities"></a><span data-ttu-id="3eb5b-105">Действия по обработке ошибок</span><span class="sxs-lookup"><span data-stu-id="3eb5b-105">Error handling activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.Rethrow>|<span data-ttu-id="3eb5b-106">Повторно формирует последнее исключение из действия `TryCatch`.</span><span class="sxs-lookup"><span data-stu-id="3eb5b-106">Rethrows the last exception thrown from within a `TryCatch` activity.</span></span>|  
|<xref:System.Activities.Statements.Throw>|<span data-ttu-id="3eb5b-107">Создает исключение.</span><span class="sxs-lookup"><span data-stu-id="3eb5b-107">Throws an exception.</span></span>|  
|<xref:System.Activities.Statements.TryCatch>|<span data-ttu-id="3eb5b-108">Реализует обработку исключений.</span><span class="sxs-lookup"><span data-stu-id="3eb5b-108">Implements exception handling.</span></span>|
