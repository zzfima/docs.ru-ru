---
title: "&lt;security&gt; для &lt;netPeerBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
caps.latest.revision: "14"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: b9228ccbed2b0f612986d59b72c920d57f38f69a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltnetpeerbindinggt"></a><span data-ttu-id="7d3b3-102">&lt;security&gt; для &lt;netPeerBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="7d3b3-102">&lt;security&gt; of &lt;netPeerBinding&gt;</span></span>
<span data-ttu-id="7d3b3-103">Определяет параметры безопасности [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), включая тип проверки подлинности, используемый и безопасности, используемый для передачи сообщений.</span><span class="sxs-lookup"><span data-stu-id="7d3b3-103">Defines the security settings of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="7d3b3-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7d3b3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7d3b3-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="7d3b3-105">\<bindings></span></span>  
<span data-ttu-id="7d3b3-106">\<netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="7d3b3-106">\<netPeerBinding></span></span>  
<span data-ttu-id="7d3b3-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="7d3b3-107">\<binding></span></span>  
<span data-ttu-id="7d3b3-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="7d3b3-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d3b3-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d3b3-109">Syntax</span></span>  
  
```xml  
<netPeerBinding>  
    <binding>  
        <security mode="Message/None/Transport//TransportWithMessageCredential">  
            <transport credentialType="Certificate/Password" />  
        </security>  
    </binding>  
</netPeerBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d3b3-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7d3b3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7d3b3-111">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7d3b3-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d3b3-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7d3b3-112">Attributes</span></span>  
  
|<span data-ttu-id="7d3b3-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7d3b3-113">Attribute</span></span>|<span data-ttu-id="7d3b3-114">Описание</span><span class="sxs-lookup"><span data-stu-id="7d3b3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7d3b3-115">режим</span><span class="sxs-lookup"><span data-stu-id="7d3b3-115">mode</span></span>|<span data-ttu-id="7d3b3-116">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="7d3b3-116">Optional.</span></span> <span data-ttu-id="7d3b3-117">Указывает тип безопасности, используемый одноранговыми узлами, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="7d3b3-117">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="7d3b3-118">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="7d3b3-118">The default value is `Message`.</span></span> <span data-ttu-id="7d3b3-119">Это атрибут типа <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="7d3b3-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="7d3b3-120">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="7d3b3-120">mode Attribute</span></span>  
  
|<span data-ttu-id="7d3b3-121">Значение</span><span class="sxs-lookup"><span data-stu-id="7d3b3-121">Value</span></span>|<span data-ttu-id="7d3b3-122">Описание</span><span class="sxs-lookup"><span data-stu-id="7d3b3-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7d3b3-123">Сообщение</span><span class="sxs-lookup"><span data-stu-id="7d3b3-123">Message</span></span>|<span data-ttu-id="7d3b3-124">Механизм безопасности SOAP обеспечивает целостность, конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="7d3b3-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="7d3b3-125">Нет</span><span class="sxs-lookup"><span data-stu-id="7d3b3-125">None</span></span>|<span data-ttu-id="7d3b3-126">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="7d3b3-126">Security is disabled.</span></span>|  
|<span data-ttu-id="7d3b3-127">Transport</span><span class="sxs-lookup"><span data-stu-id="7d3b3-127">Transport</span></span>|<span data-ttu-id="7d3b3-128">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7d3b3-128">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="7d3b3-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="7d3b3-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="7d3b3-130">HTTPS обеспечивает конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="7d3b3-130">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="7d3b3-131">Сообщения SOAP предоставляют различные типы учетных данных.</span><span class="sxs-lookup"><span data-stu-id="7d3b3-131">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d3b3-132">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7d3b3-132">Child Elements</span></span>  
  
|<span data-ttu-id="7d3b3-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="7d3b3-133">Element</span></span>|<span data-ttu-id="7d3b3-134">Описание:</span><span class="sxs-lookup"><span data-stu-id="7d3b3-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d3b3-135">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="7d3b3-135">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netpeertcpbinding.md)|<span data-ttu-id="7d3b3-136">Определяет тип транспорта для безопасных сообщений, отправленных одноранговыми узлами, настроенными с помощью этой привязки.</span><span class="sxs-lookup"><span data-stu-id="7d3b3-136">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="7d3b3-137">Это элемент типа <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="7d3b3-137">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7d3b3-138">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7d3b3-138">Parent Elements</span></span>  
  
|<span data-ttu-id="7d3b3-139">Элемент</span><span class="sxs-lookup"><span data-stu-id="7d3b3-139">Element</span></span>|<span data-ttu-id="7d3b3-140">Описание:</span><span class="sxs-lookup"><span data-stu-id="7d3b3-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d3b3-141">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="7d3b3-141">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="7d3b3-142">Определяет все возможности [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="7d3b3-142">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d3b3-143">Примечания</span><span class="sxs-lookup"><span data-stu-id="7d3b3-143">Remarks</span></span>  
 <span data-ttu-id="7d3b3-144">Безопасность может определяться как на уровне сообщений, так и на уровне транспорта.</span><span class="sxs-lookup"><span data-stu-id="7d3b3-144">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d3b3-145">См. также</span><span class="sxs-lookup"><span data-stu-id="7d3b3-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 [<span data-ttu-id="7d3b3-146">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="7d3b3-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="7d3b3-147">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="7d3b3-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="7d3b3-148">Привязки</span><span class="sxs-lookup"><span data-stu-id="7d3b3-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="7d3b3-149">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="7d3b3-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="7d3b3-150">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="7d3b3-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="7d3b3-151">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="7d3b3-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
