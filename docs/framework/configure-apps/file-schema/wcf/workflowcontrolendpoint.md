---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 2c9774217b835acdb9ebf7374b964d838497fc9f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915333"
---
# <a name="workflowcontrolendpoint"></a><span data-ttu-id="0f28c-101">\<Воркфловконтролендпоинт ></span><span class="sxs-lookup"><span data-stu-id="0f28c-101">\<workflowControlEndpoint></span></span>
<span data-ttu-id="0f28c-102">Этот элемент конфигурации определяет стандартную конечную точку для управления выполнением экземпляров рабочего процесса (создание, выполнение, приостановка, завершение и т. д.).</span><span class="sxs-lookup"><span data-stu-id="0f28c-102">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="0f28c-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0f28c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="0f28c-104">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="0f28c-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f28c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f28c-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f28c-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0f28c-106">Attributes and Elements</span></span>  
 <span data-ttu-id="0f28c-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0f28c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f28c-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0f28c-108">Attributes</span></span>  
  
|<span data-ttu-id="0f28c-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0f28c-109">Attribute</span></span>|<span data-ttu-id="0f28c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="0f28c-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0f28c-111">имя</span><span class="sxs-lookup"><span data-stu-id="0f28c-111">name</span></span>|<span data-ttu-id="0f28c-112">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="0f28c-112">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="0f28c-113">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="0f28c-113">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0f28c-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0f28c-114">Child Elements</span></span>  
 <span data-ttu-id="0f28c-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="0f28c-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0f28c-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0f28c-116">Parent Elements</span></span>  
  
|<span data-ttu-id="0f28c-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="0f28c-117">Element</span></span>|<span data-ttu-id="0f28c-118">Описание</span><span class="sxs-lookup"><span data-stu-id="0f28c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f28c-119">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="0f28c-119">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="0f28c-120">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="0f28c-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0f28c-121">См. также</span><span class="sxs-lookup"><span data-stu-id="0f28c-121">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
