---
title: '&lt;workflowUnhandledException&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4266eb6480c98c7ea1b96f2325a018b0fdcba041
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltworkflowunhandledexceptiongt"></a><span data-ttu-id="b2af8-102">&lt;workflowUnhandledException&gt;</span><span class="sxs-lookup"><span data-stu-id="b2af8-102">&lt;workflowUnhandledException&gt;</span></span>
<span data-ttu-id="b2af8-103">Поведение службы, позволяющее задать действие, которое будет выполнено при появлении необработанного исключения в службе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b2af8-103">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="b2af8-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b2af8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b2af8-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="b2af8-105">\<behaviors></span></span>  
<span data-ttu-id="b2af8-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="b2af8-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="b2af8-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="b2af8-107">\<behavior></span></span>  
<span data-ttu-id="b2af8-108">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="b2af8-108">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2af8-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2af8-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2af8-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b2af8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b2af8-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b2af8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2af8-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b2af8-112">Attributes</span></span>  
  
|<span data-ttu-id="b2af8-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b2af8-113">Attribute</span></span>|<span data-ttu-id="b2af8-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b2af8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b2af8-115">action</span><span class="sxs-lookup"><span data-stu-id="b2af8-115">action</span></span>|<span data-ttu-id="b2af8-116">Строка, указывающая действие, которое должно быть предпринято при возникновении необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="b2af8-116">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="b2af8-117">Это атрибут типа <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="b2af8-117">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2af8-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b2af8-118">Child Elements</span></span>  
 <span data-ttu-id="b2af8-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b2af8-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b2af8-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b2af8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b2af8-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="b2af8-121">Element</span></span>|<span data-ttu-id="b2af8-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="b2af8-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2af8-123">\<поведение > из \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="b2af8-123">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="b2af8-124">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="b2af8-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b2af8-125">См. также</span><span class="sxs-lookup"><span data-stu-id="b2af8-125">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
