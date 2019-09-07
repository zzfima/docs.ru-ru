---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: 29b6d8982e712a0fa595b3103803f1795adea892
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398565"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="62517-101">\<Воркфловунхандледексцептион ></span><span class="sxs-lookup"><span data-stu-id="62517-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="62517-102">Поведение службы, позволяющее задать действие, которое будет выполнено при появлении необработанного исключения в службе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="62517-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="62517-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="62517-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="62517-104">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="62517-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="62517-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="62517-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="62517-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="62517-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="62517-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="62517-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="62517-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Воркфловунхандледексцептион >**</span><span class="sxs-lookup"><span data-stu-id="62517-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowUnhandledException>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62517-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62517-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62517-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="62517-110">Attributes and Elements</span></span>  
 <span data-ttu-id="62517-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="62517-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62517-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="62517-112">Attributes</span></span>  
  
|<span data-ttu-id="62517-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="62517-113">Attribute</span></span>|<span data-ttu-id="62517-114">Описание</span><span class="sxs-lookup"><span data-stu-id="62517-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="62517-115">действие</span><span class="sxs-lookup"><span data-stu-id="62517-115">action</span></span>|<span data-ttu-id="62517-116">Строка, указывающая действие, которое должно быть предпринято при возникновении необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="62517-116">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="62517-117">Это атрибут типа <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="62517-117">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62517-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="62517-118">Child Elements</span></span>  
 <span data-ttu-id="62517-119">Нет.</span><span class="sxs-lookup"><span data-stu-id="62517-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="62517-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="62517-120">Parent Elements</span></span>  
  
|<span data-ttu-id="62517-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="62517-121">Element</span></span>|<span data-ttu-id="62517-122">Описание</span><span class="sxs-lookup"><span data-stu-id="62517-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62517-123">\<> поведения > \<serviceBehaviors</span><span class="sxs-lookup"><span data-stu-id="62517-123">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="62517-124">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="62517-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62517-125">См. также</span><span class="sxs-lookup"><span data-stu-id="62517-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
