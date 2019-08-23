---
title: <add> из <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 325d6b8111115384b18547bd11ccec8a4a8af711
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920113"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="baf54-102">\<Добавление > \<> issuerChannelBehaviors</span><span class="sxs-lookup"><span data-stu-id="baf54-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="baf54-103">Добавляет поведение конечной точки, которое должно использоваться при взаимодействии со службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="baf54-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="baf54-104">Если какое- [ \<](clientcredentials.md) либо поведение конечной точки содержит элемент ClientCredentials >, будет создано исключение.</span><span class="sxs-lookup"><span data-stu-id="baf54-104">If any endpoint behavior contains a [\<clientCredentials>](clientcredentials.md) element, an exception will be thrown.</span></span>

<span data-ttu-id="baf54-105">\<системой. ServiceModel > </span><span class="sxs-lookup"><span data-stu-id="baf54-105">\<system.ServiceModel></span></span>\
<span data-ttu-id="baf54-106">\<поведения > </span><span class="sxs-lookup"><span data-stu-id="baf54-106">\<behaviors></span></span>\
<span data-ttu-id="baf54-107">поведение раздела \<EndpointBehaviors > </span><span class="sxs-lookup"><span data-stu-id="baf54-107">endpointBehaviors section \<behavior></span></span>\
<span data-ttu-id="baf54-108">\<> clientCredentials </span><span class="sxs-lookup"><span data-stu-id="baf54-108">\<clientCredentials></span></span>\
<span data-ttu-id="baf54-109">\<issuedToken > </span><span class="sxs-lookup"><span data-stu-id="baf54-109">\<issuedToken></span></span>\
<span data-ttu-id="baf54-110">\<Элемент > issuerChannelBehaviors </span><span class="sxs-lookup"><span data-stu-id="baf54-110">\<issuerChannelBehaviors> Element</span></span>\
<span data-ttu-id="baf54-111">\<add></span><span class="sxs-lookup"><span data-stu-id="baf54-111">\<add></span></span>

## <a name="syntax"></a><span data-ttu-id="baf54-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="baf54-112">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="baf54-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="baf54-113">Attributes and Elements</span></span>

<span data-ttu-id="baf54-114">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="baf54-114">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="baf54-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="baf54-115">Attributes</span></span>

|<span data-ttu-id="baf54-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="baf54-116">Attribute</span></span>|<span data-ttu-id="baf54-117">Описание</span><span class="sxs-lookup"><span data-stu-id="baf54-117">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="baf54-118">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="baf54-118">issuerAddress</span></span>|<span data-ttu-id="baf54-119">Универсальный код ресурса (URI) издателя маркера безопасности, с которым осуществляется взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="baf54-119">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="baf54-120">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="baf54-120">behaviorConfiguration</span></span>|<span data-ttu-id="baf54-121">Имя поведения конечной точки, определенное в том же файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="baf54-121">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="baf54-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="baf54-122">Child Elements</span></span>

<span data-ttu-id="baf54-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="baf54-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="baf54-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="baf54-124">Parent Elements</span></span>

|<span data-ttu-id="baf54-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="baf54-125">Element</span></span>|<span data-ttu-id="baf54-126">Описание</span><span class="sxs-lookup"><span data-stu-id="baf54-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="baf54-127">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="baf54-127">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)|<span data-ttu-id="baf54-128">Содержит коллекцию поведений конечной точки клиента Windows Communication Foundation (WCF) для использования при взаимодействии с указанными службами маркеров службы.</span><span class="sxs-lookup"><span data-stu-id="baf54-128">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="baf54-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="baf54-129">Remarks</span></span>

<span data-ttu-id="baf54-130">`issuerAddress` содержит URI службы токенов безопасности, с которым клиент хочет обмениваться данными.</span><span class="sxs-lookup"><span data-stu-id="baf54-130">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="baf54-131">`behaviorConfiguration`Указывает на поведение конечной точки, используемое приложением в каналах, созданных Windows Communication Foundation (WCF) для получения выданных маркеров от служб маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="baf54-131">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="baf54-132">См. также</span><span class="sxs-lookup"><span data-stu-id="baf54-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="baf54-133">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="baf54-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="baf54-134">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="baf54-134">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="baf54-135">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="baf54-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="baf54-136">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="baf54-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="baf54-137">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="baf54-137">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="baf54-138">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="baf54-138">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="baf54-139">Практическое руководство. Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="baf54-139">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="baf54-140">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="baf54-140">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="baf54-141">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="baf54-141">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)
