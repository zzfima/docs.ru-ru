---
title: <transport> из <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 5dbc55db25c0c49d72ec2cd8dd1041a3f8705d8e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940634"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="71f33-102">\<транспортное \<> из пиртранспорт ></span><span class="sxs-lookup"><span data-stu-id="71f33-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="71f33-103">Задает тип транспорта для безопасных сообщений, отправленных одноранговыми узлами, настроенными с помощью этой привязки.</span><span class="sxs-lookup"><span data-stu-id="71f33-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
 <span data-ttu-id="71f33-104">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="71f33-104">\<system.serviceModel></span></span>  
<span data-ttu-id="71f33-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="71f33-105">\<bindings></span></span>  
<span data-ttu-id="71f33-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="71f33-106">\<customBinding></span></span>  
<span data-ttu-id="71f33-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="71f33-107">\<binding></span></span>  
<span data-ttu-id="71f33-108">\<Пиртранспорт ></span><span class="sxs-lookup"><span data-stu-id="71f33-108">\<peerTransport></span></span>  
<span data-ttu-id="71f33-109">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="71f33-109">\<security></span></span>  
<span data-ttu-id="71f33-110">\<> транспорта</span><span class="sxs-lookup"><span data-stu-id="71f33-110">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71f33-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71f33-111">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71f33-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="71f33-112">Attributes and Elements</span></span>  
 <span data-ttu-id="71f33-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="71f33-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71f33-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="71f33-114">Attributes</span></span>  
  
|<span data-ttu-id="71f33-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="71f33-115">Attribute</span></span>|<span data-ttu-id="71f33-116">Описание</span><span class="sxs-lookup"><span data-stu-id="71f33-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="71f33-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="71f33-117">credentialType</span></span>|<span data-ttu-id="71f33-118">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="71f33-118">Optional.</span></span> <span data-ttu-id="71f33-119">Задает тип учетных данных, используемых для проверки сообщений, отправляемых с помощью однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="71f33-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="71f33-120">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="71f33-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="71f33-121">Атрибут credentialType</span><span class="sxs-lookup"><span data-stu-id="71f33-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="71f33-122">Значение</span><span class="sxs-lookup"><span data-stu-id="71f33-122">Value</span></span>|<span data-ttu-id="71f33-123">Описание</span><span class="sxs-lookup"><span data-stu-id="71f33-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="71f33-124">Сертификат</span><span class="sxs-lookup"><span data-stu-id="71f33-124">Certificate</span></span>|<span data-ttu-id="71f33-125">Для проверки подлинности однорангового транспорта канала необходим сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="71f33-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="71f33-126">Пароль</span><span class="sxs-lookup"><span data-stu-id="71f33-126">Password</span></span>|<span data-ttu-id="71f33-127">Для проверки подлинности однорангового транспорта канала необходим правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="71f33-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71f33-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="71f33-128">Child Elements</span></span>  
 <span data-ttu-id="71f33-129">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="71f33-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="71f33-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="71f33-130">Parent Elements</span></span>  
  
|<span data-ttu-id="71f33-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="71f33-131">Element</span></span>|<span data-ttu-id="71f33-132">Описание</span><span class="sxs-lookup"><span data-stu-id="71f33-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71f33-133">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="71f33-133">\<security></span></span>](security-of-peertransport.md)|<span data-ttu-id="71f33-134">Определяет параметры безопасности для однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="71f33-134">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71f33-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="71f33-135">Remarks</span></span>  
 <span data-ttu-id="71f33-136">Этот элемент задается только в том случае, если атрибут `Transport` `TransportWithMessageCredential` [ \<Mode > безопасности](security-of-peertransport.md) имеет значение или.</span><span class="sxs-lookup"><span data-stu-id="71f33-136">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71f33-137">См. также</span><span class="sxs-lookup"><span data-stu-id="71f33-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="71f33-138">Безопасность транспорта</span><span class="sxs-lookup"><span data-stu-id="71f33-138">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="71f33-139">Транспорты</span><span class="sxs-lookup"><span data-stu-id="71f33-139">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="71f33-140">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="71f33-140">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="71f33-141">Привязки</span><span class="sxs-lookup"><span data-stu-id="71f33-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="71f33-142">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="71f33-142">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="71f33-143">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="71f33-143">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="71f33-144">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="71f33-144">\<customBinding></span></span>](custombinding.md)
