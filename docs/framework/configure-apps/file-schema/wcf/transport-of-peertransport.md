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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 787d4569416203364e04898c6adcd57fb5a7aec8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="lttransportgt-of-ltpeertransportgt"></a><span data-ttu-id="d6f1e-102">&lt;transport&gt; для &lt;peerTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="d6f1e-102">&lt;transport&gt; of &lt;peerTransport&gt;</span></span>
<span data-ttu-id="d6f1e-103">Задает тип транспорта для безопасных сообщений, отправленных одноранговыми узлами, настроенными с помощью этой привязки.</span><span class="sxs-lookup"><span data-stu-id="d6f1e-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
 <span data-ttu-id="d6f1e-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="d6f1e-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d6f1e-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="d6f1e-105">\<bindings></span></span>  
<span data-ttu-id="d6f1e-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="d6f1e-106">\<customBinding></span></span>  
<span data-ttu-id="d6f1e-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="d6f1e-107">\<binding></span></span>  
<span data-ttu-id="d6f1e-108">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="d6f1e-108">\<peerTransport></span></span>  
<span data-ttu-id="d6f1e-109">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="d6f1e-109">\<security></span></span>  
<span data-ttu-id="d6f1e-110">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="d6f1e-110">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6f1e-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d6f1e-111">Syntax</span></span>  
  
```xml  
<security>  
   <transport credentialType="Certificate/Password" />  
</security>         
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6f1e-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d6f1e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d6f1e-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d6f1e-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6f1e-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d6f1e-114">Attributes</span></span>  
  
|<span data-ttu-id="d6f1e-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d6f1e-115">Attribute</span></span>|<span data-ttu-id="d6f1e-116">Описание</span><span class="sxs-lookup"><span data-stu-id="d6f1e-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d6f1e-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="d6f1e-117">credentialType</span></span>|<span data-ttu-id="d6f1e-118">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="d6f1e-118">Optional.</span></span> <span data-ttu-id="d6f1e-119">Задает тип учетных данных, используемых для проверки сообщений, отправляемых с помощью однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="d6f1e-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="d6f1e-120">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="d6f1e-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="d6f1e-121">Атрибут credentialType</span><span class="sxs-lookup"><span data-stu-id="d6f1e-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="d6f1e-122">Значение</span><span class="sxs-lookup"><span data-stu-id="d6f1e-122">Value</span></span>|<span data-ttu-id="d6f1e-123">Описание</span><span class="sxs-lookup"><span data-stu-id="d6f1e-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d6f1e-124">Сертификат</span><span class="sxs-lookup"><span data-stu-id="d6f1e-124">Certificate</span></span>|<span data-ttu-id="d6f1e-125">Для проверки подлинности однорангового транспорта канала необходим сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="d6f1e-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="d6f1e-126">Пароль</span><span class="sxs-lookup"><span data-stu-id="d6f1e-126">Password</span></span>|<span data-ttu-id="d6f1e-127">Для проверки подлинности однорангового транспорта канала необходим правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="d6f1e-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6f1e-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d6f1e-128">Child Elements</span></span>  
 <span data-ttu-id="d6f1e-129">Нет</span><span class="sxs-lookup"><span data-stu-id="d6f1e-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6f1e-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d6f1e-130">Parent Elements</span></span>  
  
|<span data-ttu-id="d6f1e-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="d6f1e-131">Element</span></span>|<span data-ttu-id="d6f1e-132">Описание</span><span class="sxs-lookup"><span data-stu-id="d6f1e-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6f1e-133">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="d6f1e-133">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="d6f1e-134">Определяет параметры безопасности для однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="d6f1e-134">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6f1e-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="d6f1e-135">Remarks</span></span>  
 <span data-ttu-id="d6f1e-136">Этот элемент имеет значение только в том случае, если атрибут режима [ \<безопасности >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) равно `Transport` или `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="d6f1e-136">This element is set only if the mode attribute of [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6f1e-137">См. также</span><span class="sxs-lookup"><span data-stu-id="d6f1e-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="d6f1e-138">Безопасность транспорта</span><span class="sxs-lookup"><span data-stu-id="d6f1e-138">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [<span data-ttu-id="d6f1e-139">Транспорты</span><span class="sxs-lookup"><span data-stu-id="d6f1e-139">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="d6f1e-140">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="d6f1e-140">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="d6f1e-141">Привязки</span><span class="sxs-lookup"><span data-stu-id="d6f1e-141">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="d6f1e-142">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="d6f1e-142">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="d6f1e-143">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="d6f1e-143">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="d6f1e-144">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="d6f1e-144">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
