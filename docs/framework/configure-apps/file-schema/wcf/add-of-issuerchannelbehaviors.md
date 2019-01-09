---
title: '&lt;add&gt; для &lt;issuerChannelBehaviors&gt;'
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 072e3f4e961f6bf45e7c8b48c64cda36d385cf2b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149544"
---
# <a name="ltaddgt-of-ltissuerchannelbehaviorsgt"></a><span data-ttu-id="23b9b-102">&lt;add&gt; для &lt;issuerChannelBehaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="23b9b-102">&lt;add&gt; of &lt;issuerChannelBehaviors&gt;</span></span>
<span data-ttu-id="23b9b-103">Добавляет поведение конечной точки, которое должно использоваться при взаимодействии со службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="23b9b-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23b9b-104">Если все поведения конечной точки содержит [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) элемент, будет создано исключение.</span><span class="sxs-lookup"><span data-stu-id="23b9b-104">If any endpoint behavior contains a [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element, an exception will be thrown.</span></span>  
  
 <span data-ttu-id="23b9b-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="23b9b-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="23b9b-106">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="23b9b-106">\<behaviors></span></span>  
<span data-ttu-id="23b9b-107">раздел endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="23b9b-107">endpointBehaviors section</span></span>  
<span data-ttu-id="23b9b-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="23b9b-108">\<behavior></span></span>  
<span data-ttu-id="23b9b-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="23b9b-109">\<clientCredentials></span></span>  
<span data-ttu-id="23b9b-110">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="23b9b-110">\<issuedToken></span></span>  
<span data-ttu-id="23b9b-111">\<issuerChannelBehaviors > элемент</span><span class="sxs-lookup"><span data-stu-id="23b9b-111">\<issuerChannelBehaviors> Element</span></span>  
<span data-ttu-id="23b9b-112">\<add></span><span class="sxs-lookup"><span data-stu-id="23b9b-112">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23b9b-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="23b9b-113">Syntax</span></span>  
  
```xml  
<add issuerAddress="string"
     behaviorConfiguraton="string" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23b9b-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="23b9b-114">Attributes and Elements</span></span>  
 <span data-ttu-id="23b9b-115">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="23b9b-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23b9b-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="23b9b-116">Attributes</span></span>  
  
|<span data-ttu-id="23b9b-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="23b9b-117">Attribute</span></span>|<span data-ttu-id="23b9b-118">Описание</span><span class="sxs-lookup"><span data-stu-id="23b9b-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="23b9b-119">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="23b9b-119">issuerAddress</span></span>|<span data-ttu-id="23b9b-120">Универсальный код ресурса (URI) издателя маркера безопасности, с которым осуществляется взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="23b9b-120">The URI of the security token issuer to communicate with.</span></span>|  
|<span data-ttu-id="23b9b-121">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="23b9b-121">behaviorConfiguration</span></span>|<span data-ttu-id="23b9b-122">Имя поведения конечной точки, определенное в том же файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="23b9b-122">The name of an endpoint behavior defined in the same configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="23b9b-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="23b9b-123">Child Elements</span></span>  
 <span data-ttu-id="23b9b-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="23b9b-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="23b9b-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="23b9b-125">Parent Elements</span></span>  
  
|<span data-ttu-id="23b9b-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="23b9b-126">Element</span></span>|<span data-ttu-id="23b9b-127">Описание:</span><span class="sxs-lookup"><span data-stu-id="23b9b-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="23b9b-128">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="23b9b-128">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="23b9b-129">Содержит коллекцию поведений конечной точки клиента Windows Communication Foundation (WCF) для использования при взаимодействии с заданными службами маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="23b9b-129">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23b9b-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="23b9b-130">Remarks</span></span>  
 <span data-ttu-id="23b9b-131">`issuerAddress` содержит URI службы токенов безопасности, с которым клиент хочет обмениваться данными.</span><span class="sxs-lookup"><span data-stu-id="23b9b-131">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="23b9b-132">`behaviorConfiguration` Указывает поведение конечной точки, приложение использует в каналах, созданных в Windows Communication Foundation (WCF) для получения маркеров, выданных из службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="23b9b-132">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23b9b-133">См. также</span><span class="sxs-lookup"><span data-stu-id="23b9b-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [<span data-ttu-id="23b9b-134">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="23b9b-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="23b9b-135">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="23b9b-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="23b9b-136">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="23b9b-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="23b9b-137">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="23b9b-137">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="23b9b-138">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="23b9b-138">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="23b9b-139">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="23b9b-139">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="23b9b-140">Практическое руководство. Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="23b9b-140">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="23b9b-141">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="23b9b-141">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="23b9b-142">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="23b9b-142">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
