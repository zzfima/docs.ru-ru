---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: 98bc1b24da6e65a11a39d133057c1bb55b003a58
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191618"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="5c586-101">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="5c586-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="5c586-102">Поведение службы, которое позволяет указать параметры, управляющие выполнением экземпляров рабочего процесса, включая сохраняемость, необработанное поведение исключения и неактивное поведение.</span><span class="sxs-lookup"><span data-stu-id="5c586-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="5c586-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5c586-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5c586-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="5c586-104">\<behaviors></span></span>  
<span data-ttu-id="5c586-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5c586-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="5c586-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="5c586-106">\<behavior></span></span>  
<span data-ttu-id="5c586-107">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="5c586-107">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c586-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c586-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c586-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5c586-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5c586-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5c586-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c586-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5c586-111">Attributes</span></span>  
  
|<span data-ttu-id="5c586-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5c586-112">Attribute</span></span>|<span data-ttu-id="5c586-113">Описание</span><span class="sxs-lookup"><span data-stu-id="5c586-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5c586-114">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="5c586-114">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="5c586-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5c586-115">Child Elements</span></span>  
 <span data-ttu-id="5c586-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5c586-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5c586-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5c586-117">Parent Elements</span></span>  
  
|<span data-ttu-id="5c586-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="5c586-118">Element</span></span>|<span data-ttu-id="5c586-119">Описание</span><span class="sxs-lookup"><span data-stu-id="5c586-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c586-120">\<поведение > из \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5c586-120">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="5c586-121">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="5c586-121">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c586-122">См. также</span><span class="sxs-lookup"><span data-stu-id="5c586-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
