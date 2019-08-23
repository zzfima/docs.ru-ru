---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: a982fa87ab84725e36ee913f00200cd34f0b8f6f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925578"
---
# <a name="headers"></a><span data-ttu-id="67356-101">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="67356-101">\<headers></span></span>
<span data-ttu-id="67356-102">Помимо базового универсального кода ресурса (URI) к конечной точке можно обратиться по одному или нескольким заголовкам SOAP.</span><span class="sxs-lookup"><span data-stu-id="67356-102">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="67356-103">К сценариям, в которых это бывает удобно, относятся сценарии с посредниками протокола SOAP, в которых конечная точка требует, чтобы клиенты включали заголовки SOAP, нацеленные на посредники.</span><span class="sxs-lookup"><span data-stu-id="67356-103">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="67356-104">Данный элемент конфигурации можно использовать для определения подобных пользовательских заголовков адресов.</span><span class="sxs-lookup"><span data-stu-id="67356-104">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="67356-105">Записи в коллекции заголовков конечной точки являются пользовательскими элементами XML.</span><span class="sxs-lookup"><span data-stu-id="67356-105">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="67356-106">Каждый элемент должен представлять собой XML-код правильного формата.</span><span class="sxs-lookup"><span data-stu-id="67356-106">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="67356-107">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="67356-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="67356-108">\<> клиента</span><span class="sxs-lookup"><span data-stu-id="67356-108">\<client></span></span>  
<span data-ttu-id="67356-109">\<> конечной точки</span><span class="sxs-lookup"><span data-stu-id="67356-109">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67356-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67356-110">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67356-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="67356-111">Attributes and Elements</span></span>  
 <span data-ttu-id="67356-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="67356-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67356-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="67356-113">Attributes</span></span>  
 <span data-ttu-id="67356-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="67356-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="67356-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="67356-115">Child Elements</span></span>  
 <span data-ttu-id="67356-116">Определяемые пользователем XML-элементы.</span><span class="sxs-lookup"><span data-stu-id="67356-116">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="67356-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="67356-117">Parent Elements</span></span>  
  
|<span data-ttu-id="67356-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="67356-118">Element</span></span>|<span data-ttu-id="67356-119">Описание</span><span class="sxs-lookup"><span data-stu-id="67356-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67356-120">\<> конечной точки</span><span class="sxs-lookup"><span data-stu-id="67356-120">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="67356-121">Настраивает разные типы конечных точек.</span><span class="sxs-lookup"><span data-stu-id="67356-121">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67356-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="67356-122">Remarks</span></span>  
 <span data-ttu-id="67356-123">Необязательные заголовки содержат более подробную информацию для идентификации конечной точки и взаимодействия с ней.</span><span class="sxs-lookup"><span data-stu-id="67356-123">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="67356-124">Например, в заголовках может содержаться информация о том, как следует обрабатывать входящее сообщение, куда конечная точка должна отправить ответное сообщение или какой экземпляр службы необходимо использовать для обработки входящего сообщения от конкретного пользователя, если доступно несколько экземпляров.</span><span class="sxs-lookup"><span data-stu-id="67356-124">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67356-125">См. также</span><span class="sxs-lookup"><span data-stu-id="67356-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="67356-126">Конеч Адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="67356-126">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
