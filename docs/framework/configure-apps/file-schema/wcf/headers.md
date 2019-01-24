---
title: '&lt;Заголовки&gt;'
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: f47462ba63b9bd8868420ee9d3a320ba18c83c65
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557829"
---
# <a name="ltheadersgt"></a><span data-ttu-id="8cab7-102">&lt;Заголовки&gt;</span><span class="sxs-lookup"><span data-stu-id="8cab7-102">&lt;headers&gt;</span></span>
<span data-ttu-id="8cab7-103">Помимо базового универсального кода ресурса (URI) к конечной точке можно обратиться по одному или нескольким заголовкам SOAP.</span><span class="sxs-lookup"><span data-stu-id="8cab7-103">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="8cab7-104">К сценариям, в которых это бывает удобно, относятся сценарии с посредниками протокола SOAP, в которых конечная точка требует, чтобы клиенты включали заголовки SOAP, нацеленные на посредники.</span><span class="sxs-lookup"><span data-stu-id="8cab7-104">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="8cab7-105">Данный элемент конфигурации можно использовать для определения подобных пользовательских заголовков адресов.</span><span class="sxs-lookup"><span data-stu-id="8cab7-105">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="8cab7-106">Записи в коллекции заголовков конечной точки являются пользовательскими элементами XML.</span><span class="sxs-lookup"><span data-stu-id="8cab7-106">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="8cab7-107">Каждый элемент должен представлять собой XML-код правильного формата.</span><span class="sxs-lookup"><span data-stu-id="8cab7-107">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="8cab7-108">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8cab7-108">\<system.ServiceModel></span></span>  
<span data-ttu-id="8cab7-109">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="8cab7-109">\<client></span></span>  
<span data-ttu-id="8cab7-110">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="8cab7-110">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cab7-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8cab7-111">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8cab7-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8cab7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8cab7-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8cab7-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8cab7-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8cab7-114">Attributes</span></span>  
 <span data-ttu-id="8cab7-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8cab7-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8cab7-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8cab7-116">Child Elements</span></span>  
 <span data-ttu-id="8cab7-117">Пользовательские XML-элементы.</span><span class="sxs-lookup"><span data-stu-id="8cab7-117">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8cab7-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8cab7-118">Parent Elements</span></span>  
  
|<span data-ttu-id="8cab7-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="8cab7-119">Element</span></span>|<span data-ttu-id="8cab7-120">Описание</span><span class="sxs-lookup"><span data-stu-id="8cab7-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8cab7-121">\<Конечная точка ></span><span class="sxs-lookup"><span data-stu-id="8cab7-121">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="8cab7-122">Настраивает разные типы конечных точек.</span><span class="sxs-lookup"><span data-stu-id="8cab7-122">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8cab7-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="8cab7-123">Remarks</span></span>  
 <span data-ttu-id="8cab7-124">Необязательные заголовки содержат более подробную информацию для идентификации конечной точки и взаимодействия с ней.</span><span class="sxs-lookup"><span data-stu-id="8cab7-124">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="8cab7-125">Например, в заголовках может содержаться информация о том, как следует обрабатывать входящее сообщение, куда конечная точка должна отправить ответное сообщение или какой экземпляр службы необходимо использовать для обработки входящего сообщения от конкретного пользователя, если доступно несколько экземпляров.</span><span class="sxs-lookup"><span data-stu-id="8cab7-125">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cab7-126">См. также</span><span class="sxs-lookup"><span data-stu-id="8cab7-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="8cab7-127">Конечные точки: Адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="8cab7-127">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
