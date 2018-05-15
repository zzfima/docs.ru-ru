---
title: '&lt;transport&gt; для &lt;netPeerTcpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: c94336413424542f6fc6c0ef5b400b10ae715cd8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="lttransportgt-of-ltnetpeertcpbindinggt"></a><span data-ttu-id="6306a-102">&lt;transport&gt; для &lt;netPeerTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="6306a-102">&lt;transport&gt; of &lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="6306a-103">Задает параметры безопасности на транспортном уровне при использовании [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="6306a-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="6306a-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6306a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6306a-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="6306a-105">\<bindings></span></span>  
<span data-ttu-id="6306a-106">\<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="6306a-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="6306a-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="6306a-107">\<binding></span></span>  
<span data-ttu-id="6306a-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="6306a-108">\<security></span></span>  
<span data-ttu-id="6306a-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="6306a-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6306a-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6306a-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6306a-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6306a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6306a-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6306a-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6306a-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6306a-113">Attributes</span></span>  
  
|<span data-ttu-id="6306a-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6306a-114">Attribute</span></span>|<span data-ttu-id="6306a-115">Описание</span><span class="sxs-lookup"><span data-stu-id="6306a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6306a-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="6306a-116">credentialType</span></span>|<span data-ttu-id="6306a-117">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="6306a-117">Optional.</span></span> <span data-ttu-id="6306a-118">Задает тип учетных данных, используемых для проверки сообщений, отправляемых с помощью однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="6306a-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="6306a-119">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="6306a-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="6306a-120">Атрибут credentialType</span><span class="sxs-lookup"><span data-stu-id="6306a-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="6306a-121">Значение</span><span class="sxs-lookup"><span data-stu-id="6306a-121">Value</span></span>|<span data-ttu-id="6306a-122">Описание</span><span class="sxs-lookup"><span data-stu-id="6306a-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6306a-123">Сертификат</span><span class="sxs-lookup"><span data-stu-id="6306a-123">Certificate</span></span>|<span data-ttu-id="6306a-124">Для проверки подлинности однорангового транспорта канала необходим сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="6306a-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="6306a-125">Пароль</span><span class="sxs-lookup"><span data-stu-id="6306a-125">Password</span></span>|<span data-ttu-id="6306a-126">Для проверки подлинности однорангового транспорта канала необходим правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="6306a-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6306a-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6306a-127">Child Elements</span></span>  
 <span data-ttu-id="6306a-128">Нет</span><span class="sxs-lookup"><span data-stu-id="6306a-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6306a-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6306a-129">Parent Elements</span></span>  
  
|<span data-ttu-id="6306a-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="6306a-130">Element</span></span>|<span data-ttu-id="6306a-131">Описание</span><span class="sxs-lookup"><span data-stu-id="6306a-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6306a-132">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="6306a-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="6306a-133">Определяет параметры безопасности для [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="6306a-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6306a-134">См. также</span><span class="sxs-lookup"><span data-stu-id="6306a-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 [<span data-ttu-id="6306a-135">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="6306a-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="6306a-136">Привязки</span><span class="sxs-lookup"><span data-stu-id="6306a-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="6306a-137">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="6306a-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="6306a-138">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="6306a-138">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="6306a-139">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="6306a-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
