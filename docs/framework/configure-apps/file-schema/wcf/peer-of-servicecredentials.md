---
title: <peer> из <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: d726ab460141b1e373a1cabf770b8958f50319eb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59219152"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="0d43d-102">\<Одноранговый > из \<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="0d43d-102">\<peer> of \<serviceCredentials></span></span>
<span data-ttu-id="0d43d-103">Задает текущие учетные данные для однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="0d43d-103">Specifies the current credentials for a peer node.</span></span>  
  
 <span data-ttu-id="0d43d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0d43d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0d43d-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="0d43d-105">\<behaviors></span></span>  
<span data-ttu-id="0d43d-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="0d43d-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="0d43d-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="0d43d-107">\<behavior></span></span>  
<span data-ttu-id="0d43d-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="0d43d-108">\<serviceCredentials></span></span>  
<span data-ttu-id="0d43d-109">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="0d43d-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d43d-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d43d-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d43d-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0d43d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0d43d-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0d43d-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d43d-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0d43d-113">Attributes</span></span>  
 <span data-ttu-id="0d43d-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0d43d-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0d43d-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0d43d-115">Child Elements</span></span>  
  
|<span data-ttu-id="0d43d-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="0d43d-116">Element</span></span>|<span data-ttu-id="0d43d-117">Описание</span><span class="sxs-lookup"><span data-stu-id="0d43d-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d43d-118">\<сертификат ></span><span class="sxs-lookup"><span data-stu-id="0d43d-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-peer.md)|<span data-ttu-id="0d43d-119">Задает сертификат X.509, используемый для подписи и шифрования сообщений для служб одноранговых сетей.</span><span class="sxs-lookup"><span data-stu-id="0d43d-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="0d43d-120">.</span><span class="sxs-lookup"><span data-stu-id="0d43d-120">.</span></span>|  
|[<span data-ttu-id="0d43d-121">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="0d43d-121">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication.md)|<span data-ttu-id="0d43d-122">Задает параметры проверки подлинности для отправителей сообщений.</span><span class="sxs-lookup"><span data-stu-id="0d43d-122">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="0d43d-123">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="0d43d-123">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication.md)|<span data-ttu-id="0d43d-124">Задает параметры проверки подлинности для одноранговых служб.</span><span class="sxs-lookup"><span data-stu-id="0d43d-124">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0d43d-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0d43d-125">Parent Elements</span></span>  
  
|<span data-ttu-id="0d43d-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="0d43d-126">Element</span></span>|<span data-ttu-id="0d43d-127">Описание</span><span class="sxs-lookup"><span data-stu-id="0d43d-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d43d-128">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="0d43d-128">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="0d43d-129">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="0d43d-129">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0d43d-130">См. также</span><span class="sxs-lookup"><span data-stu-id="0d43d-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="0d43d-131">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="0d43d-131">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="0d43d-132">[Проверка подлинности сообщений однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="0d43d-132">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="0d43d-133">[Нестандартной проверки подлинности одноранговых каналов](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="0d43d-133">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="0d43d-134">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="0d43d-134">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="0d43d-135">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="0d43d-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
