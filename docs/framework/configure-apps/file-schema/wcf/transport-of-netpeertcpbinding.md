---
title: <transport> из <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 08be5d752f8422ebe6442b295195f21b16a274c0
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399315"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="38e4d-102">\<транспортное \<> из netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="38e4d-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="38e4d-103">Задает параметры безопасности на транспортном уровне при использовании [ \<> netPeerTcpBinding](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="38e4d-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
<span data-ttu-id="38e4d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="38e4d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="38e4d-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="38e4d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="38e4d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="38e4d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="38e4d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding >** ](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="38e4d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="38e4d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="38e4d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="38e4d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> безопасности**](security-of-netpeerbinding.md)</span><span class="sxs-lookup"><span data-stu-id="38e4d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netpeerbinding.md)</span></span>\
<span data-ttu-id="38e4d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> транспорта**</span><span class="sxs-lookup"><span data-stu-id="38e4d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38e4d-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38e4d-111">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38e4d-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="38e4d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="38e4d-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="38e4d-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38e4d-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="38e4d-114">Attributes</span></span>  
  
|<span data-ttu-id="38e4d-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="38e4d-115">Attribute</span></span>|<span data-ttu-id="38e4d-116">Описание</span><span class="sxs-lookup"><span data-stu-id="38e4d-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="38e4d-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="38e4d-117">credentialType</span></span>|<span data-ttu-id="38e4d-118">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="38e4d-118">Optional.</span></span> <span data-ttu-id="38e4d-119">Задает тип учетных данных, используемых для проверки сообщений, отправляемых с помощью однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="38e4d-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="38e4d-120">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="38e4d-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="38e4d-121">Атрибут credentialType</span><span class="sxs-lookup"><span data-stu-id="38e4d-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="38e4d-122">Значение</span><span class="sxs-lookup"><span data-stu-id="38e4d-122">Value</span></span>|<span data-ttu-id="38e4d-123">Описание</span><span class="sxs-lookup"><span data-stu-id="38e4d-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="38e4d-124">Сертификат</span><span class="sxs-lookup"><span data-stu-id="38e4d-124">Certificate</span></span>|<span data-ttu-id="38e4d-125">Для проверки подлинности однорангового транспорта канала необходим сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="38e4d-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="38e4d-126">Пароль</span><span class="sxs-lookup"><span data-stu-id="38e4d-126">Password</span></span>|<span data-ttu-id="38e4d-127">Для проверки подлинности однорангового транспорта канала необходим правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="38e4d-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38e4d-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="38e4d-128">Child Elements</span></span>  
 <span data-ttu-id="38e4d-129">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="38e4d-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="38e4d-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="38e4d-130">Parent Elements</span></span>  
  
|<span data-ttu-id="38e4d-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="38e4d-131">Element</span></span>|<span data-ttu-id="38e4d-132">Описание</span><span class="sxs-lookup"><span data-stu-id="38e4d-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38e4d-133">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="38e4d-133">\<security></span></span>](security-of-netpeerbinding.md)|<span data-ttu-id="38e4d-134">Определяет параметры безопасности для [ \<> netPeerTcpBinding](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="38e4d-134">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="38e4d-135">См. также</span><span class="sxs-lookup"><span data-stu-id="38e4d-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="38e4d-136">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="38e4d-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="38e4d-137">Привязки</span><span class="sxs-lookup"><span data-stu-id="38e4d-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="38e4d-138">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="38e4d-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="38e4d-139">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="38e4d-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="38e4d-140">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="38e4d-140">\<binding></span></span>](../../../misc/binding.md)
