---
title: <add> из <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 65c76cba696ae388d6184eaaa70a1f2f5a301e1c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271802"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="89b9e-102">\<Добавить > из \<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="89b9e-102">\<add> of \<issuerChannelBehaviors></span></span>
<span data-ttu-id="89b9e-103">Добавляет поведение конечной точки, которое должно использоваться при взаимодействии со службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="89b9e-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89b9e-104">Если все поведения конечной точки содержит [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) элемент, будет создано исключение.</span><span class="sxs-lookup"><span data-stu-id="89b9e-104">If any endpoint behavior contains a [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element, an exception will be thrown.</span></span>  
  
 <span data-ttu-id="89b9e-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="89b9e-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="89b9e-106">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="89b9e-106">\<behaviors></span></span>  
<span data-ttu-id="89b9e-107">раздел endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="89b9e-107">endpointBehaviors section</span></span>  
<span data-ttu-id="89b9e-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="89b9e-108">\<behavior></span></span>  
<span data-ttu-id="89b9e-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="89b9e-109">\<clientCredentials></span></span>  
<span data-ttu-id="89b9e-110">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="89b9e-110">\<issuedToken></span></span>  
<span data-ttu-id="89b9e-111">\<issuerChannelBehaviors > элемент</span><span class="sxs-lookup"><span data-stu-id="89b9e-111">\<issuerChannelBehaviors> Element</span></span>  
<span data-ttu-id="89b9e-112">\<add></span><span class="sxs-lookup"><span data-stu-id="89b9e-112">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89b9e-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89b9e-113">Syntax</span></span>  
  
```xml  
<add issuerAddress="string"
     behaviorConfiguraton="string" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89b9e-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="89b9e-114">Attributes and Elements</span></span>  
 <span data-ttu-id="89b9e-115">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="89b9e-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89b9e-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="89b9e-116">Attributes</span></span>  
  
|<span data-ttu-id="89b9e-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="89b9e-117">Attribute</span></span>|<span data-ttu-id="89b9e-118">Описание</span><span class="sxs-lookup"><span data-stu-id="89b9e-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="89b9e-119">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="89b9e-119">issuerAddress</span></span>|<span data-ttu-id="89b9e-120">Универсальный код ресурса (URI) издателя маркера безопасности, с которым осуществляется взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="89b9e-120">The URI of the security token issuer to communicate with.</span></span>|  
|<span data-ttu-id="89b9e-121">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="89b9e-121">behaviorConfiguration</span></span>|<span data-ttu-id="89b9e-122">Имя поведения конечной точки, определенное в том же файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="89b9e-122">The name of an endpoint behavior defined in the same configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89b9e-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="89b9e-123">Child Elements</span></span>  
 <span data-ttu-id="89b9e-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="89b9e-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="89b9e-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="89b9e-125">Parent Elements</span></span>  
  
|<span data-ttu-id="89b9e-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="89b9e-126">Element</span></span>|<span data-ttu-id="89b9e-127">Описание:</span><span class="sxs-lookup"><span data-stu-id="89b9e-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89b9e-128">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="89b9e-128">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="89b9e-129">Содержит коллекцию поведений конечной точки клиента Windows Communication Foundation (WCF) для использования при взаимодействии с заданными службами маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="89b9e-129">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89b9e-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="89b9e-130">Remarks</span></span>  
 <span data-ttu-id="89b9e-131">`issuerAddress` содержит URI службы токенов безопасности, с которым клиент хочет обмениваться данными.</span><span class="sxs-lookup"><span data-stu-id="89b9e-131">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="89b9e-132">`behaviorConfiguration` Указывает поведение конечной точки, приложение использует в каналах, созданных в Windows Communication Foundation (WCF) для получения маркеров, выданных из службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="89b9e-132">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89b9e-133">См. также</span><span class="sxs-lookup"><span data-stu-id="89b9e-133">See also</span></span>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="89b9e-134">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="89b9e-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="89b9e-135">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="89b9e-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="89b9e-136">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="89b9e-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="89b9e-137">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="89b9e-137">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="89b9e-138">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="89b9e-138">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="89b9e-139">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="89b9e-139">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="89b9e-140">Практическое руководство. Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="89b9e-140">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="89b9e-141">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="89b9e-141">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="89b9e-142">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="89b9e-142">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
