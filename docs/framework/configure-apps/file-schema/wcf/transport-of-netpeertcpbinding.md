---
title: <transport> из <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 837d01540fa63579877ab4085bd8034c78f2fbe0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915564"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="95017-102">\<транспортное \<> из netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="95017-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="95017-103">Задает параметры безопасности на транспортном уровне при использовании [ \<> netPeerTcpBinding](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="95017-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="95017-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="95017-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="95017-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="95017-105">\<bindings></span></span>  
<span data-ttu-id="95017-106">\<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="95017-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="95017-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="95017-107">\<binding></span></span>  
<span data-ttu-id="95017-108">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="95017-108">\<security></span></span>  
<span data-ttu-id="95017-109">\<> транспорта</span><span class="sxs-lookup"><span data-stu-id="95017-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95017-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95017-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95017-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="95017-111">Attributes and Elements</span></span>  
 <span data-ttu-id="95017-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="95017-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95017-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="95017-113">Attributes</span></span>  
  
|<span data-ttu-id="95017-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="95017-114">Attribute</span></span>|<span data-ttu-id="95017-115">Описание</span><span class="sxs-lookup"><span data-stu-id="95017-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="95017-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="95017-116">credentialType</span></span>|<span data-ttu-id="95017-117">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="95017-117">Optional.</span></span> <span data-ttu-id="95017-118">Задает тип учетных данных, используемых для проверки сообщений, отправляемых с помощью однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="95017-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="95017-119">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="95017-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="95017-120">Атрибут credentialType</span><span class="sxs-lookup"><span data-stu-id="95017-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="95017-121">Значение</span><span class="sxs-lookup"><span data-stu-id="95017-121">Value</span></span>|<span data-ttu-id="95017-122">Описание</span><span class="sxs-lookup"><span data-stu-id="95017-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="95017-123">Сертификат</span><span class="sxs-lookup"><span data-stu-id="95017-123">Certificate</span></span>|<span data-ttu-id="95017-124">Для проверки подлинности однорангового транспорта канала необходим сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="95017-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="95017-125">Пароль</span><span class="sxs-lookup"><span data-stu-id="95017-125">Password</span></span>|<span data-ttu-id="95017-126">Для проверки подлинности однорангового транспорта канала необходим правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="95017-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="95017-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="95017-127">Child Elements</span></span>  
 <span data-ttu-id="95017-128">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="95017-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="95017-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="95017-129">Parent Elements</span></span>  
  
|<span data-ttu-id="95017-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="95017-130">Element</span></span>|<span data-ttu-id="95017-131">Описание</span><span class="sxs-lookup"><span data-stu-id="95017-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95017-132">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="95017-132">\<security></span></span>](security-of-netpeerbinding.md)|<span data-ttu-id="95017-133">Определяет параметры безопасности для [ \<> netPeerTcpBinding](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="95017-133">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="95017-134">См. также</span><span class="sxs-lookup"><span data-stu-id="95017-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="95017-135">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="95017-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="95017-136">Привязки</span><span class="sxs-lookup"><span data-stu-id="95017-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="95017-137">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="95017-137">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="95017-138">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="95017-138">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="95017-139">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="95017-139">\<binding></span></span>](../../../misc/binding.md)
