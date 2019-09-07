---
title: <peer> элемента <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: dce7ef64de1e3eb248e3553c97cbce8e9b205b4c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400100"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="e5d58-102">\<Одноранговая \<> >ного элемента ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="e5d58-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="e5d58-103">Задает учетные данные, используемые при проверке подлинности одноранговых клиентов.</span><span class="sxs-lookup"><span data-stu-id="e5d58-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
<span data-ttu-id="e5d58-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e5d58-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e5d58-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e5d58-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e5d58-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e5d58-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="e5d58-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e5d58-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="e5d58-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e5d58-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="e5d58-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="e5d58-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="e5d58-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Одноранговые >**</span><span class="sxs-lookup"><span data-stu-id="e5d58-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5d58-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5d58-111">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5d58-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e5d58-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e5d58-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e5d58-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5d58-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e5d58-114">Attributes</span></span>  
 <span data-ttu-id="e5d58-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="e5d58-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e5d58-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e5d58-116">Child Elements</span></span>  
  
|<span data-ttu-id="e5d58-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="e5d58-117">Element</span></span>|<span data-ttu-id="e5d58-118">Описание</span><span class="sxs-lookup"><span data-stu-id="e5d58-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5d58-119">\<> сертификата</span><span class="sxs-lookup"><span data-stu-id="e5d58-119">\<certificate></span></span>](certificate-element.md)|<span data-ttu-id="e5d58-120">Задает сертификат X.509, используемый для подписи и шифрования сообщений для клиентов одноранговых сетей.</span><span class="sxs-lookup"><span data-stu-id="e5d58-120">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="e5d58-121">.</span><span class="sxs-lookup"><span data-stu-id="e5d58-121">.</span></span>|  
|[<span data-ttu-id="e5d58-122">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="e5d58-122">\<peerAuthentication></span></span>](peerauthentication-element.md)|<span data-ttu-id="e5d58-123">Задает параметры проверки подлинности для одноранговых клиентов.</span><span class="sxs-lookup"><span data-stu-id="e5d58-123">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="e5d58-124">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="e5d58-124">\<messageSenderAuthentication></span></span>](messagesenderauthentication-element.md)|<span data-ttu-id="e5d58-125">Задает параметры проверки подлинности для отправителей сообщений.</span><span class="sxs-lookup"><span data-stu-id="e5d58-125">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e5d58-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e5d58-126">Parent Elements</span></span>  
  
|<span data-ttu-id="e5d58-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="e5d58-127">Element</span></span>|<span data-ttu-id="e5d58-128">Описание</span><span class="sxs-lookup"><span data-stu-id="e5d58-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5d58-129">\<> clientCredentials</span><span class="sxs-lookup"><span data-stu-id="e5d58-129">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="e5d58-130">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="e5d58-130">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5d58-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="e5d58-131">Remarks</span></span>  
 <span data-ttu-id="e5d58-132">Этот элемент конфигурации задает учетные данные, используемые одноранговым узлом для подтверждения своей подлинности для других узлов в сетке, а также параметры, используемые одноранговым узлом для проверки подлинности других одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="e5d58-132">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="e5d58-133">Дополнительные сведения см. в статье [Проверка подлинности сообщений одноранговых каналов](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) и [Защита приложений одноранговых каналов](../../../wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="e5d58-133">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5d58-134">См. также</span><span class="sxs-lookup"><span data-stu-id="e5d58-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="e5d58-135">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="e5d58-135">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="e5d58-136">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="e5d58-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- <span data-ttu-id="e5d58-137">[Проверка подлинности сообщений однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e5d58-137">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="e5d58-138">[Пользовательская проверка подлинности однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e5d58-138">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="e5d58-139">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="e5d58-139">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="e5d58-140">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e5d58-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
