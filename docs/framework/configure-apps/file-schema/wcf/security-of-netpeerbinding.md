---
title: <security> из <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: 3d1ac85073c44f683fe0c054737c5ec7ed1cbf52
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738657"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="58d37-102">\<> безопасности \<Нетпирбиндинг ></span><span class="sxs-lookup"><span data-stu-id="58d37-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="58d37-103">Определяет параметры безопасности [\<netPeerTcpBinding >](netpeertcpbinding.md), включая тип используемой проверки подлинности и безопасность, используемую для транспорта сообщений.</span><span class="sxs-lookup"><span data-stu-id="58d37-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
<span data-ttu-id="58d37-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="58d37-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="58d37-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="58d37-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="58d37-106">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="58d37-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="58d37-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding >** ](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="58d37-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="58d37-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="58d37-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="58d37-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<security >**</span><span class="sxs-lookup"><span data-stu-id="58d37-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58d37-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="58d37-110">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58d37-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="58d37-111">Attributes and Elements</span></span>  
 <span data-ttu-id="58d37-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="58d37-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58d37-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="58d37-113">Attributes</span></span>  
  
|<span data-ttu-id="58d37-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="58d37-114">Attribute</span></span>|<span data-ttu-id="58d37-115">Описание</span><span class="sxs-lookup"><span data-stu-id="58d37-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="58d37-116">режим</span><span class="sxs-lookup"><span data-stu-id="58d37-116">mode</span></span>|<span data-ttu-id="58d37-117">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="58d37-117">Optional.</span></span> <span data-ttu-id="58d37-118">Указывает тип безопасности, используемый одноранговыми узлами, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="58d37-118">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="58d37-119">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="58d37-119">The default value is `Message`.</span></span> <span data-ttu-id="58d37-120">Это атрибут типа <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="58d37-120">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="58d37-121">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="58d37-121">mode Attribute</span></span>  
  
|<span data-ttu-id="58d37-122">значения</span><span class="sxs-lookup"><span data-stu-id="58d37-122">Value</span></span>|<span data-ttu-id="58d37-123">Описание</span><span class="sxs-lookup"><span data-stu-id="58d37-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="58d37-124">Сообщение</span><span class="sxs-lookup"><span data-stu-id="58d37-124">Message</span></span>|<span data-ttu-id="58d37-125">Механизм безопасности SOAP обеспечивает целостность, конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="58d37-125">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="58d37-126">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="58d37-126">None</span></span>|<span data-ttu-id="58d37-127">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="58d37-127">Security is disabled.</span></span>|  
|<span data-ttu-id="58d37-128">Transport</span><span class="sxs-lookup"><span data-stu-id="58d37-128">Transport</span></span>|<span data-ttu-id="58d37-129">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="58d37-129">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="58d37-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="58d37-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="58d37-131">HTTPS обеспечивает конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="58d37-131">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="58d37-132">Сообщения SOAP предоставляют различные типы учетных данных.</span><span class="sxs-lookup"><span data-stu-id="58d37-132">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58d37-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="58d37-133">Child Elements</span></span>  
  
|<span data-ttu-id="58d37-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="58d37-134">Element</span></span>|<span data-ttu-id="58d37-135">Описание</span><span class="sxs-lookup"><span data-stu-id="58d37-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58d37-136">\<> транспорта</span><span class="sxs-lookup"><span data-stu-id="58d37-136">\<transport></span></span>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="58d37-137">Определяет тип транспорта для безопасных сообщений, отправленных одноранговыми узлами, настроенными с помощью этой привязки.</span><span class="sxs-lookup"><span data-stu-id="58d37-137">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="58d37-138">Это элемент типа <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="58d37-138">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="58d37-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="58d37-139">Parent Elements</span></span>  
  
|<span data-ttu-id="58d37-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="58d37-140">Element</span></span>|<span data-ttu-id="58d37-141">Описание</span><span class="sxs-lookup"><span data-stu-id="58d37-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58d37-142">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="58d37-142">\<binding></span></span>](bindings.md)|<span data-ttu-id="58d37-143">Определяет все возможности привязки [\<netPeerTcpBinding >](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="58d37-143">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58d37-144">Заметки</span><span class="sxs-lookup"><span data-stu-id="58d37-144">Remarks</span></span>  
 <span data-ttu-id="58d37-145">Безопасность может определяться как на уровне сообщений, так и на уровне транспорта.</span><span class="sxs-lookup"><span data-stu-id="58d37-145">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58d37-146">См. также</span><span class="sxs-lookup"><span data-stu-id="58d37-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="58d37-147">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="58d37-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="58d37-148">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="58d37-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="58d37-149">Привязки</span><span class="sxs-lookup"><span data-stu-id="58d37-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="58d37-150">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="58d37-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="58d37-151">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="58d37-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="58d37-152">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="58d37-152">\<binding></span></span>](bindings.md)
