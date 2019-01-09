---
title: '&lt;security&gt; для &lt;peerTransport&gt;'
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 901a1d0b29fa6ea7d9e520b379dc7c7ff1d1e522
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151960"
---
# <a name="ltsecuritygt-of-ltpeertransportgt"></a><span data-ttu-id="3d6f3-102">&lt;security&gt; для &lt;peerTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="3d6f3-102">&lt;security&gt; of &lt;peerTransport&gt;</span></span>
<span data-ttu-id="3d6f3-103">Содержит параметры безопасности, связанные с одноранговым каналом, включая используемый тип проверки подлинности и механизм безопасности, применяемый при транспортировке сообщений.</span><span class="sxs-lookup"><span data-stu-id="3d6f3-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="3d6f3-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="3d6f3-104">\<system.serviceModel></span></span>  
<span data-ttu-id="3d6f3-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="3d6f3-105">\<bindings></span></span>  
<span data-ttu-id="3d6f3-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="3d6f3-106">\<customBinding></span></span>  
<span data-ttu-id="3d6f3-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="3d6f3-107">\<binding></span></span>  
<span data-ttu-id="3d6f3-108">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="3d6f3-108">\<peerTransport></span></span>  
<span data-ttu-id="3d6f3-109">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="3d6f3-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d6f3-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d6f3-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d6f3-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3d6f3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3d6f3-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3d6f3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d6f3-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3d6f3-113">Attributes</span></span>  
  
|<span data-ttu-id="3d6f3-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3d6f3-114">Attribute</span></span>|<span data-ttu-id="3d6f3-115">Описание</span><span class="sxs-lookup"><span data-stu-id="3d6f3-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="3d6f3-116">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="3d6f3-116">Specifies the type of security to be applied.</span></span> <span data-ttu-id="3d6f3-117">Значение по умолчанию - Message.</span><span class="sxs-lookup"><span data-stu-id="3d6f3-117">The default value is Message.</span></span> <span data-ttu-id="3d6f3-118">Это атрибут типа <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="3d6f3-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="3d6f3-119">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="3d6f3-119">mode Attribute</span></span>  
  
|<span data-ttu-id="3d6f3-120">Значение</span><span class="sxs-lookup"><span data-stu-id="3d6f3-120">Value</span></span>|<span data-ttu-id="3d6f3-121">Описание</span><span class="sxs-lookup"><span data-stu-id="3d6f3-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="3d6f3-122">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="3d6f3-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="3d6f3-123">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3d6f3-123">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="3d6f3-124">Механизм безопасности SOAP обеспечивает целостность, конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="3d6f3-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="3d6f3-125">HTTPS обеспечивает конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="3d6f3-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="3d6f3-126">Сообщения SOAP предоставляют различные типы учетных данных.</span><span class="sxs-lookup"><span data-stu-id="3d6f3-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3d6f3-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3d6f3-127">Child Elements</span></span>  
  
|<span data-ttu-id="3d6f3-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="3d6f3-128">Element</span></span>|<span data-ttu-id="3d6f3-129">Описание</span><span class="sxs-lookup"><span data-stu-id="3d6f3-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d6f3-130">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="3d6f3-130">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|<span data-ttu-id="3d6f3-131">Определяет одноранговый транспорт для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="3d6f3-131">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="3d6f3-132">Этот элемент имеет атрибут `clientCredentialType`, который задает учетные данные для использования при взаимодействии со службой.</span><span class="sxs-lookup"><span data-stu-id="3d6f3-132">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="3d6f3-133">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="3d6f3-133">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="3d6f3-134">Это элемент типа <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="3d6f3-134">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3d6f3-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3d6f3-135">Parent Elements</span></span>  
  
|<span data-ttu-id="3d6f3-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="3d6f3-136">Element</span></span>|<span data-ttu-id="3d6f3-137">Описание</span><span class="sxs-lookup"><span data-stu-id="3d6f3-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d6f3-138">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="3d6f3-138">\<peerTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|<span data-ttu-id="3d6f3-139">Определяет одноранговый транспорт для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="3d6f3-139">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d6f3-140">См. также</span><span class="sxs-lookup"><span data-stu-id="3d6f3-140">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="3d6f3-141">Безопасность транспорта</span><span class="sxs-lookup"><span data-stu-id="3d6f3-141">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [<span data-ttu-id="3d6f3-142">Транспорты</span><span class="sxs-lookup"><span data-stu-id="3d6f3-142">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="3d6f3-143">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="3d6f3-143">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="3d6f3-144">Привязки</span><span class="sxs-lookup"><span data-stu-id="3d6f3-144">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="3d6f3-145">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="3d6f3-145">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="3d6f3-146">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="3d6f3-146">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="3d6f3-147">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="3d6f3-147">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
