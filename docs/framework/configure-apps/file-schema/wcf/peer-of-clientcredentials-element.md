---
title: "&lt;peer&gt; элемент для элемента &lt;clientCredentials&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: accd6c261a393da3ffcffd261d6603d20b8fcb3d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltpeergt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="e9886-102">&lt;peer&gt; элемент для элемента &lt;clientCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="e9886-102">&lt;peer&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="e9886-103">Задает учетные данные, используемые при проверке подлинности одноранговых клиентов.</span><span class="sxs-lookup"><span data-stu-id="e9886-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="e9886-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e9886-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e9886-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="e9886-105">\<behaviors></span></span>  
<span data-ttu-id="e9886-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e9886-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="e9886-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="e9886-107">\<behavior></span></span>  
<span data-ttu-id="e9886-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="e9886-108">\<clientCredentials></span></span>  
<span data-ttu-id="e9886-109">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="e9886-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9886-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9886-110">Syntax</span></span>  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9886-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e9886-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e9886-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e9886-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9886-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e9886-113">Attributes</span></span>  
 <span data-ttu-id="e9886-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e9886-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e9886-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e9886-115">Child Elements</span></span>  
  
|<span data-ttu-id="e9886-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="e9886-116">Element</span></span>|<span data-ttu-id="e9886-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="e9886-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9886-118">\<сертификат ></span><span class="sxs-lookup"><span data-stu-id="e9886-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|<span data-ttu-id="e9886-119">Задает сертификат X.509, используемый для подписи и шифрования сообщений для клиентов одноранговых сетей.</span><span class="sxs-lookup"><span data-stu-id="e9886-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="e9886-120">.</span><span class="sxs-lookup"><span data-stu-id="e9886-120">.</span></span>|  
|[<span data-ttu-id="e9886-121">\<peerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="e9886-121">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|<span data-ttu-id="e9886-122">Задает параметры проверки подлинности для одноранговых клиентов.</span><span class="sxs-lookup"><span data-stu-id="e9886-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="e9886-123">\<messageSenderAuthentication ></span><span class="sxs-lookup"><span data-stu-id="e9886-123">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|<span data-ttu-id="e9886-124">Задает параметры проверки подлинности для отправителей сообщений.</span><span class="sxs-lookup"><span data-stu-id="e9886-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e9886-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e9886-125">Parent Elements</span></span>  
  
|<span data-ttu-id="e9886-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="e9886-126">Element</span></span>|<span data-ttu-id="e9886-127">Описание:</span><span class="sxs-lookup"><span data-stu-id="e9886-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9886-128">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="e9886-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="e9886-129">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="e9886-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9886-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="e9886-130">Remarks</span></span>  
 <span data-ttu-id="e9886-131">Этот элемент конфигурации задает учетные данные, используемые одноранговым узлом для подтверждения своей подлинности для других узлов в сетке, а также параметры, используемые одноранговым узлом для проверки подлинности других одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="e9886-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="e9886-132">Дополнительные сведения см. в разделе [проверки подлинности сообщения однорангового канала](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95) и [защита приложений одноранговых каналов](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="e9886-132">For more information, see [Peer Channel Message Authentication](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95) and [Securing Peer Channel Applications](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9886-133">См. также</span><span class="sxs-lookup"><span data-stu-id="e9886-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="e9886-134">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="e9886-134">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="e9886-135">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="e9886-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="e9886-136">Проверка подлинности сообщения одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="e9886-136">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="e9886-137">Нестандартная проверка подлинности одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="e9886-137">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="e9886-138">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="e9886-138">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="e9886-139">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e9886-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
