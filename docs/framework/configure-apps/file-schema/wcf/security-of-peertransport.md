---
title: '&lt;security&gt; для &lt;peerTransport&gt;'
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 8b0b8c5f230e8e93c07e13212201896010429af0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585384"
---
# <a name="ltsecuritygt-of-ltpeertransportgt"></a><span data-ttu-id="bb29e-102">&lt;security&gt; для &lt;peerTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="bb29e-102">&lt;security&gt; of &lt;peerTransport&gt;</span></span>
<span data-ttu-id="bb29e-103">Содержит параметры безопасности, связанные с одноранговым каналом, включая используемый тип проверки подлинности и механизм безопасности, применяемый при транспортировке сообщений.</span><span class="sxs-lookup"><span data-stu-id="bb29e-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="bb29e-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="bb29e-104">\<system.serviceModel></span></span>  
<span data-ttu-id="bb29e-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="bb29e-105">\<bindings></span></span>  
<span data-ttu-id="bb29e-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="bb29e-106">\<customBinding></span></span>  
<span data-ttu-id="bb29e-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="bb29e-107">\<binding></span></span>  
<span data-ttu-id="bb29e-108">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="bb29e-108">\<peerTransport></span></span>  
<span data-ttu-id="bb29e-109">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="bb29e-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb29e-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb29e-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb29e-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bb29e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bb29e-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bb29e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb29e-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bb29e-113">Attributes</span></span>  
  
|<span data-ttu-id="bb29e-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bb29e-114">Attribute</span></span>|<span data-ttu-id="bb29e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="bb29e-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="bb29e-116">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="bb29e-116">Specifies the type of security to be applied.</span></span> <span data-ttu-id="bb29e-117">Значение по умолчанию - Message.</span><span class="sxs-lookup"><span data-stu-id="bb29e-117">The default value is Message.</span></span> <span data-ttu-id="bb29e-118">Это атрибут типа <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="bb29e-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="bb29e-119">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="bb29e-119">mode Attribute</span></span>  
  
|<span data-ttu-id="bb29e-120">Значение</span><span class="sxs-lookup"><span data-stu-id="bb29e-120">Value</span></span>|<span data-ttu-id="bb29e-121">Описание</span><span class="sxs-lookup"><span data-stu-id="bb29e-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="bb29e-122">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="bb29e-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="bb29e-123">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="bb29e-123">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="bb29e-124">Механизм безопасности SOAP обеспечивает целостность, конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="bb29e-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="bb29e-125">HTTPS обеспечивает конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="bb29e-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="bb29e-126">Сообщения SOAP предоставляют различные типы учетных данных.</span><span class="sxs-lookup"><span data-stu-id="bb29e-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb29e-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bb29e-127">Child Elements</span></span>  
  
|<span data-ttu-id="bb29e-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="bb29e-128">Element</span></span>|<span data-ttu-id="bb29e-129">Описание:</span><span class="sxs-lookup"><span data-stu-id="bb29e-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bb29e-130">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="bb29e-130">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|<span data-ttu-id="bb29e-131">Определяет одноранговый транспорт для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="bb29e-131">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="bb29e-132">Этот элемент имеет атрибут `clientCredentialType`, который задает учетные данные для использования при взаимодействии со службой.</span><span class="sxs-lookup"><span data-stu-id="bb29e-132">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="bb29e-133">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="bb29e-133">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="bb29e-134">Это элемент типа <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="bb29e-134">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bb29e-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bb29e-135">Parent Elements</span></span>  
  
|<span data-ttu-id="bb29e-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="bb29e-136">Element</span></span>|<span data-ttu-id="bb29e-137">Описание:</span><span class="sxs-lookup"><span data-stu-id="bb29e-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bb29e-138">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="bb29e-138">\<peerTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|<span data-ttu-id="bb29e-139">Определяет одноранговый транспорт для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="bb29e-139">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bb29e-140">См. также</span><span class="sxs-lookup"><span data-stu-id="bb29e-140">See also</span></span>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="bb29e-141">Безопасность транспорта</span><span class="sxs-lookup"><span data-stu-id="bb29e-141">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)
- [<span data-ttu-id="bb29e-142">Транспорты</span><span class="sxs-lookup"><span data-stu-id="bb29e-142">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="bb29e-143">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="bb29e-143">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="bb29e-144">Привязки</span><span class="sxs-lookup"><span data-stu-id="bb29e-144">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="bb29e-145">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="bb29e-145">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="bb29e-146">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="bb29e-146">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="bb29e-147">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="bb29e-147">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
