---
title: <security> из <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: 88aa2898472c20c9e52cfd5830c0e41e8ea9ba21
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399807"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="2b951-102">\<> безопасности > \<нетпирбиндинг</span><span class="sxs-lookup"><span data-stu-id="2b951-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="2b951-103">Определяет параметры [ \<безопасности > netPeerTcpBinding](netpeertcpbinding.md), включая тип используемой проверки подлинности и безопасность, используемую для транспорта сообщений.</span><span class="sxs-lookup"><span data-stu-id="2b951-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
<span data-ttu-id="2b951-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2b951-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2b951-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2b951-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2b951-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="2b951-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="2b951-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding >** ](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2b951-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="2b951-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="2b951-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="2b951-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> безопасности**</span><span class="sxs-lookup"><span data-stu-id="2b951-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b951-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b951-110">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b951-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2b951-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2b951-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2b951-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b951-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2b951-113">Attributes</span></span>  
  
|<span data-ttu-id="2b951-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2b951-114">Attribute</span></span>|<span data-ttu-id="2b951-115">Описание</span><span class="sxs-lookup"><span data-stu-id="2b951-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2b951-116">режим</span><span class="sxs-lookup"><span data-stu-id="2b951-116">mode</span></span>|<span data-ttu-id="2b951-117">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="2b951-117">Optional.</span></span> <span data-ttu-id="2b951-118">Указывает тип безопасности, используемый одноранговыми узлами, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="2b951-118">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="2b951-119">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="2b951-119">The default value is `Message`.</span></span> <span data-ttu-id="2b951-120">Это атрибут типа <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="2b951-120">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="2b951-121">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="2b951-121">mode Attribute</span></span>  
  
|<span data-ttu-id="2b951-122">Значение</span><span class="sxs-lookup"><span data-stu-id="2b951-122">Value</span></span>|<span data-ttu-id="2b951-123">Описание</span><span class="sxs-lookup"><span data-stu-id="2b951-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2b951-124">Сообщение</span><span class="sxs-lookup"><span data-stu-id="2b951-124">Message</span></span>|<span data-ttu-id="2b951-125">Механизм безопасности SOAP обеспечивает целостность, конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="2b951-125">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="2b951-126">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="2b951-126">None</span></span>|<span data-ttu-id="2b951-127">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="2b951-127">Security is disabled.</span></span>|  
|<span data-ttu-id="2b951-128">Transport</span><span class="sxs-lookup"><span data-stu-id="2b951-128">Transport</span></span>|<span data-ttu-id="2b951-129">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2b951-129">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="2b951-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="2b951-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="2b951-131">HTTPS обеспечивает конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="2b951-131">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="2b951-132">Сообщения SOAP предоставляют различные типы учетных данных.</span><span class="sxs-lookup"><span data-stu-id="2b951-132">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2b951-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2b951-133">Child Elements</span></span>  
  
|<span data-ttu-id="2b951-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="2b951-134">Element</span></span>|<span data-ttu-id="2b951-135">Описание</span><span class="sxs-lookup"><span data-stu-id="2b951-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b951-136">\<> транспорта</span><span class="sxs-lookup"><span data-stu-id="2b951-136">\<transport></span></span>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="2b951-137">Определяет тип транспорта для безопасных сообщений, отправленных одноранговыми узлами, настроенными с помощью этой привязки.</span><span class="sxs-lookup"><span data-stu-id="2b951-137">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="2b951-138">Это элемент типа <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="2b951-138">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2b951-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2b951-139">Parent Elements</span></span>  
  
|<span data-ttu-id="2b951-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="2b951-140">Element</span></span>|<span data-ttu-id="2b951-141">Описание</span><span class="sxs-lookup"><span data-stu-id="2b951-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b951-142">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="2b951-142">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="2b951-143">Определяет все возможности [ \<привязки > netPeerTcpBinding](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="2b951-143">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b951-144">Примечания</span><span class="sxs-lookup"><span data-stu-id="2b951-144">Remarks</span></span>  
 <span data-ttu-id="2b951-145">Безопасность может определяться как на уровне сообщений, так и на уровне транспорта.</span><span class="sxs-lookup"><span data-stu-id="2b951-145">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b951-146">См. также</span><span class="sxs-lookup"><span data-stu-id="2b951-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="2b951-147">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="2b951-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="2b951-148">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="2b951-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="2b951-149">Привязки</span><span class="sxs-lookup"><span data-stu-id="2b951-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2b951-150">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="2b951-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2b951-151">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="2b951-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="2b951-152">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="2b951-152">\<binding></span></span>](../../../misc/binding.md)
