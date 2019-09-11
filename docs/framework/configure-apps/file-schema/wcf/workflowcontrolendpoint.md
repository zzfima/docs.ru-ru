---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 670c1573fe4378a18c19d0a58fe58241745725bd
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854780"
---
# <a name="workflowcontrolendpoint"></a><span data-ttu-id="2d546-101">\<Воркфловконтролендпоинт ></span><span class="sxs-lookup"><span data-stu-id="2d546-101">\<workflowControlEndpoint></span></span>
<span data-ttu-id="2d546-102">Этот элемент конфигурации определяет стандартную конечную точку для управления выполнением экземпляров рабочего процесса (создание, выполнение, приостановка, завершение и т. д.).</span><span class="sxs-lookup"><span data-stu-id="2d546-102">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="2d546-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2d546-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2d546-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2d546-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2d546-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Стандардендпоинтс >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="2d546-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="2d546-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Воркфловконтролендпоинт >**</span><span class="sxs-lookup"><span data-stu-id="2d546-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowControlEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d546-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2d546-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d546-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2d546-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2d546-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2d546-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d546-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2d546-110">Attributes</span></span>  
  
|<span data-ttu-id="2d546-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2d546-111">Attribute</span></span>|<span data-ttu-id="2d546-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2d546-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2d546-113">имя</span><span class="sxs-lookup"><span data-stu-id="2d546-113">name</span></span>|<span data-ttu-id="2d546-114">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="2d546-114">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="2d546-115">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="2d546-115">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d546-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2d546-116">Child Elements</span></span>  
 <span data-ttu-id="2d546-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="2d546-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2d546-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2d546-118">Parent Elements</span></span>  
  
|<span data-ttu-id="2d546-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="2d546-119">Element</span></span>|<span data-ttu-id="2d546-120">Описание</span><span class="sxs-lookup"><span data-stu-id="2d546-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d546-121">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="2d546-121">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="2d546-122">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="2d546-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2d546-123">См. также</span><span class="sxs-lookup"><span data-stu-id="2d546-123">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
