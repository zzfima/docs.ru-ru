---
title: '&lt;workflowInstanceManagement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9883cedbbe3657eb82c25abbad66487e39ce2579
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltworkflowinstancemanagementgt"></a><span data-ttu-id="fa4df-102">&lt;workflowInstanceManagement&gt;</span><span class="sxs-lookup"><span data-stu-id="fa4df-102">&lt;workflowInstanceManagement&gt;</span></span>
<span data-ttu-id="fa4df-103">Поведение службы, которое позволяет указать параметры, управляющие выполнением экземпляров рабочего процесса, включая сохраняемость, необработанное поведение исключения и неактивное поведение.</span><span class="sxs-lookup"><span data-stu-id="fa4df-103">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="fa4df-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="fa4df-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fa4df-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="fa4df-105">\<behaviors></span></span>  
<span data-ttu-id="fa4df-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="fa4df-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="fa4df-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="fa4df-107">\<behavior></span></span>  
<span data-ttu-id="fa4df-108">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="fa4df-108">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa4df-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa4df-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa4df-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fa4df-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fa4df-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fa4df-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa4df-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fa4df-112">Attributes</span></span>  
  
|<span data-ttu-id="fa4df-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fa4df-113">Attribute</span></span>|<span data-ttu-id="fa4df-114">Описание</span><span class="sxs-lookup"><span data-stu-id="fa4df-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fa4df-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="fa4df-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="fa4df-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fa4df-116">Child Elements</span></span>  
 <span data-ttu-id="fa4df-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fa4df-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fa4df-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fa4df-118">Parent Elements</span></span>  
  
|<span data-ttu-id="fa4df-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="fa4df-119">Element</span></span>|<span data-ttu-id="fa4df-120">Описание</span><span class="sxs-lookup"><span data-stu-id="fa4df-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa4df-121">\<поведение > из \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="fa4df-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="fa4df-122">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="fa4df-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa4df-123">См. также</span><span class="sxs-lookup"><span data-stu-id="fa4df-123">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
