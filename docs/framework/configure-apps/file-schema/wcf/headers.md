---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 76b3cbf6b867a983c203141bcd901b2b7b4038d5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855180"
---
# <a name="headers"></a><span data-ttu-id="9734c-101">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="9734c-101">\<headers></span></span>
<span data-ttu-id="9734c-102">Помимо базового универсального кода ресурса (URI) к конечной точке можно обратиться по одному или нескольким заголовкам SOAP.</span><span class="sxs-lookup"><span data-stu-id="9734c-102">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="9734c-103">К сценариям, в которых это бывает удобно, относятся сценарии с посредниками протокола SOAP, в которых конечная точка требует, чтобы клиенты включали заголовки SOAP, нацеленные на посредники.</span><span class="sxs-lookup"><span data-stu-id="9734c-103">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="9734c-104">Данный элемент конфигурации можно использовать для определения подобных пользовательских заголовков адресов.</span><span class="sxs-lookup"><span data-stu-id="9734c-104">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="9734c-105">Записи в коллекции заголовков конечной точки являются пользовательскими элементами XML.</span><span class="sxs-lookup"><span data-stu-id="9734c-105">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="9734c-106">Каждый элемент должен представлять собой XML-код правильного формата.</span><span class="sxs-lookup"><span data-stu-id="9734c-106">Each element has to be well-formed XML.</span></span>  
  
<span data-ttu-id="9734c-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9734c-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9734c-108">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9734c-108">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9734c-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> клиента**](client.md)</span><span class="sxs-lookup"><span data-stu-id="9734c-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="9734c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> конечной точки**](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="9734c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="9734c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<заголовки >**</span><span class="sxs-lookup"><span data-stu-id="9734c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<headers>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9734c-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9734c-112">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9734c-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9734c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="9734c-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9734c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9734c-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9734c-115">Attributes</span></span>  
 <span data-ttu-id="9734c-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="9734c-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9734c-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9734c-117">Child Elements</span></span>  
 <span data-ttu-id="9734c-118">Определяемые пользователем XML-элементы.</span><span class="sxs-lookup"><span data-stu-id="9734c-118">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9734c-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9734c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9734c-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="9734c-120">Element</span></span>|<span data-ttu-id="9734c-121">Описание</span><span class="sxs-lookup"><span data-stu-id="9734c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9734c-122">\<> конечной точки</span><span class="sxs-lookup"><span data-stu-id="9734c-122">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="9734c-123">Настраивает разные типы конечных точек.</span><span class="sxs-lookup"><span data-stu-id="9734c-123">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9734c-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="9734c-124">Remarks</span></span>  
 <span data-ttu-id="9734c-125">Необязательные заголовки содержат более подробную информацию для идентификации конечной точки и взаимодействия с ней.</span><span class="sxs-lookup"><span data-stu-id="9734c-125">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="9734c-126">Например, в заголовках может содержаться информация о том, как следует обрабатывать входящее сообщение, куда конечная точка должна отправить ответное сообщение или какой экземпляр службы необходимо использовать для обработки входящего сообщения от конкретного пользователя, если доступно несколько экземпляров.</span><span class="sxs-lookup"><span data-stu-id="9734c-126">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9734c-127">См. также</span><span class="sxs-lookup"><span data-stu-id="9734c-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="9734c-128">Конеч Адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="9734c-128">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
