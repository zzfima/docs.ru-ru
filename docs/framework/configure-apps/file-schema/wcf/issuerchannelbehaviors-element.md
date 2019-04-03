---
title: <issuerChannelBehaviors> Элемент
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: 7cbd50daa82b0ca937a1bba93786545898b03c8b
ms.sourcegitcommit: 5c2176883dc3107445702724a7caa7ac2f6cb0d3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2019
ms.locfileid: "58890479"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="13ebf-102">\<issuerChannelBehaviors > элемент</span><span class="sxs-lookup"><span data-stu-id="13ebf-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="13ebf-103">Содержит коллекцию поведений конечной точки клиента "Windows Communication Foundation (WCF)" (определенных в конфигурации) для использования при взаимодействии с заданными службами маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="13ebf-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="13ebf-104">Определенным поведениям не могут содержать [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="13ebf-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>

```xml
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior>
        <clientCredentials>
          <issuedToken>
            <issuerChannelBehaviors>
```

## <a name="syntax"></a><span data-ttu-id="13ebf-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13ebf-105">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="13ebf-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="13ebf-106">Attributes and Elements</span></span>

<span data-ttu-id="13ebf-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="13ebf-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="13ebf-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="13ebf-108">Attributes</span></span>

<span data-ttu-id="13ebf-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="13ebf-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="13ebf-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="13ebf-110">Child Elements</span></span>

|<span data-ttu-id="13ebf-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="13ebf-111">Element</span></span>|<span data-ttu-id="13ebf-112">Описание</span><span class="sxs-lookup"><span data-stu-id="13ebf-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="13ebf-113">\<add></span><span class="sxs-lookup"><span data-stu-id="13ebf-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="13ebf-114">Добавляет поведение в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="13ebf-114">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="13ebf-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="13ebf-115">Parent Elements</span></span>

|<span data-ttu-id="13ebf-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="13ebf-116">Element</span></span>|<span data-ttu-id="13ebf-117">Описание</span><span class="sxs-lookup"><span data-stu-id="13ebf-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="13ebf-118">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="13ebf-118">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="13ebf-119">Задает пользовательский маркер, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="13ebf-119">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="13ebf-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="13ebf-120">Remarks</span></span>

<span data-ttu-id="13ebf-121">Этот элемент используется, когда для связи со службой необходимо любое поведение (кроме поведений, в которые включаются элементы `<clientCredentials>`).</span><span class="sxs-lookup"><span data-stu-id="13ebf-121">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="13ebf-122">Например если [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) поведение элемент должен быть включен.</span><span class="sxs-lookup"><span data-stu-id="13ebf-122">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="13ebf-123">См. также</span><span class="sxs-lookup"><span data-stu-id="13ebf-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="13ebf-124">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="13ebf-124">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="13ebf-125">Поведение безопасности</span><span class="sxs-lookup"><span data-stu-id="13ebf-125">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="13ebf-126">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="13ebf-126">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="13ebf-127">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="13ebf-127">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="13ebf-128">Обеспечение безопасности клиентов</span><span class="sxs-lookup"><span data-stu-id="13ebf-128">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="13ebf-129">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="13ebf-129">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="13ebf-130">Практическое руководство. Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="13ebf-130">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="13ebf-131">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="13ebf-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
