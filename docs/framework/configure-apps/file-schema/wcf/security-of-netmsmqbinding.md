---
title: <security> из <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: 1bbc3a460ce707e71b72a469af2e03acd8dc79e5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936689"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="669da-102">\<> безопасности > \<NetMsmqBinding</span><span class="sxs-lookup"><span data-stu-id="669da-102">\<security> of \<netMsmqBinding></span></span>
<span data-ttu-id="669da-103">Определяет параметры безопасности для привязки MSMQ.</span><span class="sxs-lookup"><span data-stu-id="669da-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="669da-104">Он указывает, включена ли поддержка транспорта или безопасности SOAP и, если поддержка включена, указывает используемые уровни защиты и режим проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="669da-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
 <span data-ttu-id="669da-105">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="669da-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="669da-106">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="669da-106">\<bindings></span></span>  
<span data-ttu-id="669da-107">\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="669da-107">\<netMsmqBinding></span></span>  
<span data-ttu-id="669da-108">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="669da-108">\<binding></span></span>  
<span data-ttu-id="669da-109">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="669da-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="669da-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="669da-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/Both">
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
             clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="669da-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="669da-111">Attributes and Elements</span></span>  
 <span data-ttu-id="669da-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="669da-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="669da-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="669da-113">Attributes</span></span>  
  
|<span data-ttu-id="669da-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="669da-114">Attribute</span></span>|<span data-ttu-id="669da-115">Описание</span><span class="sxs-lookup"><span data-stu-id="669da-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="669da-116">режим</span><span class="sxs-lookup"><span data-stu-id="669da-116">mode</span></span>|<span data-ttu-id="669da-117">Задает тип безопасности, который контролирует целостность, конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="669da-117">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="669da-118">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="669da-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="669da-119">None Это отключает безопасность.</span><span class="sxs-lookup"><span data-stu-id="669da-119">-   None: This disables security.</span></span><br /><span data-ttu-id="669da-120">Перемещения Защита и проверка подлинности предоставляются транспортом.</span><span class="sxs-lookup"><span data-stu-id="669da-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="669da-121">Это значение связано с безопасностью сообщений между двумя диспетчерами очереди.</span><span class="sxs-lookup"><span data-stu-id="669da-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="669da-122">Между приложением и диспетчером очереди безопасность сообщений не обеспечивается.</span><span class="sxs-lookup"><span data-stu-id="669da-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="669da-123">Существующие Msmq-приложения функционально равноценны такому режиму безопасности.</span><span class="sxs-lookup"><span data-stu-id="669da-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="669da-124">Письма Указывает безопасность конечного приложения.</span><span class="sxs-lookup"><span data-stu-id="669da-124">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="669da-125">Безопасность на транспортном уровне не предоставляется.</span><span class="sxs-lookup"><span data-stu-id="669da-125">There is no security offered at the transport layer.</span></span> <span data-ttu-id="669da-126">Такие параметры аналогичны параметрам безопасности, предоставляемой другими стандартными привязками.</span><span class="sxs-lookup"><span data-stu-id="669da-126">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="669da-127">Как Обеспечивает безопасность на уровне транспорта и сообщений протокола SOAP.</span><span class="sxs-lookup"><span data-stu-id="669da-127">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="669da-128">На обоих уровнях требуются одни и те же учетные данные.</span><span class="sxs-lookup"><span data-stu-id="669da-128">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="669da-129">Значение по умолчанию - Transport.</span><span class="sxs-lookup"><span data-stu-id="669da-129">The default value is Transport.</span></span> <span data-ttu-id="669da-130">Это атрибут типа <xref:System.ServiceModel.NetMsmqSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="669da-130">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="669da-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="669da-131">Child Elements</span></span>  
  
|<span data-ttu-id="669da-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="669da-132">Element</span></span>|<span data-ttu-id="669da-133">Описание</span><span class="sxs-lookup"><span data-stu-id="669da-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="669da-134">\<> сообщения</span><span class="sxs-lookup"><span data-stu-id="669da-134">\<message></span></span>](message-of-netmsmqbinding.md)|<span data-ttu-id="669da-135">Определяет параметры безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="669da-135">Defines the SOAP message security settings.</span></span> <span data-ttu-id="669da-136">Это элемент типа <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span><span class="sxs-lookup"><span data-stu-id="669da-136">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="669da-137">\<> транспорта</span><span class="sxs-lookup"><span data-stu-id="669da-137">\<transport></span></span>](transport-of-netmsmqbinding.md)|<span data-ttu-id="669da-138">Определяет параметры безопасности для транспорта MSMQ.</span><span class="sxs-lookup"><span data-stu-id="669da-138">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="669da-139">Это элемент типа <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="669da-139">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="669da-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="669da-140">Parent Elements</span></span>  
  
|<span data-ttu-id="669da-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="669da-141">Element</span></span>|<span data-ttu-id="669da-142">Описание</span><span class="sxs-lookup"><span data-stu-id="669da-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="669da-143">привязка</span><span class="sxs-lookup"><span data-stu-id="669da-143">binding</span></span>|<span data-ttu-id="669da-144">Элемент Binding [> \<NetMsmqBinding](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="669da-144">The binding element of the [\<netMsmqBinding>](netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="669da-145">См. также</span><span class="sxs-lookup"><span data-stu-id="669da-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="669da-146">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="669da-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="669da-147">Привязки</span><span class="sxs-lookup"><span data-stu-id="669da-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="669da-148">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="669da-148">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="669da-149">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="669da-149">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="669da-150">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="669da-150">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="669da-151">Очереди в WCF</span><span class="sxs-lookup"><span data-stu-id="669da-151">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
