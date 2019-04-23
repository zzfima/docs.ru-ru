---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 660497012dd057e4ecf95524833e2573fe03a8b0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224566"
---
# <a name="headers"></a><span data-ttu-id="e7e42-101">\<headers></span><span class="sxs-lookup"><span data-stu-id="e7e42-101">\<headers></span></span>
<span data-ttu-id="e7e42-102">Помимо базового универсального кода ресурса (URI) к конечной точке можно обратиться по одному или нескольким заголовкам SOAP.</span><span class="sxs-lookup"><span data-stu-id="e7e42-102">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="e7e42-103">К сценариям, в которых это бывает удобно, относятся сценарии с посредниками протокола SOAP, в которых конечная точка требует, чтобы клиенты включали заголовки SOAP, нацеленные на посредники.</span><span class="sxs-lookup"><span data-stu-id="e7e42-103">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="e7e42-104">Данный элемент конфигурации можно использовать для определения подобных пользовательских заголовков адресов.</span><span class="sxs-lookup"><span data-stu-id="e7e42-104">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="e7e42-105">Записи в коллекции заголовков конечной точки являются пользовательскими элементами XML.</span><span class="sxs-lookup"><span data-stu-id="e7e42-105">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="e7e42-106">Каждый элемент должен представлять собой XML-код правильного формата.</span><span class="sxs-lookup"><span data-stu-id="e7e42-106">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="e7e42-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e7e42-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="e7e42-108">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="e7e42-108">\<client></span></span>  
<span data-ttu-id="e7e42-109">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="e7e42-109">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7e42-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7e42-110">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7e42-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e7e42-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e7e42-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e7e42-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7e42-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e7e42-113">Attributes</span></span>  
 <span data-ttu-id="e7e42-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e7e42-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e7e42-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e7e42-115">Child Elements</span></span>  
 <span data-ttu-id="e7e42-116">Пользовательские XML-элементы.</span><span class="sxs-lookup"><span data-stu-id="e7e42-116">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7e42-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e7e42-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e7e42-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="e7e42-118">Element</span></span>|<span data-ttu-id="e7e42-119">Описание</span><span class="sxs-lookup"><span data-stu-id="e7e42-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7e42-120">\<Конечная точка ></span><span class="sxs-lookup"><span data-stu-id="e7e42-120">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="e7e42-121">Настраивает разные типы конечных точек.</span><span class="sxs-lookup"><span data-stu-id="e7e42-121">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7e42-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="e7e42-122">Remarks</span></span>  
 <span data-ttu-id="e7e42-123">Необязательные заголовки содержат более подробную информацию для идентификации конечной точки и взаимодействия с ней.</span><span class="sxs-lookup"><span data-stu-id="e7e42-123">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="e7e42-124">Например, в заголовках может содержаться информация о том, как следует обрабатывать входящее сообщение, куда конечная точка должна отправить ответное сообщение или какой экземпляр службы необходимо использовать для обработки входящего сообщения от конкретного пользователя, если доступно несколько экземпляров.</span><span class="sxs-lookup"><span data-stu-id="e7e42-124">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7e42-125">См. также</span><span class="sxs-lookup"><span data-stu-id="e7e42-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="e7e42-126">Конечные точки: Адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="e7e42-126">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
