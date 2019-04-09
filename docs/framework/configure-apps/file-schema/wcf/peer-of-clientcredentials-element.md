---
title: <peer> из <clientCredentials> элемент
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 7074ee992755557d7e5503035c89bdbefd678792
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107241"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="e5010-102">\<Одноранговый > из \<clientCredentials > элемент</span><span class="sxs-lookup"><span data-stu-id="e5010-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="e5010-103">Задает учетные данные, используемые при проверке подлинности одноранговых клиентов.</span><span class="sxs-lookup"><span data-stu-id="e5010-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="e5010-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e5010-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e5010-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="e5010-105">\<behaviors></span></span>  
<span data-ttu-id="e5010-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="e5010-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="e5010-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="e5010-107">\<behavior></span></span>  
<span data-ttu-id="e5010-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="e5010-108">\<clientCredentials></span></span>  
<span data-ttu-id="e5010-109">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="e5010-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5010-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5010-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5010-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e5010-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e5010-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e5010-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5010-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e5010-113">Attributes</span></span>  
 <span data-ttu-id="e5010-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e5010-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e5010-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e5010-115">Child Elements</span></span>  
  
|<span data-ttu-id="e5010-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="e5010-116">Element</span></span>|<span data-ttu-id="e5010-117">Описание</span><span class="sxs-lookup"><span data-stu-id="e5010-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5010-118">\<сертификат ></span><span class="sxs-lookup"><span data-stu-id="e5010-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|<span data-ttu-id="e5010-119">Задает сертификат X.509, используемый для подписи и шифрования сообщений для клиентов одноранговых сетей.</span><span class="sxs-lookup"><span data-stu-id="e5010-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="e5010-120">.</span><span class="sxs-lookup"><span data-stu-id="e5010-120">.</span></span>|  
|[<span data-ttu-id="e5010-121">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="e5010-121">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|<span data-ttu-id="e5010-122">Задает параметры проверки подлинности для одноранговых клиентов.</span><span class="sxs-lookup"><span data-stu-id="e5010-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="e5010-123">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="e5010-123">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|<span data-ttu-id="e5010-124">Задает параметры проверки подлинности для отправителей сообщений.</span><span class="sxs-lookup"><span data-stu-id="e5010-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e5010-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e5010-125">Parent Elements</span></span>  
  
|<span data-ttu-id="e5010-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="e5010-126">Element</span></span>|<span data-ttu-id="e5010-127">Описание</span><span class="sxs-lookup"><span data-stu-id="e5010-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5010-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="e5010-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="e5010-129">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="e5010-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5010-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="e5010-130">Remarks</span></span>  
 <span data-ttu-id="e5010-131">Этот элемент конфигурации задает учетные данные, используемые одноранговым узлом для подтверждения своей подлинности для других узлов в сетке, а также параметры, используемые одноранговым узлом для проверки подлинности других одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="e5010-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="e5010-132">Дополнительные сведения см. в разделе [проверки подлинности сообщений однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) и [защита приложений одноранговых каналов](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="e5010-132">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5010-133">См. также</span><span class="sxs-lookup"><span data-stu-id="e5010-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="e5010-134">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="e5010-134">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="e5010-135">Обеспечение безопасности клиентов</span><span class="sxs-lookup"><span data-stu-id="e5010-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="e5010-136">Проверка подлинности сообщений для однорангового канала</span><span class="sxs-lookup"><span data-stu-id="e5010-136">Peer Channel Message Authentication</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [<span data-ttu-id="e5010-137">Пользовательской проверка подлинности для однорангового канала</span><span class="sxs-lookup"><span data-stu-id="e5010-137">Peer Channel Custom Authentication</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [<span data-ttu-id="e5010-138">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="e5010-138">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="e5010-139">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e5010-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
