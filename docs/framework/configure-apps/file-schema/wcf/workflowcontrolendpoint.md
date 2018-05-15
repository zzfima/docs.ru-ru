---
title: '&lt;workflowControlEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 87c745cfb8f7cd98c25cd34fc1aa94a26a5ba507
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltworkflowcontrolendpointgt"></a><span data-ttu-id="2936b-102">&lt;workflowControlEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="2936b-102">&lt;workflowControlEndpoint&gt;</span></span>
<span data-ttu-id="2936b-103">Этот элемент конфигурации определяет стандартную конечную точку для управления выполнением экземпляров рабочего процесса (создание, выполнение, приостановка, завершение и т. д.).</span><span class="sxs-lookup"><span data-stu-id="2936b-103">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="2936b-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2936b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2936b-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="2936b-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2936b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2936b-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2936b-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2936b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="2936b-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2936b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2936b-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2936b-109">Attributes</span></span>  
  
|<span data-ttu-id="2936b-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2936b-110">Attribute</span></span>|<span data-ttu-id="2936b-111">Описание</span><span class="sxs-lookup"><span data-stu-id="2936b-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2936b-112">имя</span><span class="sxs-lookup"><span data-stu-id="2936b-112">name</span></span>|<span data-ttu-id="2936b-113">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="2936b-113">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="2936b-114">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="2936b-114">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2936b-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2936b-115">Child Elements</span></span>  
 <span data-ttu-id="2936b-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2936b-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2936b-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2936b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="2936b-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="2936b-118">Element</span></span>|<span data-ttu-id="2936b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="2936b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2936b-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="2936b-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="2936b-121">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="2936b-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2936b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="2936b-122">See Also</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
