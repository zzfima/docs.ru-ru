---
title: '&lt;workflowUnhandledException&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: d9db6ecc2e95e0d1ec5738f1d2f4a09a89c57f21
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltworkflowunhandledexceptiongt"></a><span data-ttu-id="73aac-102">&lt;workflowUnhandledException&gt;</span><span class="sxs-lookup"><span data-stu-id="73aac-102">&lt;workflowUnhandledException&gt;</span></span>
<span data-ttu-id="73aac-103">Поведение службы, позволяющее задать действие, которое будет выполнено при появлении необработанного исключения в службе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="73aac-103">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="73aac-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="73aac-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="73aac-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="73aac-105">\<behaviors></span></span>  
<span data-ttu-id="73aac-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="73aac-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="73aac-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="73aac-107">\<behavior></span></span>  
<span data-ttu-id="73aac-108">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="73aac-108">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73aac-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73aac-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73aac-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="73aac-110">Attributes and Elements</span></span>  
 <span data-ttu-id="73aac-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="73aac-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73aac-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="73aac-112">Attributes</span></span>  
  
|<span data-ttu-id="73aac-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="73aac-113">Attribute</span></span>|<span data-ttu-id="73aac-114">Описание</span><span class="sxs-lookup"><span data-stu-id="73aac-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="73aac-115">action</span><span class="sxs-lookup"><span data-stu-id="73aac-115">action</span></span>|<span data-ttu-id="73aac-116">Строка, указывающая действие, которое должно быть предпринято при возникновении необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="73aac-116">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="73aac-117">Это атрибут типа <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="73aac-117">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73aac-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="73aac-118">Child Elements</span></span>  
 <span data-ttu-id="73aac-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="73aac-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73aac-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="73aac-120">Parent Elements</span></span>  
  
|<span data-ttu-id="73aac-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="73aac-121">Element</span></span>|<span data-ttu-id="73aac-122">Описание</span><span class="sxs-lookup"><span data-stu-id="73aac-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73aac-123">\<поведение > из \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="73aac-123">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="73aac-124">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="73aac-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="73aac-125">См. также</span><span class="sxs-lookup"><span data-stu-id="73aac-125">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
