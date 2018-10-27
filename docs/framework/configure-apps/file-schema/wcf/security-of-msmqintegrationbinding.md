---
title: '&lt;security&gt; для &lt;msmqIntegrationBinding&gt;'
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: 574c0d7cba88f724143e642da13cace8c329dea6
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/26/2018
ms.locfileid: "50039693"
---
# <a name="ltsecuritygt-of-ltmsmqintegrationbindinggt"></a><span data-ttu-id="cb013-102">&lt;security&gt; для &lt;msmqIntegrationBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="cb013-102">&lt;security&gt; of &lt;msmqIntegrationBinding&gt;</span></span>
<span data-ttu-id="cb013-103">Определяет параметры безопасности транспорта для канала интеграции очереди сообщений (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="cb013-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
 <span data-ttu-id="cb013-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="cb013-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cb013-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="cb013-105">\<bindings></span></span>  
<span data-ttu-id="cb013-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="cb013-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="cb013-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="cb013-107">\<binding></span></span>  
<span data-ttu-id="cb013-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="cb013-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb013-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb013-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb013-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cb013-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cb013-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cb013-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb013-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cb013-112">Attributes</span></span>  
  
|<span data-ttu-id="cb013-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cb013-113">Attribute</span></span>|<span data-ttu-id="cb013-114">Описание</span><span class="sxs-lookup"><span data-stu-id="cb013-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cb013-115">режим</span><span class="sxs-lookup"><span data-stu-id="cb013-115">mode</span></span>|<span data-ttu-id="cb013-116">Задает тип системы безопасности, отвечающей за целостность, конфиденциальность и проверку подлинности при использовании канала интеграции очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="cb013-116">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="cb013-117">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="cb013-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="cb013-118">-None: Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="cb013-118">-   None: This disables security.</span></span><br /><span data-ttu-id="cb013-119">-Transport: Защита и проверка подлинности предоставляются транспортом.</span><span class="sxs-lookup"><span data-stu-id="cb013-119">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="cb013-120">Это значение связано с безопасностью сообщений между двумя диспетчерами очереди.</span><span class="sxs-lookup"><span data-stu-id="cb013-120">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="cb013-121">Между приложением и диспетчером очереди безопасность сообщений не обеспечивается.</span><span class="sxs-lookup"><span data-stu-id="cb013-121">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="cb013-122">Существующие Msmq-приложения функционально равноценны такому режиму безопасности.</span><span class="sxs-lookup"><span data-stu-id="cb013-122">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="cb013-123">Значение по умолчанию — `Transport`.</span><span class="sxs-lookup"><span data-stu-id="cb013-123">The default value is `Transport`.</span></span> <span data-ttu-id="cb013-124">Это атрибут типа <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="cb013-124">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb013-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cb013-125">Child Elements</span></span>  
  
|<span data-ttu-id="cb013-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="cb013-126">Element</span></span>|<span data-ttu-id="cb013-127">Описание</span><span class="sxs-lookup"><span data-stu-id="cb013-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb013-128">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="cb013-128">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-msmqintegrationbinding.md)|<span data-ttu-id="cb013-129">Определяет параметры безопасности для транспорта интеграции очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="cb013-129">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="cb013-130">Это элемент типа <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="cb013-130">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cb013-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cb013-131">Parent Elements</span></span>  
  
|<span data-ttu-id="cb013-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="cb013-132">Element</span></span>|<span data-ttu-id="cb013-133">Описание</span><span class="sxs-lookup"><span data-stu-id="cb013-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb013-134">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="cb013-134">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="cb013-135">Элемент привязки [ \<msmqIntegrationBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span><span class="sxs-lookup"><span data-stu-id="cb013-135">The binding element of the [\<msmqIntegrationBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cb013-136">См. также</span><span class="sxs-lookup"><span data-stu-id="cb013-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>  
 [<span data-ttu-id="cb013-137">Очереди в WCF</span><span class="sxs-lookup"><span data-stu-id="cb013-137">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="cb013-138">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="cb013-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="cb013-139">Привязки</span><span class="sxs-lookup"><span data-stu-id="cb013-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="cb013-140">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="cb013-140">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="cb013-141">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="cb013-141">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="cb013-142">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="cb013-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="cb013-143">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="cb013-143">\<msmqIntegrationBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)
