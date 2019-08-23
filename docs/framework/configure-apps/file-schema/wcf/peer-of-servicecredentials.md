---
title: <peer> из <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: 50415cb9b35d2a2053efa3313a415de518b7e36e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933778"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="d7cac-102">\<Одноранговая \<> > ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="d7cac-102">\<peer> of \<serviceCredentials></span></span>
<span data-ttu-id="d7cac-103">Задает текущие учетные данные для однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="d7cac-103">Specifies the current credentials for a peer node.</span></span>  
  
 <span data-ttu-id="d7cac-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d7cac-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d7cac-105">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="d7cac-105">\<behaviors></span></span>  
<span data-ttu-id="d7cac-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d7cac-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="d7cac-107">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="d7cac-107">\<behavior></span></span>  
<span data-ttu-id="d7cac-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="d7cac-108">\<serviceCredentials></span></span>  
<span data-ttu-id="d7cac-109">\<Одноранговые ></span><span class="sxs-lookup"><span data-stu-id="d7cac-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7cac-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7cac-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7cac-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d7cac-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d7cac-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d7cac-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7cac-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d7cac-113">Attributes</span></span>  
 <span data-ttu-id="d7cac-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="d7cac-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d7cac-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d7cac-115">Child Elements</span></span>  
  
|<span data-ttu-id="d7cac-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="d7cac-116">Element</span></span>|<span data-ttu-id="d7cac-117">Описание</span><span class="sxs-lookup"><span data-stu-id="d7cac-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7cac-118">\<> сертификата</span><span class="sxs-lookup"><span data-stu-id="d7cac-118">\<certificate></span></span>](certificate-of-peer.md)|<span data-ttu-id="d7cac-119">Задает сертификат X.509, используемый для подписи и шифрования сообщений для служб одноранговых сетей.</span><span class="sxs-lookup"><span data-stu-id="d7cac-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="d7cac-120">.</span><span class="sxs-lookup"><span data-stu-id="d7cac-120">.</span></span>|  
|[<span data-ttu-id="d7cac-121">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="d7cac-121">\<messageSenderAuthentication></span></span>](messagesenderauthentication.md)|<span data-ttu-id="d7cac-122">Задает параметры проверки подлинности для отправителей сообщений.</span><span class="sxs-lookup"><span data-stu-id="d7cac-122">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="d7cac-123">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="d7cac-123">\<peerAuthentication></span></span>](peerauthentication.md)|<span data-ttu-id="d7cac-124">Задает параметры проверки подлинности для одноранговых служб.</span><span class="sxs-lookup"><span data-stu-id="d7cac-124">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d7cac-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d7cac-125">Parent Elements</span></span>  
  
|<span data-ttu-id="d7cac-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="d7cac-126">Element</span></span>|<span data-ttu-id="d7cac-127">Описание</span><span class="sxs-lookup"><span data-stu-id="d7cac-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7cac-128">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="d7cac-128">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="d7cac-129">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="d7cac-129">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d7cac-130">См. также</span><span class="sxs-lookup"><span data-stu-id="d7cac-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="d7cac-131">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="d7cac-131">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="d7cac-132">[Проверка подлинности сообщений однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="d7cac-132">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="d7cac-133">[Пользовательская проверка подлинности однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="d7cac-133">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="d7cac-134">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="d7cac-134">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="d7cac-135">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="d7cac-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
