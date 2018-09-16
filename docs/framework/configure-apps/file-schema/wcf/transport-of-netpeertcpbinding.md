---
title: '&lt;transport&gt; для &lt;netPeerTcpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 2b89ae090d24ff6aad1aae1b39a0a18961bd2537
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2018
ms.locfileid: "45678050"
---
# <a name="lttransportgt-of-ltnetpeertcpbindinggt"></a><span data-ttu-id="890f3-102">&lt;transport&gt; для &lt;netPeerTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="890f3-102">&lt;transport&gt; of &lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="890f3-103">Указывает параметры безопасности уровня транспорта при использовании [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="890f3-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="890f3-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="890f3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="890f3-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="890f3-105">\<bindings></span></span>  
<span data-ttu-id="890f3-106">\<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="890f3-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="890f3-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="890f3-107">\<binding></span></span>  
<span data-ttu-id="890f3-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="890f3-108">\<security></span></span>  
<span data-ttu-id="890f3-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="890f3-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="890f3-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="890f3-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="890f3-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="890f3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="890f3-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="890f3-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="890f3-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="890f3-113">Attributes</span></span>  
  
|<span data-ttu-id="890f3-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="890f3-114">Attribute</span></span>|<span data-ttu-id="890f3-115">Описание</span><span class="sxs-lookup"><span data-stu-id="890f3-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="890f3-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="890f3-116">credentialType</span></span>|<span data-ttu-id="890f3-117">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="890f3-117">Optional.</span></span> <span data-ttu-id="890f3-118">Задает тип учетных данных, используемых для проверки сообщений, отправляемых с помощью однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="890f3-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="890f3-119">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="890f3-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="890f3-120">Атрибут credentialType</span><span class="sxs-lookup"><span data-stu-id="890f3-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="890f3-121">Значение</span><span class="sxs-lookup"><span data-stu-id="890f3-121">Value</span></span>|<span data-ttu-id="890f3-122">Описание</span><span class="sxs-lookup"><span data-stu-id="890f3-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="890f3-123">Сертификат</span><span class="sxs-lookup"><span data-stu-id="890f3-123">Certificate</span></span>|<span data-ttu-id="890f3-124">Для проверки подлинности однорангового транспорта канала необходим сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="890f3-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="890f3-125">Пароль</span><span class="sxs-lookup"><span data-stu-id="890f3-125">Password</span></span>|<span data-ttu-id="890f3-126">Для проверки подлинности однорангового транспорта канала необходим правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="890f3-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="890f3-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="890f3-127">Child Elements</span></span>  
 <span data-ttu-id="890f3-128">Нет</span><span class="sxs-lookup"><span data-stu-id="890f3-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="890f3-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="890f3-129">Parent Elements</span></span>  
  
|<span data-ttu-id="890f3-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="890f3-130">Element</span></span>|<span data-ttu-id="890f3-131">Описание</span><span class="sxs-lookup"><span data-stu-id="890f3-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="890f3-132">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="890f3-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="890f3-133">Определяет параметры безопасности для [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="890f3-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="890f3-134">См. также</span><span class="sxs-lookup"><span data-stu-id="890f3-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 [<span data-ttu-id="890f3-135">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="890f3-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="890f3-136">Привязки</span><span class="sxs-lookup"><span data-stu-id="890f3-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="890f3-137">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="890f3-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="890f3-138">Использование привязок для настройки службы Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="890f3-138">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="890f3-139">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="890f3-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
