---
title: "Элемент &lt;issuerChannelBehaviors&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b73d090aa47e18792d313b3d086e7a667e74bb08
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltissuerchannelbehaviorsgt-element"></a><span data-ttu-id="5c17c-102">Элемент &lt;issuerChannelBehaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="5c17c-102">&lt;issuerChannelBehaviors&gt; Element</span></span>
<span data-ttu-id="5c17c-103">Содержит коллекцию поведений конечной точки клиента [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (определенных в конфигурации) для использования при взаимодействии с заданными службами маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="5c17c-103">Contains a collection of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="5c17c-104">Не могут содержать заданные поведения [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="5c17c-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>  
  
 <span data-ttu-id="5c17c-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5c17c-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="5c17c-106">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="5c17c-106">\<behaviors></span></span>  
<span data-ttu-id="5c17c-107">раздел endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="5c17c-107">endpointBehaviors section</span></span>  
<span data-ttu-id="5c17c-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="5c17c-108">\<behavior></span></span>  
<span data-ttu-id="5c17c-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="5c17c-109">\<clientCredentials></span></span>  
<span data-ttu-id="5c17c-110">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="5c17c-110">\<issuedToken></span></span>  
<span data-ttu-id="5c17c-111">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5c17c-111">\<issuerChannelBehaviors></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c17c-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c17c-112">Syntax</span></span>  
  
```xml  
<issuerChannelBehaviors>  
      <add behaviorConfiguraton="string"  
                issuerAddress="string" />  
</issuerChannelBehaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c17c-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5c17c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="5c17c-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5c17c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c17c-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5c17c-115">Attributes</span></span>  
 <span data-ttu-id="5c17c-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5c17c-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5c17c-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5c17c-117">Child Elements</span></span>  
  
|<span data-ttu-id="5c17c-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="5c17c-118">Element</span></span>|<span data-ttu-id="5c17c-119">Описание</span><span class="sxs-lookup"><span data-stu-id="5c17c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c17c-120">\<add></span><span class="sxs-lookup"><span data-stu-id="5c17c-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="5c17c-121">Добавляет поведение в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="5c17c-121">Adds a behavior to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5c17c-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5c17c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="5c17c-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="5c17c-123">Element</span></span>|<span data-ttu-id="5c17c-124">Описание</span><span class="sxs-lookup"><span data-stu-id="5c17c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c17c-125">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="5c17c-125">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="5c17c-126">Задает пользовательский маркер, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="5c17c-126">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c17c-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="5c17c-127">Remarks</span></span>  
 <span data-ttu-id="5c17c-128">Этот элемент используется, когда для связи со службой необходимо любое поведение (кроме поведений, в которые включаются элементы `<clientCredentials>`).</span><span class="sxs-lookup"><span data-stu-id="5c17c-128">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="5c17c-129">Например если [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) поведение элемент должен быть включен.</span><span class="sxs-lookup"><span data-stu-id="5c17c-129">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c17c-130">См. также</span><span class="sxs-lookup"><span data-stu-id="5c17c-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [<span data-ttu-id="5c17c-131">Службы идентификации и проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="5c17c-131">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="5c17c-132">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="5c17c-132">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="5c17c-133">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="5c17c-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="5c17c-134">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="5c17c-134">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="5c17c-135">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="5c17c-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="5c17c-136">Как: создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="5c17c-136">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="5c17c-137">Как: Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="5c17c-137">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="5c17c-138">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="5c17c-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
