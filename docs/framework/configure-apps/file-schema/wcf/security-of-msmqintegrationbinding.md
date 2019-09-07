---
title: <security> из <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: e4f10ab994429c6cbb690caef38114b8340e6839
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399867"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="57555-102">\<> безопасности > \<MsmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="57555-102">\<security> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="57555-103">Определяет параметры безопасности транспорта для канала интеграции очереди сообщений (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="57555-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
<span data-ttu-id="57555-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="57555-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="57555-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="57555-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="57555-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="57555-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="57555-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<msmqIntegrationBinding >** ](msmqintegrationbinding.md)</span><span class="sxs-lookup"><span data-stu-id="57555-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)</span></span>\
<span data-ttu-id="57555-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="57555-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="57555-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> безопасности**</span><span class="sxs-lookup"><span data-stu-id="57555-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57555-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57555-110">Syntax</span></span>  
  
```xml  
<msmqIntegrationBinding>
  <binding>
    <security mode="None/Transport">
      <transport msmqAuthenticationMode="None/Windows/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
      <message algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               defaultProtectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</msmqIntegrationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57555-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="57555-111">Attributes and Elements</span></span>  
 <span data-ttu-id="57555-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="57555-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57555-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="57555-113">Attributes</span></span>  
  
|<span data-ttu-id="57555-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="57555-114">Attribute</span></span>|<span data-ttu-id="57555-115">Описание</span><span class="sxs-lookup"><span data-stu-id="57555-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="57555-116">режим</span><span class="sxs-lookup"><span data-stu-id="57555-116">mode</span></span>|<span data-ttu-id="57555-117">Задает тип системы безопасности, отвечающей за целостность, конфиденциальность и проверку подлинности при использовании канала интеграции очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="57555-117">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="57555-118">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="57555-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="57555-119">None Это отключает безопасность.</span><span class="sxs-lookup"><span data-stu-id="57555-119">-   None: This disables security.</span></span><br /><span data-ttu-id="57555-120">Перемещения Защита и проверка подлинности предоставляются транспортом.</span><span class="sxs-lookup"><span data-stu-id="57555-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="57555-121">Это значение связано с безопасностью сообщений между двумя диспетчерами очереди.</span><span class="sxs-lookup"><span data-stu-id="57555-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="57555-122">Между приложением и диспетчером очереди безопасность сообщений не обеспечивается.</span><span class="sxs-lookup"><span data-stu-id="57555-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="57555-123">Существующие Msmq-приложения функционально равноценны такому режиму безопасности.</span><span class="sxs-lookup"><span data-stu-id="57555-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="57555-124">Значение по умолчанию — `Transport`.</span><span class="sxs-lookup"><span data-stu-id="57555-124">The default value is `Transport`.</span></span> <span data-ttu-id="57555-125">Это атрибут типа <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="57555-125">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57555-126">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="57555-126">Child Elements</span></span>  
  
|<span data-ttu-id="57555-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="57555-127">Element</span></span>|<span data-ttu-id="57555-128">Описание</span><span class="sxs-lookup"><span data-stu-id="57555-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="57555-129">\<> транспорта</span><span class="sxs-lookup"><span data-stu-id="57555-129">\<transport></span></span>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="57555-130">Определяет параметры безопасности для транспорта интеграции очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="57555-130">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="57555-131">Это элемент типа <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="57555-131">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="57555-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="57555-132">Parent Elements</span></span>  
  
|<span data-ttu-id="57555-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="57555-133">Element</span></span>|<span data-ttu-id="57555-134">Описание</span><span class="sxs-lookup"><span data-stu-id="57555-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="57555-135">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="57555-135">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="57555-136">[ Элемент\<Binding > MsmqIntegrationBinding](msmqintegrationbinding.md).</span><span class="sxs-lookup"><span data-stu-id="57555-136">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="57555-137">См. также</span><span class="sxs-lookup"><span data-stu-id="57555-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="57555-138">Очереди в WCF</span><span class="sxs-lookup"><span data-stu-id="57555-138">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="57555-139">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="57555-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="57555-140">Привязки</span><span class="sxs-lookup"><span data-stu-id="57555-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="57555-141">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="57555-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="57555-142">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="57555-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="57555-143">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="57555-143">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="57555-144">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="57555-144">\<msmqIntegrationBinding></span></span>](msmqintegrationbinding.md)
