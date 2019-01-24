---
title: '&lt;peer&gt;’ для &lt;serviceCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: 132c001de02e223375453c91832f461b96b57dfe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741273"
---
# <a name="ltpeergt-of-ltservicecredentialsgt"></a><span data-ttu-id="05c1d-102">&lt;peer&gt;’ для &lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="05c1d-102">&lt;peer&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="05c1d-103">Задает текущие учетные данные для однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="05c1d-103">Specifies the current credentials for a peer node.</span></span>  
  
 <span data-ttu-id="05c1d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="05c1d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="05c1d-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="05c1d-105">\<behaviors></span></span>  
<span data-ttu-id="05c1d-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="05c1d-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="05c1d-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="05c1d-107">\<behavior></span></span>  
<span data-ttu-id="05c1d-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="05c1d-108">\<serviceCredentials></span></span>  
<span data-ttu-id="05c1d-109">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="05c1d-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05c1d-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05c1d-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05c1d-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="05c1d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="05c1d-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="05c1d-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05c1d-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="05c1d-113">Attributes</span></span>  
 <span data-ttu-id="05c1d-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="05c1d-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="05c1d-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="05c1d-115">Child Elements</span></span>  
  
|<span data-ttu-id="05c1d-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="05c1d-116">Element</span></span>|<span data-ttu-id="05c1d-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="05c1d-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05c1d-118">\<сертификат ></span><span class="sxs-lookup"><span data-stu-id="05c1d-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-peer.md)|<span data-ttu-id="05c1d-119">Задает сертификат X.509, используемый для подписи и шифрования сообщений для служб одноранговых сетей.</span><span class="sxs-lookup"><span data-stu-id="05c1d-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="05c1d-120">.</span><span class="sxs-lookup"><span data-stu-id="05c1d-120">.</span></span>|  
|[<span data-ttu-id="05c1d-121">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="05c1d-121">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication.md)|<span data-ttu-id="05c1d-122">Задает параметры проверки подлинности для отправителей сообщений.</span><span class="sxs-lookup"><span data-stu-id="05c1d-122">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="05c1d-123">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="05c1d-123">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication.md)|<span data-ttu-id="05c1d-124">Задает параметры проверки подлинности для одноранговых служб.</span><span class="sxs-lookup"><span data-stu-id="05c1d-124">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="05c1d-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="05c1d-125">Parent Elements</span></span>  
  
|<span data-ttu-id="05c1d-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="05c1d-126">Element</span></span>|<span data-ttu-id="05c1d-127">Описание:</span><span class="sxs-lookup"><span data-stu-id="05c1d-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05c1d-128">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="05c1d-128">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="05c1d-129">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="05c1d-129">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05c1d-130">См. также</span><span class="sxs-lookup"><span data-stu-id="05c1d-130">See also</span></span>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="05c1d-131">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="05c1d-131">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="05c1d-132">Проверка подлинности сообщений однорангового канала</span><span class="sxs-lookup"><span data-stu-id="05c1d-132">Peer Channel Message Authentication</span></span>](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)
- [<span data-ttu-id="05c1d-133">Нестандартной проверки подлинности одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="05c1d-133">Peer Channel Custom Authentication</span></span>](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)
- [<span data-ttu-id="05c1d-134">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="05c1d-134">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="05c1d-135">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="05c1d-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
