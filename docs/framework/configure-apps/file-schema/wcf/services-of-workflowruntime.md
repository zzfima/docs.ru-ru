---
title: <services> из <workflowRuntime>
ms.date: 03/30/2017
ms.assetid: 219a05b1-f573-45c9-849b-e86bc373b62f
ms.openlocfilehash: 1106a9c62f4b57a2a695343c26879b2adf0934de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159709"
---
# <a name="services-of-workflowruntime"></a><span data-ttu-id="4d4b4-102">\<Services > из \<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="4d4b4-102">\<services> of \<workflowRuntime></span></span>
<span data-ttu-id="4d4b4-103">Представляет коллекцию служб, добавляемую в подсистему <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="4d4b4-103">Represents a collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="4d4b4-104">Элементы имеют тип <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="4d4b4-104">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="4d4b4-105">Службы, указанные в коллекции, инициализируются механизмом среды выполнения рабочих процессов и добавляются в службы при вызове соответствующего конструктора <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="4d4b4-105">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="4d4b4-106">Таким образом, службы, указанные в коллекции, должны отвечать определенным правилам в отношении сигнатур конструкторов.</span><span class="sxs-lookup"><span data-stu-id="4d4b4-106">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="4d4b4-107">Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="4d4b4-107">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d4b4-108">См. также</span><span class="sxs-lookup"><span data-stu-id="4d4b4-108">See also</span></span>

- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- [<span data-ttu-id="4d4b4-109">Файлы конфигурации рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="4d4b4-109">Workflow Configuration Files</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))
