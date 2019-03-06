---
title: <add> из <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 5c9937cb6302a194228461f3e2e06ecdf4d43269
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377759"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="89895-102">\<Добавить > из \<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="89895-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="89895-103">Добавляет поведение конечной точки, которое должно использоваться при взаимодействии со службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="89895-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="89895-104">Если все поведения конечной точки содержит [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) элемент, будет создано исключение.</span><span class="sxs-lookup"><span data-stu-id="89895-104">If any endpoint behavior contains a [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element, an exception will be thrown.</span></span>

<span data-ttu-id="89895-105">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="89895-105">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="89895-106">\<варианты поведения > \\</span><span class="sxs-lookup"><span data-stu-id="89895-106">\<behaviors>\\</span></span>
<span data-ttu-id="89895-107">раздел endpointBehaviors \<поведение > \\</span><span class="sxs-lookup"><span data-stu-id="89895-107">endpointBehaviors section \<behavior>\\</span></span>
<span data-ttu-id="89895-108">\<clientCredentials > \\</span><span class="sxs-lookup"><span data-stu-id="89895-108">\<clientCredentials>\\</span></span>
<span data-ttu-id="89895-109">\<issuedToken > \\</span><span class="sxs-lookup"><span data-stu-id="89895-109">\<issuedToken>\\</span></span>
<span data-ttu-id="89895-110">\<issuerChannelBehaviors> Element\\</span><span class="sxs-lookup"><span data-stu-id="89895-110">\<issuerChannelBehaviors> Element\\</span></span>
<span data-ttu-id="89895-111">\<add></span><span class="sxs-lookup"><span data-stu-id="89895-111">\<add></span></span>

## <a name="syntax"></a><span data-ttu-id="89895-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89895-112">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="89895-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="89895-113">Attributes and Elements</span></span>

<span data-ttu-id="89895-114">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="89895-114">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="89895-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="89895-115">Attributes</span></span>

|<span data-ttu-id="89895-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="89895-116">Attribute</span></span>|<span data-ttu-id="89895-117">Описание</span><span class="sxs-lookup"><span data-stu-id="89895-117">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="89895-118">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="89895-118">issuerAddress</span></span>|<span data-ttu-id="89895-119">Универсальный код ресурса (URI) издателя маркера безопасности, с которым осуществляется взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="89895-119">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="89895-120">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="89895-120">behaviorConfiguration</span></span>|<span data-ttu-id="89895-121">Имя поведения конечной точки, определенное в том же файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="89895-121">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="89895-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="89895-122">Child Elements</span></span>

<span data-ttu-id="89895-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="89895-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="89895-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="89895-124">Parent Elements</span></span>

|<span data-ttu-id="89895-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="89895-125">Element</span></span>|<span data-ttu-id="89895-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="89895-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="89895-127">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="89895-127">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="89895-128">Содержит коллекцию поведений конечной точки клиента Windows Communication Foundation (WCF) для использования при взаимодействии с заданными службами маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="89895-128">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="89895-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="89895-129">Remarks</span></span>

<span data-ttu-id="89895-130">`issuerAddress` содержит URI службы токенов безопасности, с которым клиент хочет обмениваться данными.</span><span class="sxs-lookup"><span data-stu-id="89895-130">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="89895-131">`behaviorConfiguration` Указывает поведение конечной точки, приложение использует в каналах, созданных в Windows Communication Foundation (WCF) для получения маркеров, выданных из службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="89895-131">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="89895-132">См. также</span><span class="sxs-lookup"><span data-stu-id="89895-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="89895-133">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="89895-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="89895-134">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="89895-134">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="89895-135">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="89895-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="89895-136">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="89895-136">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="89895-137">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="89895-137">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="89895-138">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="89895-138">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="89895-139">Практическое руководство. Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="89895-139">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="89895-140">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="89895-140">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="89895-141">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="89895-141">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
