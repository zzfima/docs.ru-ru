---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: caf5be7aaff0df436be3a1d618a9f89bb32e6bb7
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254854"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="3369e-101">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="3369e-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="3369e-102">Поведение службы, позволяющее задать действие, которое будет выполнено при появлении необработанного исключения в службе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="3369e-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="3369e-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3369e-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="3369e-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="3369e-104">\<behaviors></span></span>  
<span data-ttu-id="3369e-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3369e-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="3369e-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="3369e-106">\<behavior></span></span>  
<span data-ttu-id="3369e-107">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="3369e-107">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3369e-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3369e-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3369e-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3369e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3369e-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3369e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3369e-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3369e-111">Attributes</span></span>  
  
|<span data-ttu-id="3369e-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3369e-112">Attribute</span></span>|<span data-ttu-id="3369e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3369e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3369e-114">action</span><span class="sxs-lookup"><span data-stu-id="3369e-114">action</span></span>|<span data-ttu-id="3369e-115">Строка, указывающая действие, которое должно быть предпринято при возникновении необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="3369e-115">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="3369e-116">Это атрибут типа <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="3369e-116">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3369e-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3369e-117">Child Elements</span></span>  
 <span data-ttu-id="3369e-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3369e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3369e-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3369e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3369e-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="3369e-120">Element</span></span>|<span data-ttu-id="3369e-121">Описание</span><span class="sxs-lookup"><span data-stu-id="3369e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3369e-122">\<поведение > из \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3369e-122">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="3369e-123">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="3369e-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3369e-124">См. также</span><span class="sxs-lookup"><span data-stu-id="3369e-124">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
