---
title: <transport> из <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 3b2c7716727f58abb81bf4d58b13189ac170cf7c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399292"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="188de-102">\<транспортное \<> из пиртранспорт ></span><span class="sxs-lookup"><span data-stu-id="188de-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="188de-103">Задает тип транспорта для безопасных сообщений, отправленных одноранговыми узлами, настроенными с помощью этой привязки.</span><span class="sxs-lookup"><span data-stu-id="188de-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
<span data-ttu-id="188de-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="188de-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="188de-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="188de-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="188de-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="188de-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="188de-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="188de-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="188de-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="188de-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="188de-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Пиртранспорт >** ](peertransport.md)</span><span class="sxs-lookup"><span data-stu-id="188de-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)</span></span>\
<span data-ttu-id="188de-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> безопасности**](security-of-peertransport.md)</span><span class="sxs-lookup"><span data-stu-id="188de-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-peertransport.md)</span></span>\
<span data-ttu-id="188de-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> транспорта**</span><span class="sxs-lookup"><span data-stu-id="188de-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="188de-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="188de-112">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="188de-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="188de-113">Attributes and Elements</span></span>  
 <span data-ttu-id="188de-114">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="188de-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="188de-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="188de-115">Attributes</span></span>  
  
|<span data-ttu-id="188de-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="188de-116">Attribute</span></span>|<span data-ttu-id="188de-117">Описание</span><span class="sxs-lookup"><span data-stu-id="188de-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="188de-118">credentialType</span><span class="sxs-lookup"><span data-stu-id="188de-118">credentialType</span></span>|<span data-ttu-id="188de-119">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="188de-119">Optional.</span></span> <span data-ttu-id="188de-120">Задает тип учетных данных, используемых для проверки сообщений, отправляемых с помощью однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="188de-120">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="188de-121">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="188de-121">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="188de-122">Атрибут credentialType</span><span class="sxs-lookup"><span data-stu-id="188de-122">credentialType Attribute</span></span>  
  
|<span data-ttu-id="188de-123">Значение</span><span class="sxs-lookup"><span data-stu-id="188de-123">Value</span></span>|<span data-ttu-id="188de-124">Описание</span><span class="sxs-lookup"><span data-stu-id="188de-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="188de-125">Сертификат</span><span class="sxs-lookup"><span data-stu-id="188de-125">Certificate</span></span>|<span data-ttu-id="188de-126">Для проверки подлинности однорангового транспорта канала необходим сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="188de-126">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="188de-127">Пароль</span><span class="sxs-lookup"><span data-stu-id="188de-127">Password</span></span>|<span data-ttu-id="188de-128">Для проверки подлинности однорангового транспорта канала необходим правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="188de-128">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="188de-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="188de-129">Child Elements</span></span>  
 <span data-ttu-id="188de-130">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="188de-130">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="188de-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="188de-131">Parent Elements</span></span>  
  
|<span data-ttu-id="188de-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="188de-132">Element</span></span>|<span data-ttu-id="188de-133">Описание</span><span class="sxs-lookup"><span data-stu-id="188de-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="188de-134">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="188de-134">\<security></span></span>](security-of-peertransport.md)|<span data-ttu-id="188de-135">Определяет параметры безопасности для однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="188de-135">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="188de-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="188de-136">Remarks</span></span>  
 <span data-ttu-id="188de-137">Этот элемент задается только в том случае, если атрибут `Transport` `TransportWithMessageCredential` [ \<Mode > безопасности](security-of-peertransport.md) имеет значение или.</span><span class="sxs-lookup"><span data-stu-id="188de-137">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="188de-138">См. также</span><span class="sxs-lookup"><span data-stu-id="188de-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="188de-139">Безопасность транспорта</span><span class="sxs-lookup"><span data-stu-id="188de-139">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="188de-140">Транспорты</span><span class="sxs-lookup"><span data-stu-id="188de-140">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="188de-141">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="188de-141">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="188de-142">Привязки</span><span class="sxs-lookup"><span data-stu-id="188de-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="188de-143">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="188de-143">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="188de-144">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="188de-144">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="188de-145">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="188de-145">\<customBinding></span></span>](custombinding.md)
