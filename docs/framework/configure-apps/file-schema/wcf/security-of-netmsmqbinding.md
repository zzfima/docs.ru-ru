---
title: '&lt;security&gt; для &lt;netMsmqBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 0ed1021bdc45d0d64a20ff19410ad56e0d304ed3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltsecuritygt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="e1d39-102">&lt;security&gt; для &lt;netMsmqBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="e1d39-102">&lt;security&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="e1d39-103">Определяет параметры безопасности для привязки MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e1d39-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="e1d39-104">Он указывает, включена ли поддержка транспорта или безопасности SOAP и, если поддержка включена, указывает используемые уровни защиты и режим проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e1d39-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
 <span data-ttu-id="e1d39-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e1d39-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e1d39-106">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="e1d39-106">\<bindings></span></span>  
<span data-ttu-id="e1d39-107">\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="e1d39-107">\<netMsmqBinding></span></span>  
<span data-ttu-id="e1d39-108">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="e1d39-108">\<binding></span></span>  
<span data-ttu-id="e1d39-109">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="e1d39-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1d39-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1d39-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/Both">  
   <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
      msmqEncryptionAlgorithm="RC4Stream/AES"  
      msmqProtectionLevel="None/Sign/EncryptAndSign"  
      msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
      <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="None/Windows/UserName/Certificate/CardSpace"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1d39-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e1d39-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e1d39-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e1d39-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1d39-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e1d39-113">Attributes</span></span>  
  
|<span data-ttu-id="e1d39-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e1d39-114">Attribute</span></span>|<span data-ttu-id="e1d39-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e1d39-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e1d39-116">режим</span><span class="sxs-lookup"><span data-stu-id="e1d39-116">mode</span></span>|<span data-ttu-id="e1d39-117">Задает тип безопасности, который контролирует целостность, конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="e1d39-117">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="e1d39-118">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="e1d39-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e1d39-119">— None: Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="e1d39-119">-   None: This disables security.</span></span><br /><span data-ttu-id="e1d39-120">-Transport: Защита и проверка подлинности предоставляются транспортом.</span><span class="sxs-lookup"><span data-stu-id="e1d39-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="e1d39-121">Это значение связано с безопасностью сообщений между двумя диспетчерами очереди.</span><span class="sxs-lookup"><span data-stu-id="e1d39-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="e1d39-122">Между приложением и диспетчером очереди безопасность сообщений не обеспечивается.</span><span class="sxs-lookup"><span data-stu-id="e1d39-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="e1d39-123">Существующие Msmq-приложения функционально равноценны такому режиму безопасности.</span><span class="sxs-lookup"><span data-stu-id="e1d39-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="e1d39-124">-Сообщение об ошибке Указывает комплексной безопасности приложения.</span><span class="sxs-lookup"><span data-stu-id="e1d39-124">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="e1d39-125">Безопасность на транспортном уровне не предоставляется.</span><span class="sxs-lookup"><span data-stu-id="e1d39-125">There is no security offered at the transport layer.</span></span> <span data-ttu-id="e1d39-126">Такие параметры аналогичны параметрам безопасности, предоставляемой другими стандартными привязками.</span><span class="sxs-lookup"><span data-stu-id="e1d39-126">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="e1d39-127">-Оба: Обеспечивает безопасность на уровне транспорта и обмена сообщениями SOAP.</span><span class="sxs-lookup"><span data-stu-id="e1d39-127">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="e1d39-128">На обоих уровнях требуются одни и те же учетные данные.</span><span class="sxs-lookup"><span data-stu-id="e1d39-128">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="e1d39-129">Значение по умолчанию - Transport.</span><span class="sxs-lookup"><span data-stu-id="e1d39-129">The default value is Transport.</span></span> <span data-ttu-id="e1d39-130">Это атрибут типа <xref:System.ServiceModel.NetMsmqSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="e1d39-130">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1d39-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e1d39-131">Child Elements</span></span>  
  
|<span data-ttu-id="e1d39-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="e1d39-132">Element</span></span>|<span data-ttu-id="e1d39-133">Описание</span><span class="sxs-lookup"><span data-stu-id="e1d39-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1d39-134">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="e1d39-134">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|<span data-ttu-id="e1d39-135">Определяет параметры безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="e1d39-135">Defines the SOAP message security settings.</span></span> <span data-ttu-id="e1d39-136">Это элемент типа <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span><span class="sxs-lookup"><span data-stu-id="e1d39-136">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="e1d39-137">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="e1d39-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|<span data-ttu-id="e1d39-138">Определяет параметры безопасности для транспорта MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e1d39-138">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="e1d39-139">Это элемент типа <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="e1d39-139">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e1d39-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e1d39-140">Parent Elements</span></span>  
  
|<span data-ttu-id="e1d39-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="e1d39-141">Element</span></span>|<span data-ttu-id="e1d39-142">Описание</span><span class="sxs-lookup"><span data-stu-id="e1d39-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e1d39-143">привязка</span><span class="sxs-lookup"><span data-stu-id="e1d39-143">binding</span></span>|<span data-ttu-id="e1d39-144">Элемент привязки для [ \<netMsmqBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="e1d39-144">The binding element of the [\<netMsmqBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e1d39-145">См. также</span><span class="sxs-lookup"><span data-stu-id="e1d39-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>  
 <xref:System.ServiceModel.NetMsmqBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity>  
 [<span data-ttu-id="e1d39-146">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e1d39-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="e1d39-147">Привязки</span><span class="sxs-lookup"><span data-stu-id="e1d39-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e1d39-148">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="e1d39-148">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="e1d39-149">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="e1d39-149">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="e1d39-150">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="e1d39-150">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="e1d39-151">Очереди в WCF</span><span class="sxs-lookup"><span data-stu-id="e1d39-151">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
