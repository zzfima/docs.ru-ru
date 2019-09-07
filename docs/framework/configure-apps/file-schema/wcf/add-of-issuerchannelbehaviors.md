---
title: <add> из <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: cf7ac2691ad1c641352a8047373ced538b19e983
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398333"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="86b44-102">\<Добавление > \<> issuerChannelBehaviors</span><span class="sxs-lookup"><span data-stu-id="86b44-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="86b44-103">Добавляет поведение конечной точки, которое должно использоваться при взаимодействии со службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="86b44-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="86b44-104">Если какое- [ \<](clientcredentials.md) либо поведение конечной точки содержит элемент ClientCredentials >, будет создано исключение.</span><span class="sxs-lookup"><span data-stu-id="86b44-104">If any endpoint behavior contains a [\<clientCredentials>](clientcredentials.md) element, an exception will be thrown.</span></span>

<span data-ttu-id="86b44-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="86b44-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="86b44-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="86b44-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="86b44-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="86b44-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="86b44-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="86b44-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="86b44-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="86b44-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="86b44-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="86b44-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="86b44-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedToken >** ](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="86b44-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)</span></span>\
<span data-ttu-id="86b44-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuerChannelBehaviors >** ](issuerchannelbehaviors-element.md)</span><span class="sxs-lookup"><span data-stu-id="86b44-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerChannelBehaviors>**](issuerchannelbehaviors-element.md)</span></span>\
<span data-ttu-id="86b44-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="86b44-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="86b44-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86b44-114">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="86b44-115">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="86b44-115">Attributes and Elements</span></span>

<span data-ttu-id="86b44-116">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="86b44-116">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="86b44-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="86b44-117">Attributes</span></span>

|<span data-ttu-id="86b44-118">Атрибут</span><span class="sxs-lookup"><span data-stu-id="86b44-118">Attribute</span></span>|<span data-ttu-id="86b44-119">Описание</span><span class="sxs-lookup"><span data-stu-id="86b44-119">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="86b44-120">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="86b44-120">issuerAddress</span></span>|<span data-ttu-id="86b44-121">Универсальный код ресурса (URI) издателя маркера безопасности, с которым осуществляется взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="86b44-121">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="86b44-122">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="86b44-122">behaviorConfiguration</span></span>|<span data-ttu-id="86b44-123">Имя поведения конечной точки, определенное в том же файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="86b44-123">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="86b44-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="86b44-124">Child Elements</span></span>

<span data-ttu-id="86b44-125">Нет.</span><span class="sxs-lookup"><span data-stu-id="86b44-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="86b44-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="86b44-126">Parent Elements</span></span>

|<span data-ttu-id="86b44-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="86b44-127">Element</span></span>|<span data-ttu-id="86b44-128">Описание</span><span class="sxs-lookup"><span data-stu-id="86b44-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="86b44-129">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="86b44-129">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)|<span data-ttu-id="86b44-130">Содержит коллекцию поведений конечной точки клиента Windows Communication Foundation (WCF) для использования при взаимодействии с указанными службами маркеров службы.</span><span class="sxs-lookup"><span data-stu-id="86b44-130">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="86b44-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="86b44-131">Remarks</span></span>

<span data-ttu-id="86b44-132">`issuerAddress` содержит URI службы токенов безопасности, с которым клиент хочет обмениваться данными.</span><span class="sxs-lookup"><span data-stu-id="86b44-132">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="86b44-133">`behaviorConfiguration`Указывает на поведение конечной точки, используемое приложением в каналах, созданных Windows Communication Foundation (WCF) для получения выданных маркеров от служб маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="86b44-133">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="86b44-134">См. также</span><span class="sxs-lookup"><span data-stu-id="86b44-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="86b44-135">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="86b44-135">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="86b44-136">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="86b44-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="86b44-137">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="86b44-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="86b44-138">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="86b44-138">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="86b44-139">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="86b44-139">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="86b44-140">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="86b44-140">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="86b44-141">Практическое руководство. Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="86b44-141">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="86b44-142">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="86b44-142">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="86b44-143">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="86b44-143">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)
