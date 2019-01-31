---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 3c3c3a3d747a1338e2db3afa92c735af4a588642
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55288032"
---
# <a name="headers"></a><span data-ttu-id="1e01f-101">\<headers></span><span class="sxs-lookup"><span data-stu-id="1e01f-101">\<headers></span></span>
<span data-ttu-id="1e01f-102">Помимо базового универсального кода ресурса (URI) к конечной точке можно обратиться по одному или нескольким заголовкам SOAP.</span><span class="sxs-lookup"><span data-stu-id="1e01f-102">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="1e01f-103">К сценариям, в которых это бывает удобно, относятся сценарии с посредниками протокола SOAP, в которых конечная точка требует, чтобы клиенты включали заголовки SOAP, нацеленные на посредники.</span><span class="sxs-lookup"><span data-stu-id="1e01f-103">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="1e01f-104">Данный элемент конфигурации можно использовать для определения подобных пользовательских заголовков адресов.</span><span class="sxs-lookup"><span data-stu-id="1e01f-104">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="1e01f-105">Записи в коллекции заголовков конечной точки являются пользовательскими элементами XML.</span><span class="sxs-lookup"><span data-stu-id="1e01f-105">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="1e01f-106">Каждый элемент должен представлять собой XML-код правильного формата.</span><span class="sxs-lookup"><span data-stu-id="1e01f-106">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="1e01f-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1e01f-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="1e01f-108">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="1e01f-108">\<client></span></span>  
<span data-ttu-id="1e01f-109">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="1e01f-109">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e01f-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e01f-110">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e01f-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1e01f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1e01f-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1e01f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e01f-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1e01f-113">Attributes</span></span>  
 <span data-ttu-id="1e01f-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1e01f-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1e01f-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1e01f-115">Child Elements</span></span>  
 <span data-ttu-id="1e01f-116">Пользовательские XML-элементы.</span><span class="sxs-lookup"><span data-stu-id="1e01f-116">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1e01f-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1e01f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="1e01f-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="1e01f-118">Element</span></span>|<span data-ttu-id="1e01f-119">Описание</span><span class="sxs-lookup"><span data-stu-id="1e01f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e01f-120">\<Конечная точка ></span><span class="sxs-lookup"><span data-stu-id="1e01f-120">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="1e01f-121">Настраивает разные типы конечных точек.</span><span class="sxs-lookup"><span data-stu-id="1e01f-121">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e01f-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="1e01f-122">Remarks</span></span>  
 <span data-ttu-id="1e01f-123">Необязательные заголовки содержат более подробную информацию для идентификации конечной точки и взаимодействия с ней.</span><span class="sxs-lookup"><span data-stu-id="1e01f-123">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="1e01f-124">Например, в заголовках может содержаться информация о том, как следует обрабатывать входящее сообщение, куда конечная точка должна отправить ответное сообщение или какой экземпляр службы необходимо использовать для обработки входящего сообщения от конкретного пользователя, если доступно несколько экземпляров.</span><span class="sxs-lookup"><span data-stu-id="1e01f-124">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e01f-125">См. также</span><span class="sxs-lookup"><span data-stu-id="1e01f-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="1e01f-126">Конечные точки: Адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="1e01f-126">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
