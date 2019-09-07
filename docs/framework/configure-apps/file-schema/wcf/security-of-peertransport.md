---
title: <security> из <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 270ca844f586be256b6483653c868d1cc4396657
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399769"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="c9a4f-102">\<> безопасности > \<пиртранспорт</span><span class="sxs-lookup"><span data-stu-id="c9a4f-102">\<security> of \<peerTransport></span></span>
<span data-ttu-id="c9a4f-103">Содержит параметры безопасности, связанные с одноранговым каналом, включая используемый тип проверки подлинности и механизм безопасности, применяемый при транспортировке сообщений.</span><span class="sxs-lookup"><span data-stu-id="c9a4f-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
<span data-ttu-id="c9a4f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c9a4f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c9a4f-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c9a4f-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c9a4f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="c9a4f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="c9a4f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="c9a4f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="c9a4f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="c9a4f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="c9a4f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Пиртранспорт >** ](peertransport.md)</span><span class="sxs-lookup"><span data-stu-id="c9a4f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)</span></span>\
<span data-ttu-id="c9a4f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> безопасности**</span><span class="sxs-lookup"><span data-stu-id="c9a4f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9a4f-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9a4f-111">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9a4f-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c9a4f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c9a4f-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c9a4f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9a4f-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c9a4f-114">Attributes</span></span>  
  
|<span data-ttu-id="c9a4f-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c9a4f-115">Attribute</span></span>|<span data-ttu-id="c9a4f-116">Описание</span><span class="sxs-lookup"><span data-stu-id="c9a4f-116">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="c9a4f-117">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="c9a4f-117">Specifies the type of security to be applied.</span></span> <span data-ttu-id="c9a4f-118">Значение по умолчанию - Message.</span><span class="sxs-lookup"><span data-stu-id="c9a4f-118">The default value is Message.</span></span> <span data-ttu-id="c9a4f-119">Это атрибут типа <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="c9a4f-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="c9a4f-120">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="c9a4f-120">mode Attribute</span></span>  
  
|<span data-ttu-id="c9a4f-121">Значение</span><span class="sxs-lookup"><span data-stu-id="c9a4f-121">Value</span></span>|<span data-ttu-id="c9a4f-122">Описание</span><span class="sxs-lookup"><span data-stu-id="c9a4f-122">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="c9a4f-123">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="c9a4f-123">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="c9a4f-124">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c9a4f-124">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="c9a4f-125">Механизм безопасности SOAP обеспечивает целостность, конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="c9a4f-125">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="c9a4f-126">HTTPS обеспечивает конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="c9a4f-126">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="c9a4f-127">Сообщения SOAP предоставляют различные типы учетных данных.</span><span class="sxs-lookup"><span data-stu-id="c9a4f-127">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c9a4f-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c9a4f-128">Child Elements</span></span>  
  
|<span data-ttu-id="c9a4f-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="c9a4f-129">Element</span></span>|<span data-ttu-id="c9a4f-130">Описание</span><span class="sxs-lookup"><span data-stu-id="c9a4f-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9a4f-131">\<> транспорта</span><span class="sxs-lookup"><span data-stu-id="c9a4f-131">\<transport></span></span>](transport-of-peertransport.md)|<span data-ttu-id="c9a4f-132">Определяет одноранговый транспорт для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="c9a4f-132">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="c9a4f-133">Этот элемент имеет атрибут `clientCredentialType`, который задает учетные данные для использования при взаимодействии со службой.</span><span class="sxs-lookup"><span data-stu-id="c9a4f-133">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="c9a4f-134">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="c9a4f-134">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="c9a4f-135">Это элемент типа <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="c9a4f-135">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c9a4f-136">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c9a4f-136">Parent Elements</span></span>  
  
|<span data-ttu-id="c9a4f-137">Элемент</span><span class="sxs-lookup"><span data-stu-id="c9a4f-137">Element</span></span>|<span data-ttu-id="c9a4f-138">Описание</span><span class="sxs-lookup"><span data-stu-id="c9a4f-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9a4f-139">\<Пиртранспорт ></span><span class="sxs-lookup"><span data-stu-id="c9a4f-139">\<peerTransport></span></span>](peertransport.md)|<span data-ttu-id="c9a4f-140">Определяет одноранговый транспорт для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="c9a4f-140">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c9a4f-141">См. также</span><span class="sxs-lookup"><span data-stu-id="c9a4f-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c9a4f-142">Безопасность транспорта</span><span class="sxs-lookup"><span data-stu-id="c9a4f-142">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="c9a4f-143">Транспорты</span><span class="sxs-lookup"><span data-stu-id="c9a4f-143">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="c9a4f-144">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="c9a4f-144">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="c9a4f-145">Привязки</span><span class="sxs-lookup"><span data-stu-id="c9a4f-145">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c9a4f-146">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="c9a4f-146">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c9a4f-147">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="c9a4f-147">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c9a4f-148">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="c9a4f-148">\<customBinding></span></span>](custombinding.md)
