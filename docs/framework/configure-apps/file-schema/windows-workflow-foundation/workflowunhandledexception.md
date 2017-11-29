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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9b3e9450721de526aa489500f152a277acc52178
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltworkflowunhandledexceptiongt"></a><span data-ttu-id="67f1c-102">&lt;workflowUnhandledException&gt;</span><span class="sxs-lookup"><span data-stu-id="67f1c-102">&lt;workflowUnhandledException&gt;</span></span>
<span data-ttu-id="67f1c-103">Поведение службы, позволяющее задать действие, которое будет выполнено при появлении необработанного исключения в службе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="67f1c-103">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="67f1c-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="67f1c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="67f1c-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="67f1c-105">\<behaviors></span></span>  
<span data-ttu-id="67f1c-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="67f1c-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="67f1c-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="67f1c-107">\<behavior></span></span>  
<span data-ttu-id="67f1c-108">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="67f1c-108">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67f1c-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67f1c-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67f1c-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="67f1c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="67f1c-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="67f1c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67f1c-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="67f1c-112">Attributes</span></span>  
  
|<span data-ttu-id="67f1c-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="67f1c-113">Attribute</span></span>|<span data-ttu-id="67f1c-114">Описание</span><span class="sxs-lookup"><span data-stu-id="67f1c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="67f1c-115">action</span><span class="sxs-lookup"><span data-stu-id="67f1c-115">action</span></span>|<span data-ttu-id="67f1c-116">Строка, указывающая действие, которое должно быть предпринято при возникновении необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="67f1c-116">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="67f1c-117">Это атрибут типа <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="67f1c-117">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="67f1c-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="67f1c-118">Child Elements</span></span>  
 <span data-ttu-id="67f1c-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="67f1c-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="67f1c-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="67f1c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="67f1c-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="67f1c-121">Element</span></span>|<span data-ttu-id="67f1c-122">Описание</span><span class="sxs-lookup"><span data-stu-id="67f1c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67f1c-123">\<поведение > из \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="67f1c-123">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="67f1c-124">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="67f1c-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="67f1c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="67f1c-125">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
