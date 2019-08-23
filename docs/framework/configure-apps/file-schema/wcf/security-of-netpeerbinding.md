---
title: <security> из <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: be5ebacec466caf8d8a77bf552f42da1861e77a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936629"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="af127-102">\<> безопасности > \<нетпирбиндинг</span><span class="sxs-lookup"><span data-stu-id="af127-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="af127-103">Определяет параметры [ \<безопасности > netPeerTcpBinding](netpeertcpbinding.md), включая тип используемой проверки подлинности и безопасность, используемую для транспорта сообщений.</span><span class="sxs-lookup"><span data-stu-id="af127-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="af127-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="af127-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="af127-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="af127-105">\<bindings></span></span>  
<span data-ttu-id="af127-106">\<Нетпирбиндинг ></span><span class="sxs-lookup"><span data-stu-id="af127-106">\<netPeerBinding></span></span>  
<span data-ttu-id="af127-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="af127-107">\<binding></span></span>  
<span data-ttu-id="af127-108">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="af127-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af127-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="af127-109">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af127-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="af127-110">Attributes and Elements</span></span>  
 <span data-ttu-id="af127-111">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="af127-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af127-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="af127-112">Attributes</span></span>  
  
|<span data-ttu-id="af127-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="af127-113">Attribute</span></span>|<span data-ttu-id="af127-114">Описание</span><span class="sxs-lookup"><span data-stu-id="af127-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="af127-115">режим</span><span class="sxs-lookup"><span data-stu-id="af127-115">mode</span></span>|<span data-ttu-id="af127-116">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="af127-116">Optional.</span></span> <span data-ttu-id="af127-117">Указывает тип безопасности, используемый одноранговыми узлами, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="af127-117">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="af127-118">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="af127-118">The default value is `Message`.</span></span> <span data-ttu-id="af127-119">Это атрибут типа <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="af127-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="af127-120">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="af127-120">mode Attribute</span></span>  
  
|<span data-ttu-id="af127-121">Значение</span><span class="sxs-lookup"><span data-stu-id="af127-121">Value</span></span>|<span data-ttu-id="af127-122">Описание</span><span class="sxs-lookup"><span data-stu-id="af127-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="af127-123">Сообщение</span><span class="sxs-lookup"><span data-stu-id="af127-123">Message</span></span>|<span data-ttu-id="af127-124">Механизм безопасности SOAP обеспечивает целостность, конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="af127-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="af127-125">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="af127-125">None</span></span>|<span data-ttu-id="af127-126">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="af127-126">Security is disabled.</span></span>|  
|<span data-ttu-id="af127-127">Transport</span><span class="sxs-lookup"><span data-stu-id="af127-127">Transport</span></span>|<span data-ttu-id="af127-128">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="af127-128">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="af127-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="af127-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="af127-130">HTTPS обеспечивает конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="af127-130">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="af127-131">Сообщения SOAP предоставляют различные типы учетных данных.</span><span class="sxs-lookup"><span data-stu-id="af127-131">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af127-132">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="af127-132">Child Elements</span></span>  
  
|<span data-ttu-id="af127-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="af127-133">Element</span></span>|<span data-ttu-id="af127-134">Описание</span><span class="sxs-lookup"><span data-stu-id="af127-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af127-135">\<> транспорта</span><span class="sxs-lookup"><span data-stu-id="af127-135">\<transport></span></span>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="af127-136">Определяет тип транспорта для безопасных сообщений, отправленных одноранговыми узлами, настроенными с помощью этой привязки.</span><span class="sxs-lookup"><span data-stu-id="af127-136">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="af127-137">Это элемент типа <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="af127-137">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="af127-138">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="af127-138">Parent Elements</span></span>  
  
|<span data-ttu-id="af127-139">Элемент</span><span class="sxs-lookup"><span data-stu-id="af127-139">Element</span></span>|<span data-ttu-id="af127-140">Описание</span><span class="sxs-lookup"><span data-stu-id="af127-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af127-141">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="af127-141">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="af127-142">Определяет все возможности [ \<привязки > netPeerTcpBinding](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="af127-142">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af127-143">Примечания</span><span class="sxs-lookup"><span data-stu-id="af127-143">Remarks</span></span>  
 <span data-ttu-id="af127-144">Безопасность может определяться как на уровне сообщений, так и на уровне транспорта.</span><span class="sxs-lookup"><span data-stu-id="af127-144">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af127-145">См. также</span><span class="sxs-lookup"><span data-stu-id="af127-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="af127-146">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="af127-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="af127-147">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="af127-147">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="af127-148">Привязки</span><span class="sxs-lookup"><span data-stu-id="af127-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="af127-149">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="af127-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="af127-150">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="af127-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="af127-151">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="af127-151">\<binding></span></span>](../../../misc/binding.md)
