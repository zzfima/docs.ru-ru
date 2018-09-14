---
title: '&lt;transport&gt; для &lt;netPeerTcpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 2b89ae090d24ff6aad1aae1b39a0a18961bd2537
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "45519225"
---
# <a name="lttransportgt-of-ltnetpeertcpbindinggt"></a><span data-ttu-id="192d3-102">&lt;transport&gt; для &lt;netPeerTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="192d3-102">&lt;transport&gt; of &lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="192d3-103">Указывает параметры безопасности уровня транспорта при использовании [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="192d3-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="192d3-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="192d3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="192d3-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="192d3-105">\<bindings></span></span>  
<span data-ttu-id="192d3-106">\<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="192d3-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="192d3-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="192d3-107">\<binding></span></span>  
<span data-ttu-id="192d3-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="192d3-108">\<security></span></span>  
<span data-ttu-id="192d3-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="192d3-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="192d3-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="192d3-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="192d3-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="192d3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="192d3-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="192d3-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="192d3-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="192d3-113">Attributes</span></span>  
  
|<span data-ttu-id="192d3-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="192d3-114">Attribute</span></span>|<span data-ttu-id="192d3-115">Описание</span><span class="sxs-lookup"><span data-stu-id="192d3-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="192d3-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="192d3-116">credentialType</span></span>|<span data-ttu-id="192d3-117">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="192d3-117">Optional.</span></span> <span data-ttu-id="192d3-118">Задает тип учетных данных, используемых для проверки сообщений, отправляемых с помощью однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="192d3-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="192d3-119">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="192d3-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="192d3-120">Атрибут credentialType</span><span class="sxs-lookup"><span data-stu-id="192d3-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="192d3-121">Значение</span><span class="sxs-lookup"><span data-stu-id="192d3-121">Value</span></span>|<span data-ttu-id="192d3-122">Описание</span><span class="sxs-lookup"><span data-stu-id="192d3-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="192d3-123">Сертификат</span><span class="sxs-lookup"><span data-stu-id="192d3-123">Certificate</span></span>|<span data-ttu-id="192d3-124">Для проверки подлинности однорангового транспорта канала необходим сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="192d3-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="192d3-125">Пароль</span><span class="sxs-lookup"><span data-stu-id="192d3-125">Password</span></span>|<span data-ttu-id="192d3-126">Для проверки подлинности однорангового транспорта канала необходим правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="192d3-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="192d3-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="192d3-127">Child Elements</span></span>  
 <span data-ttu-id="192d3-128">Нет</span><span class="sxs-lookup"><span data-stu-id="192d3-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="192d3-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="192d3-129">Parent Elements</span></span>  
  
|<span data-ttu-id="192d3-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="192d3-130">Element</span></span>|<span data-ttu-id="192d3-131">Описание</span><span class="sxs-lookup"><span data-stu-id="192d3-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="192d3-132">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="192d3-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="192d3-133">Определяет параметры безопасности для [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="192d3-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="192d3-134">См. также</span><span class="sxs-lookup"><span data-stu-id="192d3-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 [<span data-ttu-id="192d3-135">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="192d3-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="192d3-136">Привязки</span><span class="sxs-lookup"><span data-stu-id="192d3-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="192d3-137">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="192d3-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="192d3-138">Использование привязок для настройки службы Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="192d3-138">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="192d3-139">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="192d3-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
