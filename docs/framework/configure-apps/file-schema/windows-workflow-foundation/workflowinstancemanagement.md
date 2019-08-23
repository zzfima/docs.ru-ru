---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: a22c72b7a683e3ecab4344c92e7d835a184a58d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947150"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="4d2be-101">\<Воркфловинстанцеманажемент ></span><span class="sxs-lookup"><span data-stu-id="4d2be-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="4d2be-102">Поведение службы, которое позволяет указать параметры, управляющие выполнением экземпляров рабочего процесса, включая сохраняемость, необработанное поведение исключения и неактивное поведение.</span><span class="sxs-lookup"><span data-stu-id="4d2be-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="4d2be-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4d2be-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="4d2be-104">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="4d2be-104">\<behaviors></span></span>  
<span data-ttu-id="4d2be-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4d2be-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="4d2be-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="4d2be-106">\<behavior></span></span>  
<span data-ttu-id="4d2be-107">\<Воркфловинстанцеманажемент ></span><span class="sxs-lookup"><span data-stu-id="4d2be-107">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d2be-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d2be-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d2be-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4d2be-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4d2be-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4d2be-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d2be-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4d2be-111">Attributes</span></span>  
  
|<span data-ttu-id="4d2be-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4d2be-112">Attribute</span></span>|<span data-ttu-id="4d2be-113">Описание</span><span class="sxs-lookup"><span data-stu-id="4d2be-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4d2be-114">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="4d2be-114">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="4d2be-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4d2be-115">Child Elements</span></span>  
 <span data-ttu-id="4d2be-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="4d2be-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d2be-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4d2be-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4d2be-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="4d2be-118">Element</span></span>|<span data-ttu-id="4d2be-119">Описание</span><span class="sxs-lookup"><span data-stu-id="4d2be-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d2be-120">\<> поведения > \<serviceBehaviors</span><span class="sxs-lookup"><span data-stu-id="4d2be-120">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="4d2be-121">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="4d2be-121">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d2be-122">См. также</span><span class="sxs-lookup"><span data-stu-id="4d2be-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
