---
title: '&lt;services&gt; для &lt;workflowRuntime&gt;'
ms.date: 03/30/2017
ms.assetid: 219a05b1-f573-45c9-849b-e86bc373b62f
ms.openlocfilehash: 44da735ab1aa2391fe882dfba6e1afc47be746ff
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47086357"
---
# <a name="ltservicesgt-of-ltworkflowruntimegt"></a><span data-ttu-id="2dfb3-102">&lt;services&gt; для &lt;workflowRuntime&gt;</span><span class="sxs-lookup"><span data-stu-id="2dfb3-102">&lt;services&gt; of &lt;workflowRuntime&gt;</span></span>
<span data-ttu-id="2dfb3-103">Представляет коллекцию служб, добавляемую в подсистему <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-103">Represents a collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="2dfb3-104">Элементы имеют тип <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-104">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="2dfb3-105">Службы, указанные в коллекции, инициализируются механизмом среды выполнения рабочих процессов и добавляются в службы при вызове соответствующего конструктора <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-105">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="2dfb3-106">Таким образом, службы, указанные в коллекции, должны отвечать определенным правилам в отношении сигнатур конструкторов.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-106">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="2dfb3-107">Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="2dfb3-107">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dfb3-108">См. также</span><span class="sxs-lookup"><span data-stu-id="2dfb3-108">See Also</span></span>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <span data-ttu-id="2dfb3-109">[Файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="2dfb3-109">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
