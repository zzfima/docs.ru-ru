---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: cfe3350ac42d1e0e837b79f25753f62dc2051dd2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61613396"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="33531-101">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="33531-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="33531-102">Поведение службы, позволяющее задать действие, которое будет выполнено при появлении необработанного исключения в службе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="33531-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="33531-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="33531-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="33531-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="33531-104">\<behaviors></span></span>  
<span data-ttu-id="33531-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="33531-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="33531-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="33531-106">\<behavior></span></span>  
<span data-ttu-id="33531-107">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="33531-107">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33531-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33531-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33531-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="33531-109">Attributes and Elements</span></span>  
 <span data-ttu-id="33531-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="33531-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33531-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="33531-111">Attributes</span></span>  
  
|<span data-ttu-id="33531-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="33531-112">Attribute</span></span>|<span data-ttu-id="33531-113">Описание</span><span class="sxs-lookup"><span data-stu-id="33531-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="33531-114">action</span><span class="sxs-lookup"><span data-stu-id="33531-114">action</span></span>|<span data-ttu-id="33531-115">Строка, указывающая действие, которое должно быть предпринято при возникновении необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="33531-115">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="33531-116">Это атрибут типа <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="33531-116">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33531-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="33531-117">Child Elements</span></span>  
 <span data-ttu-id="33531-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="33531-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="33531-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="33531-119">Parent Elements</span></span>  
  
|<span data-ttu-id="33531-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="33531-120">Element</span></span>|<span data-ttu-id="33531-121">Описание</span><span class="sxs-lookup"><span data-stu-id="33531-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33531-122">\<поведение > из \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="33531-122">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="33531-123">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="33531-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="33531-124">См. также</span><span class="sxs-lookup"><span data-stu-id="33531-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
