---
title: <transport> из <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 9b6f548515afbba5068659bd5c6f7f2b33f80cda
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076007"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="c0b04-102">\<Транспорт > из \<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="c0b04-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="c0b04-103">Задает тип транспорта для безопасных сообщений, отправленных одноранговыми узлами, настроенными с помощью этой привязки.</span><span class="sxs-lookup"><span data-stu-id="c0b04-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
 <span data-ttu-id="c0b04-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c0b04-104">\<system.serviceModel></span></span>  
<span data-ttu-id="c0b04-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="c0b04-105">\<bindings></span></span>  
<span data-ttu-id="c0b04-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="c0b04-106">\<customBinding></span></span>  
<span data-ttu-id="c0b04-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="c0b04-107">\<binding></span></span>  
<span data-ttu-id="c0b04-108">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="c0b04-108">\<peerTransport></span></span>  
<span data-ttu-id="c0b04-109">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="c0b04-109">\<security></span></span>  
<span data-ttu-id="c0b04-110">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="c0b04-110">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0b04-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0b04-111">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0b04-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c0b04-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c0b04-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c0b04-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0b04-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c0b04-114">Attributes</span></span>  
  
|<span data-ttu-id="c0b04-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c0b04-115">Attribute</span></span>|<span data-ttu-id="c0b04-116">Описание</span><span class="sxs-lookup"><span data-stu-id="c0b04-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c0b04-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="c0b04-117">credentialType</span></span>|<span data-ttu-id="c0b04-118">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="c0b04-118">Optional.</span></span> <span data-ttu-id="c0b04-119">Задает тип учетных данных, используемых для проверки сообщений, отправляемых с помощью однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="c0b04-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="c0b04-120">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="c0b04-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="c0b04-121">Атрибут credentialType</span><span class="sxs-lookup"><span data-stu-id="c0b04-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="c0b04-122">Значение</span><span class="sxs-lookup"><span data-stu-id="c0b04-122">Value</span></span>|<span data-ttu-id="c0b04-123">Описание</span><span class="sxs-lookup"><span data-stu-id="c0b04-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c0b04-124">Сертификат</span><span class="sxs-lookup"><span data-stu-id="c0b04-124">Certificate</span></span>|<span data-ttu-id="c0b04-125">Для проверки подлинности однорангового транспорта канала необходим сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="c0b04-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="c0b04-126">Пароль</span><span class="sxs-lookup"><span data-stu-id="c0b04-126">Password</span></span>|<span data-ttu-id="c0b04-127">Для проверки подлинности однорангового транспорта канала необходим правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="c0b04-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0b04-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c0b04-128">Child Elements</span></span>  
 <span data-ttu-id="c0b04-129">Нет</span><span class="sxs-lookup"><span data-stu-id="c0b04-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0b04-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c0b04-130">Parent Elements</span></span>  
  
|<span data-ttu-id="c0b04-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="c0b04-131">Element</span></span>|<span data-ttu-id="c0b04-132">Описание</span><span class="sxs-lookup"><span data-stu-id="c0b04-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0b04-133">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="c0b04-133">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="c0b04-134">Определяет параметры безопасности для однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="c0b04-134">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0b04-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="c0b04-135">Remarks</span></span>  
 <span data-ttu-id="c0b04-136">Этот элемент имеет значение только в том случае, если атрибуту режима [ \<безопасности >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) присваивается `Transport` или `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="c0b04-136">This element is set only if the mode attribute of [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0b04-137">См. также</span><span class="sxs-lookup"><span data-stu-id="c0b04-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c0b04-138">Безопасность транспорта</span><span class="sxs-lookup"><span data-stu-id="c0b04-138">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)
- [<span data-ttu-id="c0b04-139">Транспорты</span><span class="sxs-lookup"><span data-stu-id="c0b04-139">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="c0b04-140">Выбор транспортов</span><span class="sxs-lookup"><span data-stu-id="c0b04-140">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="c0b04-141">Привязки</span><span class="sxs-lookup"><span data-stu-id="c0b04-141">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="c0b04-142">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="c0b04-142">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c0b04-143">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="c0b04-143">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c0b04-144">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="c0b04-144">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
