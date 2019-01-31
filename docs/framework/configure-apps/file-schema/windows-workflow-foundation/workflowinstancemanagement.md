---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: baa1ccbe0accd2db701fac9ef53cdc6357713c5d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257425"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="7305c-101">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="7305c-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="7305c-102">Поведение службы, которое позволяет указать параметры, управляющие выполнением экземпляров рабочего процесса, включая сохраняемость, необработанное поведение исключения и неактивное поведение.</span><span class="sxs-lookup"><span data-stu-id="7305c-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="7305c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7305c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="7305c-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="7305c-104">\<behaviors></span></span>  
<span data-ttu-id="7305c-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="7305c-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="7305c-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="7305c-106">\<behavior></span></span>  
<span data-ttu-id="7305c-107">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="7305c-107">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7305c-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7305c-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7305c-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7305c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7305c-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7305c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7305c-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7305c-111">Attributes</span></span>  
  
|<span data-ttu-id="7305c-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7305c-112">Attribute</span></span>|<span data-ttu-id="7305c-113">Описание</span><span class="sxs-lookup"><span data-stu-id="7305c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7305c-114">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="7305c-114">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="7305c-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7305c-115">Child Elements</span></span>  
 <span data-ttu-id="7305c-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7305c-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7305c-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7305c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="7305c-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="7305c-118">Element</span></span>|<span data-ttu-id="7305c-119">Описание</span><span class="sxs-lookup"><span data-stu-id="7305c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7305c-120">\<поведение > из \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="7305c-120">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="7305c-121">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="7305c-121">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7305c-122">См. также</span><span class="sxs-lookup"><span data-stu-id="7305c-122">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
