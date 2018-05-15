---
title: '&lt;заголовки&gt;'
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 7683b07093719cda6b210a4174d47e5785d4644d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltheadersgt"></a><span data-ttu-id="f6fa4-102">&lt;заголовки&gt;</span><span class="sxs-lookup"><span data-stu-id="f6fa4-102">&lt;headers&gt;</span></span>
<span data-ttu-id="f6fa4-103">Помимо базового универсального кода ресурса (URI) к конечной точке можно обратиться по одному или нескольким заголовкам SOAP.</span><span class="sxs-lookup"><span data-stu-id="f6fa4-103">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="f6fa4-104">К сценариям, в которых это бывает удобно, относятся сценарии с посредниками протокола SOAP, в которых конечная точка требует, чтобы клиенты включали заголовки SOAP, нацеленные на посредники.</span><span class="sxs-lookup"><span data-stu-id="f6fa4-104">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="f6fa4-105">Данный элемент конфигурации можно использовать для определения подобных пользовательских заголовков адресов.</span><span class="sxs-lookup"><span data-stu-id="f6fa4-105">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="f6fa4-106">Записи в коллекции заголовков конечной точки являются пользовательскими элементами XML.</span><span class="sxs-lookup"><span data-stu-id="f6fa4-106">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="f6fa4-107">Каждый элемент должен представлять собой XML-код правильного формата.</span><span class="sxs-lookup"><span data-stu-id="f6fa4-107">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="f6fa4-108">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f6fa4-108">\<system.ServiceModel></span></span>  
<span data-ttu-id="f6fa4-109">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="f6fa4-109">\<client></span></span>  
<span data-ttu-id="f6fa4-110">\<Конечная точка ></span><span class="sxs-lookup"><span data-stu-id="f6fa4-110">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6fa4-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6fa4-111">Syntax</span></span>  
  
```xml  
<headers>  
    <Region xmlns="Uri">"String"</Region>  
        <Member xmlns="Uri">"String"</Member>  
</headers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6fa4-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f6fa4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f6fa4-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f6fa4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6fa4-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f6fa4-114">Attributes</span></span>  
 <span data-ttu-id="f6fa4-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f6fa4-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f6fa4-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f6fa4-116">Child Elements</span></span>  
  
|<span data-ttu-id="f6fa4-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="f6fa4-117">Element</span></span>|<span data-ttu-id="f6fa4-118">Описание</span><span class="sxs-lookup"><span data-stu-id="f6fa4-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f6fa4-119">Region</span><span class="sxs-lookup"><span data-stu-id="f6fa4-119">Region</span></span>||  
|<span data-ttu-id="f6fa4-120">Член</span><span class="sxs-lookup"><span data-stu-id="f6fa4-120">Member</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="f6fa4-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f6fa4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="f6fa4-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="f6fa4-122">Element</span></span>|<span data-ttu-id="f6fa4-123">Описание</span><span class="sxs-lookup"><span data-stu-id="f6fa4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6fa4-124">\<Конечная точка ></span><span class="sxs-lookup"><span data-stu-id="f6fa4-124">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="f6fa4-125">Настраивает разные типы конечных точек.</span><span class="sxs-lookup"><span data-stu-id="f6fa4-125">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6fa4-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="f6fa4-126">Remarks</span></span>  
 <span data-ttu-id="f6fa4-127">Необязательные заголовки содержат более подробную информацию для идентификации конечной точки и взаимодействия с ней.</span><span class="sxs-lookup"><span data-stu-id="f6fa4-127">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="f6fa4-128">Например, в заголовках может содержаться информация о том, как следует обрабатывать входящее сообщение, куда конечная точка должна отправить ответное сообщение или какой экземпляр службы необходимо использовать для обработки входящего сообщения от конкретного пользователя, если доступно несколько экземпляров.</span><span class="sxs-lookup"><span data-stu-id="f6fa4-128">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6fa4-129">См. также</span><span class="sxs-lookup"><span data-stu-id="f6fa4-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Headers%2A>  
 <xref:System.ServiceModel.Channels.AddressHeaderCollection>  
 [<span data-ttu-id="f6fa4-130">Конечные точки: адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="f6fa4-130">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
