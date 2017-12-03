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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 28e0f2b0ed88ee73edb52a8c18346746beb34771
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltworkflowinstancemanagementgt"></a><span data-ttu-id="eb80a-102">&lt;workflowInstanceManagement&gt;</span><span class="sxs-lookup"><span data-stu-id="eb80a-102">&lt;workflowInstanceManagement&gt;</span></span>
<span data-ttu-id="eb80a-103">Поведение службы, которое позволяет указать параметры, управляющие выполнением экземпляров рабочего процесса, включая сохраняемость, необработанное поведение исключения и неактивное поведение.</span><span class="sxs-lookup"><span data-stu-id="eb80a-103">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="eb80a-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="eb80a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="eb80a-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="eb80a-105">\<behaviors></span></span>  
<span data-ttu-id="eb80a-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="eb80a-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="eb80a-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="eb80a-107">\<behavior></span></span>  
<span data-ttu-id="eb80a-108">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="eb80a-108">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb80a-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb80a-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb80a-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="eb80a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="eb80a-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="eb80a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb80a-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="eb80a-112">Attributes</span></span>  
  
|<span data-ttu-id="eb80a-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="eb80a-113">Attribute</span></span>|<span data-ttu-id="eb80a-114">Описание</span><span class="sxs-lookup"><span data-stu-id="eb80a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eb80a-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="eb80a-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="eb80a-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="eb80a-116">Child Elements</span></span>  
 <span data-ttu-id="eb80a-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="eb80a-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb80a-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="eb80a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="eb80a-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="eb80a-119">Element</span></span>|<span data-ttu-id="eb80a-120">Описание</span><span class="sxs-lookup"><span data-stu-id="eb80a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb80a-121">\<поведение > из \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="eb80a-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="eb80a-122">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="eb80a-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb80a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="eb80a-123">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
