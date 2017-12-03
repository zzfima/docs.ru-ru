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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 181e6a9458754934d6b3b27a31c2cf2dd3455f52
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="lttransportgt-of-ltnetpeertcpbindinggt"></a><span data-ttu-id="40c9e-102">&lt;transport&gt; для &lt;netPeerTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="40c9e-102">&lt;transport&gt; of &lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="40c9e-103">Задает параметры безопасности на транспортном уровне при использовании [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="40c9e-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="40c9e-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="40c9e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="40c9e-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="40c9e-105">\<bindings></span></span>  
<span data-ttu-id="40c9e-106">\<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="40c9e-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="40c9e-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="40c9e-107">\<binding></span></span>  
<span data-ttu-id="40c9e-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="40c9e-108">\<security></span></span>  
<span data-ttu-id="40c9e-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="40c9e-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40c9e-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40c9e-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40c9e-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="40c9e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="40c9e-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="40c9e-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40c9e-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="40c9e-113">Attributes</span></span>  
  
|<span data-ttu-id="40c9e-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="40c9e-114">Attribute</span></span>|<span data-ttu-id="40c9e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="40c9e-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="40c9e-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="40c9e-116">credentialType</span></span>|<span data-ttu-id="40c9e-117">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="40c9e-117">Optional.</span></span> <span data-ttu-id="40c9e-118">Задает тип учетных данных, используемых для проверки сообщений, отправляемых с помощью однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="40c9e-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="40c9e-119">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="40c9e-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="40c9e-120">Атрибут credentialType</span><span class="sxs-lookup"><span data-stu-id="40c9e-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="40c9e-121">Значение</span><span class="sxs-lookup"><span data-stu-id="40c9e-121">Value</span></span>|<span data-ttu-id="40c9e-122">Описание</span><span class="sxs-lookup"><span data-stu-id="40c9e-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="40c9e-123">Сертификат</span><span class="sxs-lookup"><span data-stu-id="40c9e-123">Certificate</span></span>|<span data-ttu-id="40c9e-124">Для проверки подлинности однорангового транспорта канала необходим сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="40c9e-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="40c9e-125">Пароль</span><span class="sxs-lookup"><span data-stu-id="40c9e-125">Password</span></span>|<span data-ttu-id="40c9e-126">Для проверки подлинности однорангового транспорта канала необходим правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="40c9e-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40c9e-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="40c9e-127">Child Elements</span></span>  
 <span data-ttu-id="40c9e-128">Нет</span><span class="sxs-lookup"><span data-stu-id="40c9e-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40c9e-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="40c9e-129">Parent Elements</span></span>  
  
|<span data-ttu-id="40c9e-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="40c9e-130">Element</span></span>|<span data-ttu-id="40c9e-131">Описание</span><span class="sxs-lookup"><span data-stu-id="40c9e-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40c9e-132">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="40c9e-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="40c9e-133">Определяет параметры безопасности для [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="40c9e-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="40c9e-134">См. также</span><span class="sxs-lookup"><span data-stu-id="40c9e-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 [<span data-ttu-id="40c9e-135">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="40c9e-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="40c9e-136">Привязки</span><span class="sxs-lookup"><span data-stu-id="40c9e-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="40c9e-137">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="40c9e-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="40c9e-138">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="40c9e-138">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="40c9e-139">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="40c9e-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
