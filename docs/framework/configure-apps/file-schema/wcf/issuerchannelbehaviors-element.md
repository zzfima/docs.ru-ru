---
title: Элемент <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: e0e41b4f6d66cd4455c43dda7c77798553f2b58f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929929"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="5d5f4-102">\<Элемент > issuerChannelBehaviors</span><span class="sxs-lookup"><span data-stu-id="5d5f4-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="5d5f4-103">Содержит коллекцию поведений конечной точки клиента Windows Communication Foundation (WCF) (определенную в конфигурации) для использования при взаимодействии с указанными службами маркеров службы.</span><span class="sxs-lookup"><span data-stu-id="5d5f4-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="5d5f4-104">Определенные поведения не могут включать в себя [ \<> элементы ClientCredentials](clientcredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="5d5f4-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

```xml
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior>
        <clientCredentials>
          <issuedToken>
            <issuerChannelBehaviors>
```

## <a name="syntax"></a><span data-ttu-id="5d5f4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d5f4-105">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5d5f4-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5d5f4-106">Attributes and Elements</span></span>

<span data-ttu-id="5d5f4-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5d5f4-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="5d5f4-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5d5f4-108">Attributes</span></span>

<span data-ttu-id="5d5f4-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="5d5f4-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5d5f4-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5d5f4-110">Child Elements</span></span>

|<span data-ttu-id="5d5f4-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="5d5f4-111">Element</span></span>|<span data-ttu-id="5d5f4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5d5f4-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5d5f4-113">\<add></span><span class="sxs-lookup"><span data-stu-id="5d5f4-113">\<add></span></span>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="5d5f4-114">Добавляет поведение в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="5d5f4-114">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5d5f4-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5d5f4-115">Parent Elements</span></span>

|<span data-ttu-id="5d5f4-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="5d5f4-116">Element</span></span>|<span data-ttu-id="5d5f4-117">Описание</span><span class="sxs-lookup"><span data-stu-id="5d5f4-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5d5f4-118">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="5d5f4-118">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="5d5f4-119">Задает пользовательский маркер, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="5d5f4-119">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5d5f4-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="5d5f4-120">Remarks</span></span>

<span data-ttu-id="5d5f4-121">Этот элемент используется, когда для связи со службой необходимо любое поведение (кроме поведений, в которые включаются элементы `<clientCredentials>`).</span><span class="sxs-lookup"><span data-stu-id="5d5f4-121">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="5d5f4-122">Например, если [ \<](datacontractserializer-element.md) необходимо добавить элемент поведения dataContractSerializer >.</span><span class="sxs-lookup"><span data-stu-id="5d5f4-122">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d5f4-123">См. также</span><span class="sxs-lookup"><span data-stu-id="5d5f4-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="5d5f4-124">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="5d5f4-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="5d5f4-125">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="5d5f4-125">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="5d5f4-126">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="5d5f4-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="5d5f4-127">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="5d5f4-127">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5d5f4-128">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="5d5f4-128">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="5d5f4-129">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="5d5f4-129">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="5d5f4-130">Практическое руководство. Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="5d5f4-130">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="5d5f4-131">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="5d5f4-131">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
