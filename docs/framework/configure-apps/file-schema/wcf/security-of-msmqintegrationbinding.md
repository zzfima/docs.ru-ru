---
title: '&lt;security&gt; для &lt;msmqIntegrationBinding&gt;'
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6419c2157281d00cf79de16d4f494fc52bcee598
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45617692"
---
# <a name="ltsecuritygt-of-ltmsmqintegrationbindinggt"></a><span data-ttu-id="7cfa3-102">&lt;security&gt; для &lt;msmqIntegrationBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="7cfa3-102">&lt;security&gt; of &lt;msmqIntegrationBinding&gt;</span></span>
<span data-ttu-id="7cfa3-103">Определяет параметры безопасности транспорта для канала интеграции очереди сообщений (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="7cfa3-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
 <span data-ttu-id="7cfa3-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7cfa3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7cfa3-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="7cfa3-105">\<bindings></span></span>  
<span data-ttu-id="7cfa3-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="7cfa3-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="7cfa3-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="7cfa3-107">\<binding></span></span>  
<span data-ttu-id="7cfa3-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="7cfa3-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cfa3-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7cfa3-109">Syntax</span></span>  
  
```xml  
<msmqIntegrationBinding>  
   <binding>   
       <security mode="None/Transport">  
         <transport msmqAuthenticationMode="None/Windows/Certificate"  
            msmqEncryptionAlgorithm="RC4Stream/AES"  
            msmqProtectionLevel="None/Sign/EncryptAndSign"  
            msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
          <message  algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"  
                        clientCredentialType="None/Windows/UserName/Certificate/CardSpace"  
            defaultProtectionLevel="None/Sign/EncryptAndSign" />  
       </security>  
   </binding>  
</msmqIntegrationBinding>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7cfa3-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7cfa3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7cfa3-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7cfa3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7cfa3-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7cfa3-112">Attributes</span></span>  
  
|<span data-ttu-id="7cfa3-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7cfa3-113">Attribute</span></span>|<span data-ttu-id="7cfa3-114">Описание</span><span class="sxs-lookup"><span data-stu-id="7cfa3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7cfa3-115">режим</span><span class="sxs-lookup"><span data-stu-id="7cfa3-115">mode</span></span>|<span data-ttu-id="7cfa3-116">Задает тип системы безопасности, отвечающей за целостность, конфиденциальность и проверку подлинности при использовании канала интеграции очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="7cfa3-116">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="7cfa3-117">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7cfa3-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7cfa3-118">-None: Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="7cfa3-118">-   None: This disables security.</span></span><br /><span data-ttu-id="7cfa3-119">-Transport: Защита и проверка подлинности предоставляются транспортом.</span><span class="sxs-lookup"><span data-stu-id="7cfa3-119">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="7cfa3-120">Это значение связано с безопасностью сообщений между двумя диспетчерами очереди.</span><span class="sxs-lookup"><span data-stu-id="7cfa3-120">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="7cfa3-121">Между приложением и диспетчером очереди безопасность сообщений не обеспечивается.</span><span class="sxs-lookup"><span data-stu-id="7cfa3-121">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="7cfa3-122">Существующие Msmq-приложения функционально равноценны такому режиму безопасности.</span><span class="sxs-lookup"><span data-stu-id="7cfa3-122">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="7cfa3-123">Значение по умолчанию — `Transport`.</span><span class="sxs-lookup"><span data-stu-id="7cfa3-123">The default value is `Transport`.</span></span> <span data-ttu-id="7cfa3-124">Это атрибут типа <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="7cfa3-124">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7cfa3-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7cfa3-125">Child Elements</span></span>  
  
|<span data-ttu-id="7cfa3-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="7cfa3-126">Element</span></span>|<span data-ttu-id="7cfa3-127">Описание</span><span class="sxs-lookup"><span data-stu-id="7cfa3-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7cfa3-128">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="7cfa3-128">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-msmqintegrationbinding.md)|<span data-ttu-id="7cfa3-129">Определяет параметры безопасности для транспорта интеграции очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="7cfa3-129">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="7cfa3-130">Это элемент типа <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="7cfa3-130">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7cfa3-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7cfa3-131">Parent Elements</span></span>  
  
|<span data-ttu-id="7cfa3-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="7cfa3-132">Element</span></span>|<span data-ttu-id="7cfa3-133">Описание</span><span class="sxs-lookup"><span data-stu-id="7cfa3-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7cfa3-134">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="7cfa3-134">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="7cfa3-135">Элемент привязки [ \<msmqIntegrationBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span><span class="sxs-lookup"><span data-stu-id="7cfa3-135">The binding element of the [\<msmqIntegrationBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7cfa3-136">См. также</span><span class="sxs-lookup"><span data-stu-id="7cfa3-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>  
 [<span data-ttu-id="7cfa3-137">Очереди в WCF</span><span class="sxs-lookup"><span data-stu-id="7cfa3-137">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="7cfa3-138">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="7cfa3-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="7cfa3-139">Привязки</span><span class="sxs-lookup"><span data-stu-id="7cfa3-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="7cfa3-140">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="7cfa3-140">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="7cfa3-141">Использование привязок для настройки службы Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="7cfa3-141">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="7cfa3-142">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="7cfa3-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="7cfa3-143">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="7cfa3-143">\<msmqIntegrationBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)
