---
title: <transport> из <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: f5feca232265cbcad7feff78c0c66e3606c8567e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270396"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="6b4c6-102">\<Транспорт > из \<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="6b4c6-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="6b4c6-103">Указывает параметры безопасности уровня транспорта при использовании [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="6b4c6-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="6b4c6-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6b4c6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6b4c6-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="6b4c6-105">\<bindings></span></span>  
<span data-ttu-id="6b4c6-106">\<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="6b4c6-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="6b4c6-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="6b4c6-107">\<binding></span></span>  
<span data-ttu-id="6b4c6-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="6b4c6-108">\<security></span></span>  
<span data-ttu-id="6b4c6-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="6b4c6-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b4c6-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6b4c6-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b4c6-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6b4c6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6b4c6-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6b4c6-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b4c6-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6b4c6-113">Attributes</span></span>  
  
|<span data-ttu-id="6b4c6-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6b4c6-114">Attribute</span></span>|<span data-ttu-id="6b4c6-115">Описание</span><span class="sxs-lookup"><span data-stu-id="6b4c6-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6b4c6-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="6b4c6-116">credentialType</span></span>|<span data-ttu-id="6b4c6-117">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="6b4c6-117">Optional.</span></span> <span data-ttu-id="6b4c6-118">Задает тип учетных данных, используемых для проверки сообщений, отправляемых с помощью однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="6b4c6-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="6b4c6-119">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="6b4c6-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="6b4c6-120">Атрибут credentialType</span><span class="sxs-lookup"><span data-stu-id="6b4c6-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="6b4c6-121">Значение</span><span class="sxs-lookup"><span data-stu-id="6b4c6-121">Value</span></span>|<span data-ttu-id="6b4c6-122">Описание</span><span class="sxs-lookup"><span data-stu-id="6b4c6-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6b4c6-123">Сертификат</span><span class="sxs-lookup"><span data-stu-id="6b4c6-123">Certificate</span></span>|<span data-ttu-id="6b4c6-124">Для проверки подлинности однорангового транспорта канала необходим сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="6b4c6-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="6b4c6-125">Пароль</span><span class="sxs-lookup"><span data-stu-id="6b4c6-125">Password</span></span>|<span data-ttu-id="6b4c6-126">Для проверки подлинности однорангового транспорта канала необходим правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="6b4c6-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b4c6-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6b4c6-127">Child Elements</span></span>  
 <span data-ttu-id="6b4c6-128">Нет</span><span class="sxs-lookup"><span data-stu-id="6b4c6-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6b4c6-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6b4c6-129">Parent Elements</span></span>  
  
|<span data-ttu-id="6b4c6-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="6b4c6-130">Element</span></span>|<span data-ttu-id="6b4c6-131">Описание</span><span class="sxs-lookup"><span data-stu-id="6b4c6-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b4c6-132">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="6b4c6-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="6b4c6-133">Определяет параметры безопасности для [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="6b4c6-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6b4c6-134">См. также</span><span class="sxs-lookup"><span data-stu-id="6b4c6-134">See also</span></span>
- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="6b4c6-135">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="6b4c6-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6b4c6-136">Привязки</span><span class="sxs-lookup"><span data-stu-id="6b4c6-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="6b4c6-137">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="6b4c6-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6b4c6-138">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="6b4c6-138">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="6b4c6-139">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="6b4c6-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
