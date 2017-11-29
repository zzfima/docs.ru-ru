---
title: "&lt;transport&gt; для &lt;netPeerTcpBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 60880461a3d71e64be2b3b74b1a236625426c2b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="lttransportgt-of-ltnetpeertcpbindinggt"></a><span data-ttu-id="a59aa-102">&lt;transport&gt; для &lt;netPeerTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="a59aa-102">&lt;transport&gt; of &lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="a59aa-103">Задает параметры безопасности на транспортном уровне при использовании [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a59aa-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="a59aa-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a59aa-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a59aa-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="a59aa-105">\<bindings></span></span>  
<span data-ttu-id="a59aa-106">\<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="a59aa-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="a59aa-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="a59aa-107">\<binding></span></span>  
<span data-ttu-id="a59aa-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="a59aa-108">\<security></span></span>  
<span data-ttu-id="a59aa-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="a59aa-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a59aa-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a59aa-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a59aa-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a59aa-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a59aa-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a59aa-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a59aa-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a59aa-113">Attributes</span></span>  
  
|<span data-ttu-id="a59aa-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a59aa-114">Attribute</span></span>|<span data-ttu-id="a59aa-115">Описание</span><span class="sxs-lookup"><span data-stu-id="a59aa-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a59aa-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="a59aa-116">credentialType</span></span>|<span data-ttu-id="a59aa-117">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="a59aa-117">Optional.</span></span> <span data-ttu-id="a59aa-118">Задает тип учетных данных, используемых для проверки сообщений, отправляемых с помощью однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="a59aa-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="a59aa-119">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="a59aa-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="a59aa-120">Атрибут credentialType</span><span class="sxs-lookup"><span data-stu-id="a59aa-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="a59aa-121">Значение</span><span class="sxs-lookup"><span data-stu-id="a59aa-121">Value</span></span>|<span data-ttu-id="a59aa-122">Описание</span><span class="sxs-lookup"><span data-stu-id="a59aa-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a59aa-123">Сертификат</span><span class="sxs-lookup"><span data-stu-id="a59aa-123">Certificate</span></span>|<span data-ttu-id="a59aa-124">Для проверки подлинности однорангового транспорта канала необходим сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="a59aa-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="a59aa-125">Пароль</span><span class="sxs-lookup"><span data-stu-id="a59aa-125">Password</span></span>|<span data-ttu-id="a59aa-126">Для проверки подлинности однорангового транспорта канала необходим правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="a59aa-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a59aa-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a59aa-127">Child Elements</span></span>  
 <span data-ttu-id="a59aa-128">Нет</span><span class="sxs-lookup"><span data-stu-id="a59aa-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a59aa-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a59aa-129">Parent Elements</span></span>  
  
|<span data-ttu-id="a59aa-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="a59aa-130">Element</span></span>|<span data-ttu-id="a59aa-131">Описание</span><span class="sxs-lookup"><span data-stu-id="a59aa-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a59aa-132">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="a59aa-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="a59aa-133">Определяет параметры безопасности для [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a59aa-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a59aa-134">См. также</span><span class="sxs-lookup"><span data-stu-id="a59aa-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 [<span data-ttu-id="a59aa-135">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="a59aa-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="a59aa-136">Привязки</span><span class="sxs-lookup"><span data-stu-id="a59aa-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a59aa-137">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="a59aa-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="a59aa-138">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="a59aa-138">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="a59aa-139">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="a59aa-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
