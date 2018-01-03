---
title: "&lt;заголовки&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f7fdd869553a672045c94a256b00638c9d0c4c24
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltheadersgt"></a><span data-ttu-id="bd5a1-102">&lt;заголовки&gt;</span><span class="sxs-lookup"><span data-stu-id="bd5a1-102">&lt;headers&gt;</span></span>
<span data-ttu-id="bd5a1-103">Помимо базового универсального кода ресурса (URI) к конечной точке можно обратиться по одному или нескольким заголовкам SOAP.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-103">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="bd5a1-104">К сценариям, в которых это бывает удобно, относятся сценарии с посредниками протокола SOAP, в которых конечная точка требует, чтобы клиенты включали заголовки SOAP, нацеленные на посредники.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-104">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="bd5a1-105">Данный элемент конфигурации можно использовать для определения подобных пользовательских заголовков адресов.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-105">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="bd5a1-106">Записи в коллекции заголовков конечной точки являются пользовательскими элементами XML.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-106">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="bd5a1-107">Каждый элемент должен представлять собой XML-код правильного формата.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-107">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="bd5a1-108">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bd5a1-108">\<system.ServiceModel></span></span>  
<span data-ttu-id="bd5a1-109">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="bd5a1-109">\<client></span></span>  
<span data-ttu-id="bd5a1-110">\<Конечная точка ></span><span class="sxs-lookup"><span data-stu-id="bd5a1-110">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd5a1-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd5a1-111">Syntax</span></span>  
  
```xml  
<headers>  
    <Region xmlns="Uri">"String"</Region>  
        <Member xmlns="Uri">"String"</Member>  
</headers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd5a1-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bd5a1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="bd5a1-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd5a1-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bd5a1-114">Attributes</span></span>  
 <span data-ttu-id="bd5a1-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bd5a1-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bd5a1-116">Child Elements</span></span>  
  
|<span data-ttu-id="bd5a1-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="bd5a1-117">Element</span></span>|<span data-ttu-id="bd5a1-118">Описание</span><span class="sxs-lookup"><span data-stu-id="bd5a1-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bd5a1-119">Region</span><span class="sxs-lookup"><span data-stu-id="bd5a1-119">Region</span></span>||  
|<span data-ttu-id="bd5a1-120">Член</span><span class="sxs-lookup"><span data-stu-id="bd5a1-120">Member</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="bd5a1-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bd5a1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="bd5a1-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="bd5a1-122">Element</span></span>|<span data-ttu-id="bd5a1-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="bd5a1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd5a1-124">\<Конечная точка ></span><span class="sxs-lookup"><span data-stu-id="bd5a1-124">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="bd5a1-125">Настраивает разные типы конечных точек.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-125">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd5a1-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="bd5a1-126">Remarks</span></span>  
 <span data-ttu-id="bd5a1-127">Необязательные заголовки содержат более подробную информацию для идентификации конечной точки и взаимодействия с ней.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-127">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="bd5a1-128">Например, в заголовках может содержаться информация о том, как следует обрабатывать входящее сообщение, куда конечная точка должна отправить ответное сообщение или какой экземпляр службы необходимо использовать для обработки входящего сообщения от конкретного пользователя, если доступно несколько экземпляров.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-128">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd5a1-129">См. также</span><span class="sxs-lookup"><span data-stu-id="bd5a1-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Headers%2A>  
 <xref:System.ServiceModel.Channels.AddressHeaderCollection>  
 [<span data-ttu-id="bd5a1-130">Конечные точки: адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="bd5a1-130">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
