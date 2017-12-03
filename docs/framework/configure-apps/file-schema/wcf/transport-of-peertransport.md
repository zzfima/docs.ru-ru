---
title: "&lt;transport&gt; для &lt;peerTransport&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 69b62699f5db0ab11fac3cc4d1ba4e2aa022934d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="lttransportgt-of-ltpeertransportgt"></a><span data-ttu-id="8e5a3-102">&lt;transport&gt; для &lt;peerTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="8e5a3-102">&lt;transport&gt; of &lt;peerTransport&gt;</span></span>
<span data-ttu-id="8e5a3-103">Задает тип транспорта для безопасных сообщений, отправленных одноранговыми узлами, настроенными с помощью этой привязки.</span><span class="sxs-lookup"><span data-stu-id="8e5a3-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
 <span data-ttu-id="8e5a3-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8e5a3-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8e5a3-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="8e5a3-105">\<bindings></span></span>  
<span data-ttu-id="8e5a3-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8e5a3-106">\<customBinding></span></span>  
<span data-ttu-id="8e5a3-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="8e5a3-107">\<binding></span></span>  
<span data-ttu-id="8e5a3-108">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="8e5a3-108">\<peerTransport></span></span>  
<span data-ttu-id="8e5a3-109">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="8e5a3-109">\<security></span></span>  
<span data-ttu-id="8e5a3-110">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="8e5a3-110">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e5a3-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e5a3-111">Syntax</span></span>  
  
```xml  
<security>  
   <transport credentialType="Certificate/Password" />  
</security>         
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e5a3-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8e5a3-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8e5a3-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8e5a3-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e5a3-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8e5a3-114">Attributes</span></span>  
  
|<span data-ttu-id="8e5a3-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8e5a3-115">Attribute</span></span>|<span data-ttu-id="8e5a3-116">Описание</span><span class="sxs-lookup"><span data-stu-id="8e5a3-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e5a3-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="8e5a3-117">credentialType</span></span>|<span data-ttu-id="8e5a3-118">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="8e5a3-118">Optional.</span></span> <span data-ttu-id="8e5a3-119">Задает тип учетных данных, используемых для проверки сообщений, отправляемых с помощью однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="8e5a3-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="8e5a3-120">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="8e5a3-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="8e5a3-121">Атрибут credentialType</span><span class="sxs-lookup"><span data-stu-id="8e5a3-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="8e5a3-122">Значение</span><span class="sxs-lookup"><span data-stu-id="8e5a3-122">Value</span></span>|<span data-ttu-id="8e5a3-123">Описание</span><span class="sxs-lookup"><span data-stu-id="8e5a3-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8e5a3-124">Сертификат</span><span class="sxs-lookup"><span data-stu-id="8e5a3-124">Certificate</span></span>|<span data-ttu-id="8e5a3-125">Для проверки подлинности однорангового транспорта канала необходим сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="8e5a3-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="8e5a3-126">Пароль</span><span class="sxs-lookup"><span data-stu-id="8e5a3-126">Password</span></span>|<span data-ttu-id="8e5a3-127">Для проверки подлинности однорангового транспорта канала необходим правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="8e5a3-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e5a3-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8e5a3-128">Child Elements</span></span>  
 <span data-ttu-id="8e5a3-129">Нет</span><span class="sxs-lookup"><span data-stu-id="8e5a3-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e5a3-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8e5a3-130">Parent Elements</span></span>  
  
|<span data-ttu-id="8e5a3-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="8e5a3-131">Element</span></span>|<span data-ttu-id="8e5a3-132">Описание</span><span class="sxs-lookup"><span data-stu-id="8e5a3-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e5a3-133">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="8e5a3-133">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="8e5a3-134">Определяет параметры безопасности для однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="8e5a3-134">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e5a3-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="8e5a3-135">Remarks</span></span>  
 <span data-ttu-id="8e5a3-136">Этот элемент имеет значение только в том случае, если атрибут режима [ \<безопасности >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) равно `Transport` или `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="8e5a3-136">This element is set only if the mode attribute of [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e5a3-137">См. также</span><span class="sxs-lookup"><span data-stu-id="8e5a3-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="8e5a3-138">Безопасность транспорта</span><span class="sxs-lookup"><span data-stu-id="8e5a3-138">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [<span data-ttu-id="8e5a3-139">Транспорты</span><span class="sxs-lookup"><span data-stu-id="8e5a3-139">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="8e5a3-140">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="8e5a3-140">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="8e5a3-141">Привязки</span><span class="sxs-lookup"><span data-stu-id="8e5a3-141">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="8e5a3-142">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="8e5a3-142">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="8e5a3-143">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="8e5a3-143">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="8e5a3-144">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8e5a3-144">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
