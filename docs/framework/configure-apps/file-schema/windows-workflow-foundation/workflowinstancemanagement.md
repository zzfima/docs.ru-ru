---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: aa2edafd9adc0317ed0023ad46688025dcecad67
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397519"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="ccdc4-101">\<Воркфловинстанцеманажемент ></span><span class="sxs-lookup"><span data-stu-id="ccdc4-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="ccdc4-102">Поведение службы, которое позволяет указать параметры, управляющие выполнением экземпляров рабочего процесса, включая сохраняемость, необработанное поведение исключения и неактивное поведение.</span><span class="sxs-lookup"><span data-stu-id="ccdc4-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="ccdc4-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ccdc4-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ccdc4-104">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ccdc4-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="ccdc4-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ccdc4-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="ccdc4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ccdc4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="ccdc4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ccdc4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="ccdc4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Воркфловинстанцеманажемент >**</span><span class="sxs-lookup"><span data-stu-id="ccdc4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceManagement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccdc4-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ccdc4-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ccdc4-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ccdc4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ccdc4-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ccdc4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ccdc4-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ccdc4-112">Attributes</span></span>  
  
|<span data-ttu-id="ccdc4-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ccdc4-113">Attribute</span></span>|<span data-ttu-id="ccdc4-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ccdc4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ccdc4-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="ccdc4-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="ccdc4-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ccdc4-116">Child Elements</span></span>  
 <span data-ttu-id="ccdc4-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="ccdc4-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ccdc4-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ccdc4-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ccdc4-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="ccdc4-119">Element</span></span>|<span data-ttu-id="ccdc4-120">Описание</span><span class="sxs-lookup"><span data-stu-id="ccdc4-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ccdc4-121">\<> поведения > \<serviceBehaviors</span><span class="sxs-lookup"><span data-stu-id="ccdc4-121">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="ccdc4-122">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="ccdc4-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ccdc4-123">См. также</span><span class="sxs-lookup"><span data-stu-id="ccdc4-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
