---
title: <transport> из <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 49b31a889d192d190125214e89ba09305114eb7f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735974"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="f6455-102">\<> транспорта \<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="f6455-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="f6455-103">Задает параметры безопасности на транспортном уровне при использовании [\<netPeerTcpBinding >](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="f6455-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
<span data-ttu-id="f6455-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f6455-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f6455-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f6455-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f6455-106">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="f6455-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="f6455-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding >** ](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="f6455-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="f6455-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="f6455-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="f6455-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<security >** ](security-of-netpeerbinding.md)</span><span class="sxs-lookup"><span data-stu-id="f6455-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netpeerbinding.md)</span></span>\
<span data-ttu-id="f6455-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**транспорта >**</span><span class="sxs-lookup"><span data-stu-id="f6455-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6455-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6455-111">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6455-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f6455-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f6455-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f6455-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6455-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f6455-114">Attributes</span></span>  
  
|<span data-ttu-id="f6455-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f6455-115">Attribute</span></span>|<span data-ttu-id="f6455-116">Описание</span><span class="sxs-lookup"><span data-stu-id="f6455-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f6455-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="f6455-117">credentialType</span></span>|<span data-ttu-id="f6455-118">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="f6455-118">Optional.</span></span> <span data-ttu-id="f6455-119">Задает тип учетных данных, используемых для проверки сообщений, отправляемых с помощью однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="f6455-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="f6455-120">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="f6455-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="f6455-121">Атрибут credentialType</span><span class="sxs-lookup"><span data-stu-id="f6455-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="f6455-122">значения</span><span class="sxs-lookup"><span data-stu-id="f6455-122">Value</span></span>|<span data-ttu-id="f6455-123">Описание</span><span class="sxs-lookup"><span data-stu-id="f6455-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f6455-124">Сертификат</span><span class="sxs-lookup"><span data-stu-id="f6455-124">Certificate</span></span>|<span data-ttu-id="f6455-125">Для проверки подлинности однорангового транспорта канала необходим сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="f6455-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="f6455-126">Пароль</span><span class="sxs-lookup"><span data-stu-id="f6455-126">Password</span></span>|<span data-ttu-id="f6455-127">Для проверки подлинности однорангового транспорта канала необходим правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="f6455-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f6455-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f6455-128">Child Elements</span></span>  
 <span data-ttu-id="f6455-129">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="f6455-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f6455-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f6455-130">Parent Elements</span></span>  
  
|<span data-ttu-id="f6455-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="f6455-131">Element</span></span>|<span data-ttu-id="f6455-132">Описание</span><span class="sxs-lookup"><span data-stu-id="f6455-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6455-133">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="f6455-133">\<security></span></span>](security-of-netpeerbinding.md)|<span data-ttu-id="f6455-134">Определяет параметры безопасности для [\<> netPeerTcpBinding](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="f6455-134">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f6455-135">См. также</span><span class="sxs-lookup"><span data-stu-id="f6455-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="f6455-136">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="f6455-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f6455-137">Привязки</span><span class="sxs-lookup"><span data-stu-id="f6455-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f6455-138">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="f6455-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f6455-139">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="f6455-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f6455-140">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="f6455-140">\<binding></span></span>](bindings.md)
