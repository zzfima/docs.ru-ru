---
title: '&lt;security&gt; для &lt;netPeerBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
author: BrucePerlerMS
ms.openlocfilehash: 1d7ffaf72e34b700f4702b2e531afbf7e842de09
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2018
ms.locfileid: "48844570"
---
# <a name="ltsecuritygt-of-ltnetpeerbindinggt"></a><span data-ttu-id="2e272-102">&lt;security&gt; для &lt;netPeerBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="2e272-102">&lt;security&gt; of &lt;netPeerBinding&gt;</span></span>
<span data-ttu-id="2e272-103">Определяет параметры безопасности [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), включая тип проверки подлинности, используемые и безопасности, используемый для передачи сообщений.</span><span class="sxs-lookup"><span data-stu-id="2e272-103">Defines the security settings of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="2e272-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2e272-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2e272-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="2e272-105">\<bindings></span></span>  
<span data-ttu-id="2e272-106">\<netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="2e272-106">\<netPeerBinding></span></span>  
<span data-ttu-id="2e272-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="2e272-107">\<binding></span></span>  
<span data-ttu-id="2e272-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="2e272-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e272-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e272-109">Syntax</span></span>  
  
```xml  
<netPeerBinding>  
    <binding>  
        <security mode="Message/None/Transport//TransportWithMessageCredential">  
            <transport credentialType="Certificate/Password" />  
        </security>  
    </binding>  
</netPeerBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e272-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2e272-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2e272-111">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2e272-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e272-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2e272-112">Attributes</span></span>  
  
|<span data-ttu-id="2e272-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2e272-113">Attribute</span></span>|<span data-ttu-id="2e272-114">Описание</span><span class="sxs-lookup"><span data-stu-id="2e272-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2e272-115">режим</span><span class="sxs-lookup"><span data-stu-id="2e272-115">mode</span></span>|<span data-ttu-id="2e272-116">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="2e272-116">Optional.</span></span> <span data-ttu-id="2e272-117">Указывает тип безопасности, используемый одноранговыми узлами, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="2e272-117">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="2e272-118">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="2e272-118">The default value is `Message`.</span></span> <span data-ttu-id="2e272-119">Это атрибут типа <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="2e272-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="2e272-120">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="2e272-120">mode Attribute</span></span>  
  
|<span data-ttu-id="2e272-121">Значение</span><span class="sxs-lookup"><span data-stu-id="2e272-121">Value</span></span>|<span data-ttu-id="2e272-122">Описание</span><span class="sxs-lookup"><span data-stu-id="2e272-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2e272-123">Сообщение</span><span class="sxs-lookup"><span data-stu-id="2e272-123">Message</span></span>|<span data-ttu-id="2e272-124">Механизм безопасности SOAP обеспечивает целостность, конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="2e272-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="2e272-125">Нет</span><span class="sxs-lookup"><span data-stu-id="2e272-125">None</span></span>|<span data-ttu-id="2e272-126">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="2e272-126">Security is disabled.</span></span>|  
|<span data-ttu-id="2e272-127">Transport</span><span class="sxs-lookup"><span data-stu-id="2e272-127">Transport</span></span>|<span data-ttu-id="2e272-128">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2e272-128">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="2e272-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="2e272-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="2e272-130">HTTPS обеспечивает конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="2e272-130">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="2e272-131">Сообщения SOAP предоставляют различные типы учетных данных.</span><span class="sxs-lookup"><span data-stu-id="2e272-131">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e272-132">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2e272-132">Child Elements</span></span>  
  
|<span data-ttu-id="2e272-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="2e272-133">Element</span></span>|<span data-ttu-id="2e272-134">Описание:</span><span class="sxs-lookup"><span data-stu-id="2e272-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e272-135">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="2e272-135">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netpeertcpbinding.md)|<span data-ttu-id="2e272-136">Определяет тип транспорта для безопасных сообщений, отправленных одноранговыми узлами, настроенными с помощью этой привязки.</span><span class="sxs-lookup"><span data-stu-id="2e272-136">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="2e272-137">Это элемент типа <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="2e272-137">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2e272-138">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2e272-138">Parent Elements</span></span>  
  
|<span data-ttu-id="2e272-139">Элемент</span><span class="sxs-lookup"><span data-stu-id="2e272-139">Element</span></span>|<span data-ttu-id="2e272-140">Описание:</span><span class="sxs-lookup"><span data-stu-id="2e272-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e272-141">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="2e272-141">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="2e272-142">Определяет все возможности привязки [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="2e272-142">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e272-143">Примечания</span><span class="sxs-lookup"><span data-stu-id="2e272-143">Remarks</span></span>  
 <span data-ttu-id="2e272-144">Безопасность может определяться как на уровне сообщений, так и на уровне транспорта.</span><span class="sxs-lookup"><span data-stu-id="2e272-144">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e272-145">См. также</span><span class="sxs-lookup"><span data-stu-id="2e272-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 [<span data-ttu-id="2e272-146">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="2e272-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="2e272-147">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="2e272-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="2e272-148">Привязки</span><span class="sxs-lookup"><span data-stu-id="2e272-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="2e272-149">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="2e272-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="2e272-150">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="2e272-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="2e272-151">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="2e272-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
