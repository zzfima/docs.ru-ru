---
title: '&lt;security&gt; для &lt;netMsmqBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: 8be7582ce5db88d9a79698193c44d9c50bdea4cb
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50184759"
---
# <a name="ltsecuritygt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="ea60c-102">&lt;security&gt; для &lt;netMsmqBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="ea60c-102">&lt;security&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="ea60c-103">Определяет параметры безопасности для привязки MSMQ.</span><span class="sxs-lookup"><span data-stu-id="ea60c-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="ea60c-104">Он указывает, включена ли поддержка транспорта или безопасности SOAP и, если поддержка включена, указывает используемые уровни защиты и режим проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="ea60c-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
 <span data-ttu-id="ea60c-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ea60c-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="ea60c-106">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="ea60c-106">\<bindings></span></span>  
<span data-ttu-id="ea60c-107">\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="ea60c-107">\<netMsmqBinding></span></span>  
<span data-ttu-id="ea60c-108">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="ea60c-108">\<binding></span></span>  
<span data-ttu-id="ea60c-109">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="ea60c-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea60c-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea60c-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea60c-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ea60c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ea60c-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ea60c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea60c-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ea60c-113">Attributes</span></span>  
  
|<span data-ttu-id="ea60c-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ea60c-114">Attribute</span></span>|<span data-ttu-id="ea60c-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ea60c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ea60c-116">режим</span><span class="sxs-lookup"><span data-stu-id="ea60c-116">mode</span></span>|<span data-ttu-id="ea60c-117">Задает тип безопасности, который контролирует целостность, конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="ea60c-117">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="ea60c-118">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="ea60c-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ea60c-119">-None: Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="ea60c-119">-   None: This disables security.</span></span><br /><span data-ttu-id="ea60c-120">-Transport: Защита и проверка подлинности предоставляются транспортом.</span><span class="sxs-lookup"><span data-stu-id="ea60c-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="ea60c-121">Это значение связано с безопасностью сообщений между двумя диспетчерами очереди.</span><span class="sxs-lookup"><span data-stu-id="ea60c-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="ea60c-122">Между приложением и диспетчером очереди безопасность сообщений не обеспечивается.</span><span class="sxs-lookup"><span data-stu-id="ea60c-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="ea60c-123">Существующие Msmq-приложения функционально равноценны такому режиму безопасности.</span><span class="sxs-lookup"><span data-stu-id="ea60c-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="ea60c-124">-Message: Задает параметры приложения конечными пунктами.</span><span class="sxs-lookup"><span data-stu-id="ea60c-124">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="ea60c-125">Безопасность на транспортном уровне не предоставляется.</span><span class="sxs-lookup"><span data-stu-id="ea60c-125">There is no security offered at the transport layer.</span></span> <span data-ttu-id="ea60c-126">Такие параметры аналогичны параметрам безопасности, предоставляемой другими стандартными привязками.</span><span class="sxs-lookup"><span data-stu-id="ea60c-126">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="ea60c-127">-Оба: Обеспечивает безопасность на уровне транспорта и слоя обмена сообщениями SOAP.</span><span class="sxs-lookup"><span data-stu-id="ea60c-127">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="ea60c-128">На обоих уровнях требуются одни и те же учетные данные.</span><span class="sxs-lookup"><span data-stu-id="ea60c-128">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="ea60c-129">Значение по умолчанию - Transport.</span><span class="sxs-lookup"><span data-stu-id="ea60c-129">The default value is Transport.</span></span> <span data-ttu-id="ea60c-130">Это атрибут типа <xref:System.ServiceModel.NetMsmqSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="ea60c-130">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea60c-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ea60c-131">Child Elements</span></span>  
  
|<span data-ttu-id="ea60c-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="ea60c-132">Element</span></span>|<span data-ttu-id="ea60c-133">Описание</span><span class="sxs-lookup"><span data-stu-id="ea60c-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea60c-134">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="ea60c-134">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|<span data-ttu-id="ea60c-135">Определяет параметры безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="ea60c-135">Defines the SOAP message security settings.</span></span> <span data-ttu-id="ea60c-136">Это элемент типа <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span><span class="sxs-lookup"><span data-stu-id="ea60c-136">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="ea60c-137">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="ea60c-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|<span data-ttu-id="ea60c-138">Определяет параметры безопасности для транспорта MSMQ.</span><span class="sxs-lookup"><span data-stu-id="ea60c-138">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="ea60c-139">Это элемент типа <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="ea60c-139">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ea60c-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ea60c-140">Parent Elements</span></span>  
  
|<span data-ttu-id="ea60c-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="ea60c-141">Element</span></span>|<span data-ttu-id="ea60c-142">Описание</span><span class="sxs-lookup"><span data-stu-id="ea60c-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ea60c-143">привязка</span><span class="sxs-lookup"><span data-stu-id="ea60c-143">binding</span></span>|<span data-ttu-id="ea60c-144">Элемент привязки [ \<netMsmqBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="ea60c-144">The binding element of the [\<netMsmqBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea60c-145">См. также</span><span class="sxs-lookup"><span data-stu-id="ea60c-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>  
 <xref:System.ServiceModel.NetMsmqBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity>  
 [<span data-ttu-id="ea60c-146">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="ea60c-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="ea60c-147">Привязки</span><span class="sxs-lookup"><span data-stu-id="ea60c-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="ea60c-148">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="ea60c-148">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="ea60c-149">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="ea60c-149">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="ea60c-150">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="ea60c-150">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="ea60c-151">Очереди в WCF</span><span class="sxs-lookup"><span data-stu-id="ea60c-151">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
