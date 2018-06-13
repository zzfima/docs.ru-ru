---
title: '&lt;workflowInstanceManagement&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: d86b0f61c6741fa156e04da75a62853f459324d1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32767106"
---
# <a name="ltworkflowinstancemanagementgt"></a><span data-ttu-id="fd109-102">&lt;workflowInstanceManagement&gt;</span><span class="sxs-lookup"><span data-stu-id="fd109-102">&lt;workflowInstanceManagement&gt;</span></span>
<span data-ttu-id="fd109-103">Поведение службы, которое позволяет указать параметры, управляющие выполнением экземпляров рабочего процесса, включая сохраняемость, необработанное поведение исключения и неактивное поведение.</span><span class="sxs-lookup"><span data-stu-id="fd109-103">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="fd109-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="fd109-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fd109-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="fd109-105">\<behaviors></span></span>  
<span data-ttu-id="fd109-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="fd109-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="fd109-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="fd109-107">\<behavior></span></span>  
<span data-ttu-id="fd109-108">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="fd109-108">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd109-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd109-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd109-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fd109-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fd109-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fd109-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd109-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fd109-112">Attributes</span></span>  
  
|<span data-ttu-id="fd109-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fd109-113">Attribute</span></span>|<span data-ttu-id="fd109-114">Описание</span><span class="sxs-lookup"><span data-stu-id="fd109-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fd109-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="fd109-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="fd109-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fd109-116">Child Elements</span></span>  
 <span data-ttu-id="fd109-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fd109-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fd109-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fd109-118">Parent Elements</span></span>  
  
|<span data-ttu-id="fd109-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="fd109-119">Element</span></span>|<span data-ttu-id="fd109-120">Описание</span><span class="sxs-lookup"><span data-stu-id="fd109-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd109-121">\<поведение > из \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="fd109-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="fd109-122">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="fd109-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fd109-123">См. также</span><span class="sxs-lookup"><span data-stu-id="fd109-123">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
