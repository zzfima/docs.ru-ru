---
title: Элемент <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: 624848db4cead14e46c97bba7404adcb65e43d4d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55274150"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="e38b5-102">\<issuerChannelBehaviors > элемент</span><span class="sxs-lookup"><span data-stu-id="e38b5-102">\<issuerChannelBehaviors> Element</span></span>
<span data-ttu-id="e38b5-103">Содержит коллекцию поведений конечной точки клиента "Windows Communication Foundation (WCF)" (определенных в конфигурации) для использования при взаимодействии с заданными службами маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="e38b5-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="e38b5-104">Определенным поведениям не могут содержать [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="e38b5-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>  
  
 <span data-ttu-id="e38b5-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e38b5-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e38b5-106">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="e38b5-106">\<behaviors></span></span>  
<span data-ttu-id="e38b5-107">раздел endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="e38b5-107">endpointBehaviors section</span></span>  
<span data-ttu-id="e38b5-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="e38b5-108">\<behavior></span></span>  
<span data-ttu-id="e38b5-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="e38b5-109">\<clientCredentials></span></span>  
<span data-ttu-id="e38b5-110">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="e38b5-110">\<issuedToken></span></span>  
<span data-ttu-id="e38b5-111">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="e38b5-111">\<issuerChannelBehaviors></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e38b5-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e38b5-112">Syntax</span></span>  
  
```xml  
<issuerChannelBehaviors>
  <add behaviorConfiguraton="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e38b5-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e38b5-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e38b5-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e38b5-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e38b5-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e38b5-115">Attributes</span></span>  
 <span data-ttu-id="e38b5-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e38b5-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e38b5-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e38b5-117">Child Elements</span></span>  
  
|<span data-ttu-id="e38b5-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="e38b5-118">Element</span></span>|<span data-ttu-id="e38b5-119">Описание</span><span class="sxs-lookup"><span data-stu-id="e38b5-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e38b5-120">\<add></span><span class="sxs-lookup"><span data-stu-id="e38b5-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="e38b5-121">Добавляет поведение в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="e38b5-121">Adds a behavior to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e38b5-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e38b5-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e38b5-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="e38b5-123">Element</span></span>|<span data-ttu-id="e38b5-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="e38b5-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e38b5-125">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="e38b5-125">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="e38b5-126">Задает пользовательский маркер, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="e38b5-126">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e38b5-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="e38b5-127">Remarks</span></span>  
 <span data-ttu-id="e38b5-128">Этот элемент используется, когда для связи со службой необходимо любое поведение (кроме поведений, в которые включаются элементы `<clientCredentials>`).</span><span class="sxs-lookup"><span data-stu-id="e38b5-128">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="e38b5-129">Например если [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) поведение элемент должен быть включен.</span><span class="sxs-lookup"><span data-stu-id="e38b5-129">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e38b5-130">См. также</span><span class="sxs-lookup"><span data-stu-id="e38b5-130">See also</span></span>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="e38b5-131">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="e38b5-131">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="e38b5-132">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="e38b5-132">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="e38b5-133">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="e38b5-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="e38b5-134">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e38b5-134">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e38b5-135">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="e38b5-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="e38b5-136">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="e38b5-136">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="e38b5-137">Практическое руководство. Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="e38b5-137">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="e38b5-138">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="e38b5-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
