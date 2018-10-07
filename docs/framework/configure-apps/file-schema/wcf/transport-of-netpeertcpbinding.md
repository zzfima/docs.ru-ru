---
title: '&lt;transport&gt; для &lt;netPeerTcpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 62ba3b27b10afe182623f3be0f6738940e194579
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2018
ms.locfileid: "48836619"
---
# <a name="lttransportgt-of-ltnetpeertcpbindinggt"></a><span data-ttu-id="cde47-102">&lt;transport&gt; для &lt;netPeerTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="cde47-102">&lt;transport&gt; of &lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="cde47-103">Указывает параметры безопасности уровня транспорта при использовании [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="cde47-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="cde47-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="cde47-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cde47-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="cde47-105">\<bindings></span></span>  
<span data-ttu-id="cde47-106">\<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="cde47-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="cde47-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="cde47-107">\<binding></span></span>  
<span data-ttu-id="cde47-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="cde47-108">\<security></span></span>  
<span data-ttu-id="cde47-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="cde47-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cde47-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cde47-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cde47-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cde47-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cde47-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cde47-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cde47-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cde47-113">Attributes</span></span>  
  
|<span data-ttu-id="cde47-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cde47-114">Attribute</span></span>|<span data-ttu-id="cde47-115">Описание</span><span class="sxs-lookup"><span data-stu-id="cde47-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cde47-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="cde47-116">credentialType</span></span>|<span data-ttu-id="cde47-117">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="cde47-117">Optional.</span></span> <span data-ttu-id="cde47-118">Задает тип учетных данных, используемых для проверки сообщений, отправляемых с помощью однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="cde47-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="cde47-119">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="cde47-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="cde47-120">Атрибут credentialType</span><span class="sxs-lookup"><span data-stu-id="cde47-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="cde47-121">Значение</span><span class="sxs-lookup"><span data-stu-id="cde47-121">Value</span></span>|<span data-ttu-id="cde47-122">Описание</span><span class="sxs-lookup"><span data-stu-id="cde47-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cde47-123">Сертификат</span><span class="sxs-lookup"><span data-stu-id="cde47-123">Certificate</span></span>|<span data-ttu-id="cde47-124">Для проверки подлинности однорангового транспорта канала необходим сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="cde47-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="cde47-125">Пароль</span><span class="sxs-lookup"><span data-stu-id="cde47-125">Password</span></span>|<span data-ttu-id="cde47-126">Для проверки подлинности однорангового транспорта канала необходим правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="cde47-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cde47-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cde47-127">Child Elements</span></span>  
 <span data-ttu-id="cde47-128">Нет</span><span class="sxs-lookup"><span data-stu-id="cde47-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cde47-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cde47-129">Parent Elements</span></span>  
  
|<span data-ttu-id="cde47-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="cde47-130">Element</span></span>|<span data-ttu-id="cde47-131">Описание:</span><span class="sxs-lookup"><span data-stu-id="cde47-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cde47-132">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="cde47-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="cde47-133">Определяет параметры безопасности для [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="cde47-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cde47-134">См. также</span><span class="sxs-lookup"><span data-stu-id="cde47-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 [<span data-ttu-id="cde47-135">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="cde47-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="cde47-136">Привязки</span><span class="sxs-lookup"><span data-stu-id="cde47-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="cde47-137">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="cde47-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="cde47-138">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="cde47-138">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="cde47-139">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="cde47-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
