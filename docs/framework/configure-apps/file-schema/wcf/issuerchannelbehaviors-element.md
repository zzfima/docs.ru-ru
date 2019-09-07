---
title: Элемент <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: 2c0e0d8d041565edd25c4b2c2802bfd2a589b4f7
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397900"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="0f9c8-102">\<Элемент > issuerChannelBehaviors</span><span class="sxs-lookup"><span data-stu-id="0f9c8-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="0f9c8-103">Содержит коллекцию поведений конечной точки клиента Windows Communication Foundation (WCF) (определенную в конфигурации) для использования при взаимодействии с указанными службами маркеров службы.</span><span class="sxs-lookup"><span data-stu-id="0f9c8-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="0f9c8-104">Определенные поведения не могут включать в себя [ \<> элементы ClientCredentials](clientcredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="0f9c8-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

<span data-ttu-id="0f9c8-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0f9c8-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0f9c8-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0f9c8-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0f9c8-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0f9c8-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="0f9c8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0f9c8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="0f9c8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0f9c8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="0f9c8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="0f9c8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="0f9c8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedToken >** ](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="0f9c8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)</span></span>\
<span data-ttu-id="0f9c8-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerChannelBehaviors >**</span><span class="sxs-lookup"><span data-stu-id="0f9c8-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerChannelBehaviors>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="0f9c8-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f9c8-113">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0f9c8-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0f9c8-114">Attributes and Elements</span></span>

<span data-ttu-id="0f9c8-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0f9c8-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0f9c8-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0f9c8-116">Attributes</span></span>

<span data-ttu-id="0f9c8-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="0f9c8-117">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0f9c8-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0f9c8-118">Child Elements</span></span>

|<span data-ttu-id="0f9c8-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="0f9c8-119">Element</span></span>|<span data-ttu-id="0f9c8-120">Описание</span><span class="sxs-lookup"><span data-stu-id="0f9c8-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0f9c8-121">\<add></span><span class="sxs-lookup"><span data-stu-id="0f9c8-121">\<add></span></span>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="0f9c8-122">Добавляет поведение в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="0f9c8-122">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0f9c8-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0f9c8-123">Parent Elements</span></span>

|<span data-ttu-id="0f9c8-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="0f9c8-124">Element</span></span>|<span data-ttu-id="0f9c8-125">Описание</span><span class="sxs-lookup"><span data-stu-id="0f9c8-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0f9c8-126">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="0f9c8-126">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="0f9c8-127">Задает пользовательский маркер, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="0f9c8-127">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0f9c8-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="0f9c8-128">Remarks</span></span>

<span data-ttu-id="0f9c8-129">Этот элемент используется, когда для связи со службой необходимо любое поведение (кроме поведений, в которые включаются элементы `<clientCredentials>`).</span><span class="sxs-lookup"><span data-stu-id="0f9c8-129">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="0f9c8-130">Например, если [ \<](datacontractserializer-element.md) необходимо добавить элемент поведения dataContractSerializer >.</span><span class="sxs-lookup"><span data-stu-id="0f9c8-130">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f9c8-131">См. также</span><span class="sxs-lookup"><span data-stu-id="0f9c8-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="0f9c8-132">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="0f9c8-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="0f9c8-133">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="0f9c8-133">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="0f9c8-134">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="0f9c8-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="0f9c8-135">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="0f9c8-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0f9c8-136">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="0f9c8-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="0f9c8-137">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="0f9c8-137">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="0f9c8-138">Практическое руководство. Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="0f9c8-138">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="0f9c8-139">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="0f9c8-139">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
