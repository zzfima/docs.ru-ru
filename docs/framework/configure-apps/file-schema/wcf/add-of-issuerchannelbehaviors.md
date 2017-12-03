---
title: "&lt;add&gt; для &lt;issuerChannelBehaviors&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5ea76a96597796b10c97ea57ca38c3bda453468c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltissuerchannelbehaviorsgt"></a><span data-ttu-id="19ccc-102">&lt;add&gt; для &lt;issuerChannelBehaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="19ccc-102">&lt;add&gt; of &lt;issuerChannelBehaviors&gt;</span></span>
<span data-ttu-id="19ccc-103">Добавляет поведение конечной точки, которое должно использоваться при взаимодействии со службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="19ccc-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19ccc-104">Если поведение конечной точки содержит [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) элемент, будет создано исключение.</span><span class="sxs-lookup"><span data-stu-id="19ccc-104">If any endpoint behavior contains a [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element, an exception will be thrown.</span></span>  
  
 <span data-ttu-id="19ccc-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="19ccc-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="19ccc-106">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="19ccc-106">\<behaviors></span></span>  
<span data-ttu-id="19ccc-107">раздел endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="19ccc-107">endpointBehaviors section</span></span>  
<span data-ttu-id="19ccc-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="19ccc-108">\<behavior></span></span>  
<span data-ttu-id="19ccc-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="19ccc-109">\<clientCredentials></span></span>  
<span data-ttu-id="19ccc-110">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="19ccc-110">\<issuedToken></span></span>  
<span data-ttu-id="19ccc-111">\<issuerChannelBehaviors > элемент</span><span class="sxs-lookup"><span data-stu-id="19ccc-111">\<issuerChannelBehaviors> Element</span></span>  
<span data-ttu-id="19ccc-112">\<add></span><span class="sxs-lookup"><span data-stu-id="19ccc-112">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19ccc-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="19ccc-113">Syntax</span></span>  
  
```xml  
<add issuerAddress="string"  
     behaviorConfiguraton="string" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19ccc-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="19ccc-114">Attributes and Elements</span></span>  
 <span data-ttu-id="19ccc-115">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="19ccc-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19ccc-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="19ccc-116">Attributes</span></span>  
  
|<span data-ttu-id="19ccc-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="19ccc-117">Attribute</span></span>|<span data-ttu-id="19ccc-118">Описание</span><span class="sxs-lookup"><span data-stu-id="19ccc-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="19ccc-119">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="19ccc-119">issuerAddress</span></span>|<span data-ttu-id="19ccc-120">Универсальный код ресурса (URI) издателя маркера безопасности, с которым осуществляется взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="19ccc-120">The URI of the security token issuer to communicate with.</span></span>|  
|<span data-ttu-id="19ccc-121">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="19ccc-121">behaviorConfiguration</span></span>|<span data-ttu-id="19ccc-122">Имя поведения конечной точки, определенное в том же файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="19ccc-122">The name of an endpoint behavior defined in the same configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19ccc-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="19ccc-123">Child Elements</span></span>  
 <span data-ttu-id="19ccc-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="19ccc-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="19ccc-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="19ccc-125">Parent Elements</span></span>  
  
|<span data-ttu-id="19ccc-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="19ccc-126">Element</span></span>|<span data-ttu-id="19ccc-127">Описание</span><span class="sxs-lookup"><span data-stu-id="19ccc-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19ccc-128">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="19ccc-128">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="19ccc-129">Содержит коллекцию поведений конечной точки клиента [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], которые должны использоваться при взаимодействии с заданными службами маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="19ccc-129">Contains a collection of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19ccc-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="19ccc-130">Remarks</span></span>  
 <span data-ttu-id="19ccc-131">`issuerAddress` содержит URI службы токенов безопасности, с которым клиент хочет обмениваться данными.</span><span class="sxs-lookup"><span data-stu-id="19ccc-131">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="19ccc-132">`behaviorConfiguration` указывает на поведение конечной точки, которое приложение использует в каналах, созданных [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] для получения токенов, выданных локальной службой токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="19ccc-132">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] to get the issued tokens from the Security Token Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19ccc-133">См. также</span><span class="sxs-lookup"><span data-stu-id="19ccc-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [<span data-ttu-id="19ccc-134">Службы идентификации и проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="19ccc-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="19ccc-135">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="19ccc-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="19ccc-136">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="19ccc-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="19ccc-137">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="19ccc-137">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="19ccc-138">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="19ccc-138">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="19ccc-139">Как: создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="19ccc-139">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="19ccc-140">Как: Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="19ccc-140">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="19ccc-141">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="19ccc-141">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="19ccc-142">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="19ccc-142">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
