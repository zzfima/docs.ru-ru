---
title: <security> из <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 1aff79bf5867a3a1ebe05e3f812475dac4b413e9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116867"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="44343-102">\<Безопасность > из \<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="44343-102">\<security> of \<peerTransport></span></span>
<span data-ttu-id="44343-103">Содержит параметры безопасности, связанные с одноранговым каналом, включая используемый тип проверки подлинности и механизм безопасности, применяемый при транспортировке сообщений.</span><span class="sxs-lookup"><span data-stu-id="44343-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="44343-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="44343-104">\<system.serviceModel></span></span>  
<span data-ttu-id="44343-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="44343-105">\<bindings></span></span>  
<span data-ttu-id="44343-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="44343-106">\<customBinding></span></span>  
<span data-ttu-id="44343-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="44343-107">\<binding></span></span>  
<span data-ttu-id="44343-108">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="44343-108">\<peerTransport></span></span>  
<span data-ttu-id="44343-109">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="44343-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44343-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="44343-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44343-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="44343-111">Attributes and Elements</span></span>  
 <span data-ttu-id="44343-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="44343-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44343-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="44343-113">Attributes</span></span>  
  
|<span data-ttu-id="44343-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="44343-114">Attribute</span></span>|<span data-ttu-id="44343-115">Описание</span><span class="sxs-lookup"><span data-stu-id="44343-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="44343-116">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="44343-116">Specifies the type of security to be applied.</span></span> <span data-ttu-id="44343-117">Значение по умолчанию - Message.</span><span class="sxs-lookup"><span data-stu-id="44343-117">The default value is Message.</span></span> <span data-ttu-id="44343-118">Это атрибут типа <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="44343-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="44343-119">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="44343-119">mode Attribute</span></span>  
  
|<span data-ttu-id="44343-120">Значение</span><span class="sxs-lookup"><span data-stu-id="44343-120">Value</span></span>|<span data-ttu-id="44343-121">Описание</span><span class="sxs-lookup"><span data-stu-id="44343-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="44343-122">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="44343-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="44343-123">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="44343-123">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="44343-124">Механизм безопасности SOAP обеспечивает целостность, конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="44343-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="44343-125">HTTPS обеспечивает конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="44343-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="44343-126">Сообщения SOAP предоставляют различные типы учетных данных.</span><span class="sxs-lookup"><span data-stu-id="44343-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44343-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="44343-127">Child Elements</span></span>  
  
|<span data-ttu-id="44343-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="44343-128">Element</span></span>|<span data-ttu-id="44343-129">Описание</span><span class="sxs-lookup"><span data-stu-id="44343-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44343-130">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="44343-130">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|<span data-ttu-id="44343-131">Определяет одноранговый транспорт для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="44343-131">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="44343-132">Этот элемент имеет атрибут `clientCredentialType`, который задает учетные данные для использования при взаимодействии со службой.</span><span class="sxs-lookup"><span data-stu-id="44343-132">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="44343-133">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="44343-133">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="44343-134">Это элемент типа <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="44343-134">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="44343-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="44343-135">Parent Elements</span></span>  
  
|<span data-ttu-id="44343-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="44343-136">Element</span></span>|<span data-ttu-id="44343-137">Описание</span><span class="sxs-lookup"><span data-stu-id="44343-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44343-138">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="44343-138">\<peerTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|<span data-ttu-id="44343-139">Определяет одноранговый транспорт для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="44343-139">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44343-140">См. также</span><span class="sxs-lookup"><span data-stu-id="44343-140">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="44343-141">Безопасность транспорта</span><span class="sxs-lookup"><span data-stu-id="44343-141">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)
- [<span data-ttu-id="44343-142">Транспорты</span><span class="sxs-lookup"><span data-stu-id="44343-142">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="44343-143">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="44343-143">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="44343-144">Привязки</span><span class="sxs-lookup"><span data-stu-id="44343-144">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="44343-145">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="44343-145">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="44343-146">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="44343-146">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="44343-147">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="44343-147">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
