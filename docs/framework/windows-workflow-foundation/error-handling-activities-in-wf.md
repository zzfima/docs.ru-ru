---
title: "Действия по обработке ошибок в WF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24b68bd3-cef5-4413-ab82-2e2625f209aa
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96a868cd28823c3185d1297f7709dcfdc28a14a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="error-handling-activities-in-wf"></a><span data-ttu-id="b5e51-102">Действия по обработке ошибок в WF</span><span class="sxs-lookup"><span data-stu-id="b5e51-102">Error Handling Activities in WF</span></span>
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]<span data-ttu-id="b5e51-103"> содержит несколько предоставляемых системой действий для реализации обработки ошибок и восстановления.</span><span class="sxs-lookup"><span data-stu-id="b5e51-103"> provides several system-provided activities for implementing error handling and recovery.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="b5e51-104">[Исключения](../../../docs/framework/windows-workflow-foundation/exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="b5e51-104"> [Exceptions](../../../docs/framework/windows-workflow-foundation/exceptions.md).</span></span>  
  
## <a name="error-handling-activities"></a><span data-ttu-id="b5e51-105">Действия по обработке ошибок</span><span class="sxs-lookup"><span data-stu-id="b5e51-105">Error handling activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.Rethrow>|<span data-ttu-id="b5e51-106">Повторно формирует последнее исключение из действия `TryCatch`.</span><span class="sxs-lookup"><span data-stu-id="b5e51-106">Rethrows the last exception thrown from within a `TryCatch` activity.</span></span>|  
|<xref:System.Activities.Statements.Throw>|<span data-ttu-id="b5e51-107">Создает исключение.</span><span class="sxs-lookup"><span data-stu-id="b5e51-107">Throws an exception.</span></span>|  
|<xref:System.Activities.Statements.TryCatch>|<span data-ttu-id="b5e51-108">Реализует обработку исключений.</span><span class="sxs-lookup"><span data-stu-id="b5e51-108">Implements exception handling.</span></span>|
