---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: de0a51ed6f2a878ab3a6ebe15863f1f2925034ce
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272604"
---
# <a name="workflowcontrolendpoint"></a><span data-ttu-id="3f2ea-101">\<workflowControlEndpoint ></span><span class="sxs-lookup"><span data-stu-id="3f2ea-101">\<workflowControlEndpoint></span></span>
<span data-ttu-id="3f2ea-102">Этот элемент конфигурации определяет стандартную конечную точку для управления выполнением экземпляров рабочего процесса (создание, выполнение, приостановка, завершение и т. д.).</span><span class="sxs-lookup"><span data-stu-id="3f2ea-102">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="3f2ea-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3f2ea-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="3f2ea-104">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="3f2ea-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f2ea-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f2ea-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f2ea-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3f2ea-106">Attributes and Elements</span></span>  
 <span data-ttu-id="3f2ea-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3f2ea-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f2ea-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3f2ea-108">Attributes</span></span>  
  
|<span data-ttu-id="3f2ea-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3f2ea-109">Attribute</span></span>|<span data-ttu-id="3f2ea-110">Описание</span><span class="sxs-lookup"><span data-stu-id="3f2ea-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3f2ea-111">имя</span><span class="sxs-lookup"><span data-stu-id="3f2ea-111">name</span></span>|<span data-ttu-id="3f2ea-112">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3f2ea-112">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="3f2ea-113">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="3f2ea-113">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3f2ea-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3f2ea-114">Child Elements</span></span>  
 <span data-ttu-id="3f2ea-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3f2ea-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f2ea-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3f2ea-116">Parent Elements</span></span>  
  
|<span data-ttu-id="3f2ea-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="3f2ea-117">Element</span></span>|<span data-ttu-id="3f2ea-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="3f2ea-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3f2ea-119">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="3f2ea-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="3f2ea-120">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="3f2ea-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3f2ea-121">См. также</span><span class="sxs-lookup"><span data-stu-id="3f2ea-121">See also</span></span>
- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
