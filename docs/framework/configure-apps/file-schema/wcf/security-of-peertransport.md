---
title: <security> из <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: bdd3b236c9bae198f8027c4ca0c0fa5b70d30342
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936643"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="0aae6-102">\<> безопасности > \<пиртранспорт</span><span class="sxs-lookup"><span data-stu-id="0aae6-102">\<security> of \<peerTransport></span></span>
<span data-ttu-id="0aae6-103">Содержит параметры безопасности, связанные с одноранговым каналом, включая используемый тип проверки подлинности и механизм безопасности, применяемый при транспортировке сообщений.</span><span class="sxs-lookup"><span data-stu-id="0aae6-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="0aae6-104">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="0aae6-104">\<system.serviceModel></span></span>  
<span data-ttu-id="0aae6-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="0aae6-105">\<bindings></span></span>  
<span data-ttu-id="0aae6-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="0aae6-106">\<customBinding></span></span>  
<span data-ttu-id="0aae6-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="0aae6-107">\<binding></span></span>  
<span data-ttu-id="0aae6-108">\<Пиртранспорт ></span><span class="sxs-lookup"><span data-stu-id="0aae6-108">\<peerTransport></span></span>  
<span data-ttu-id="0aae6-109">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="0aae6-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0aae6-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0aae6-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0aae6-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0aae6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0aae6-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0aae6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0aae6-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0aae6-113">Attributes</span></span>  
  
|<span data-ttu-id="0aae6-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0aae6-114">Attribute</span></span>|<span data-ttu-id="0aae6-115">Описание</span><span class="sxs-lookup"><span data-stu-id="0aae6-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="0aae6-116">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="0aae6-116">Specifies the type of security to be applied.</span></span> <span data-ttu-id="0aae6-117">Значение по умолчанию - Message.</span><span class="sxs-lookup"><span data-stu-id="0aae6-117">The default value is Message.</span></span> <span data-ttu-id="0aae6-118">Это атрибут типа <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="0aae6-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="0aae6-119">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="0aae6-119">mode Attribute</span></span>  
  
|<span data-ttu-id="0aae6-120">Значение</span><span class="sxs-lookup"><span data-stu-id="0aae6-120">Value</span></span>|<span data-ttu-id="0aae6-121">Описание</span><span class="sxs-lookup"><span data-stu-id="0aae6-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="0aae6-122">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="0aae6-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="0aae6-123">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="0aae6-123">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="0aae6-124">Механизм безопасности SOAP обеспечивает целостность, конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="0aae6-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="0aae6-125">HTTPS обеспечивает конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="0aae6-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="0aae6-126">Сообщения SOAP предоставляют различные типы учетных данных.</span><span class="sxs-lookup"><span data-stu-id="0aae6-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0aae6-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0aae6-127">Child Elements</span></span>  
  
|<span data-ttu-id="0aae6-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="0aae6-128">Element</span></span>|<span data-ttu-id="0aae6-129">Описание</span><span class="sxs-lookup"><span data-stu-id="0aae6-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0aae6-130">\<> транспорта</span><span class="sxs-lookup"><span data-stu-id="0aae6-130">\<transport></span></span>](transport-of-peertransport.md)|<span data-ttu-id="0aae6-131">Определяет одноранговый транспорт для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="0aae6-131">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="0aae6-132">Этот элемент имеет атрибут `clientCredentialType`, который задает учетные данные для использования при взаимодействии со службой.</span><span class="sxs-lookup"><span data-stu-id="0aae6-132">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="0aae6-133">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="0aae6-133">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="0aae6-134">Это элемент типа <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="0aae6-134">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0aae6-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0aae6-135">Parent Elements</span></span>  
  
|<span data-ttu-id="0aae6-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="0aae6-136">Element</span></span>|<span data-ttu-id="0aae6-137">Описание</span><span class="sxs-lookup"><span data-stu-id="0aae6-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0aae6-138">\<Пиртранспорт ></span><span class="sxs-lookup"><span data-stu-id="0aae6-138">\<peerTransport></span></span>](peertransport.md)|<span data-ttu-id="0aae6-139">Определяет одноранговый транспорт для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="0aae6-139">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0aae6-140">См. также</span><span class="sxs-lookup"><span data-stu-id="0aae6-140">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="0aae6-141">Безопасность транспорта</span><span class="sxs-lookup"><span data-stu-id="0aae6-141">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="0aae6-142">Транспорты</span><span class="sxs-lookup"><span data-stu-id="0aae6-142">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="0aae6-143">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="0aae6-143">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="0aae6-144">Привязки</span><span class="sxs-lookup"><span data-stu-id="0aae6-144">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0aae6-145">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="0aae6-145">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0aae6-146">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="0aae6-146">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="0aae6-147">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="0aae6-147">\<customBinding></span></span>](custombinding.md)
