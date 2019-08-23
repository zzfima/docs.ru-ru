---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: c46d1fb9eb853e57c7ad1b97eb9a22556cdfb7d8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913101"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="42b46-101">\<Воркфловунхандледексцептион ></span><span class="sxs-lookup"><span data-stu-id="42b46-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="42b46-102">Поведение службы, позволяющее задать действие, которое будет выполнено при появлении необработанного исключения в службе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="42b46-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="42b46-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="42b46-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="42b46-104">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="42b46-104">\<behaviors></span></span>  
<span data-ttu-id="42b46-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="42b46-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="42b46-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="42b46-106">\<behavior></span></span>  
<span data-ttu-id="42b46-107">\<Воркфловунхандледексцептион ></span><span class="sxs-lookup"><span data-stu-id="42b46-107">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42b46-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42b46-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42b46-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="42b46-109">Attributes and Elements</span></span>  
 <span data-ttu-id="42b46-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="42b46-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42b46-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="42b46-111">Attributes</span></span>  
  
|<span data-ttu-id="42b46-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="42b46-112">Attribute</span></span>|<span data-ttu-id="42b46-113">Описание</span><span class="sxs-lookup"><span data-stu-id="42b46-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42b46-114">действие</span><span class="sxs-lookup"><span data-stu-id="42b46-114">action</span></span>|<span data-ttu-id="42b46-115">Строка, указывающая действие, которое должно быть предпринято при возникновении необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="42b46-115">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="42b46-116">Это атрибут типа <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="42b46-116">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42b46-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="42b46-117">Child Elements</span></span>  
 <span data-ttu-id="42b46-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="42b46-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="42b46-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="42b46-119">Parent Elements</span></span>  
  
|<span data-ttu-id="42b46-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="42b46-120">Element</span></span>|<span data-ttu-id="42b46-121">Описание</span><span class="sxs-lookup"><span data-stu-id="42b46-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42b46-122">\<> поведения > \<serviceBehaviors</span><span class="sxs-lookup"><span data-stu-id="42b46-122">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="42b46-123">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="42b46-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="42b46-124">См. также</span><span class="sxs-lookup"><span data-stu-id="42b46-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
