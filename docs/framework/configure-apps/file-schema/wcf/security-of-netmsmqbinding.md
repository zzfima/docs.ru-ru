---
title: <security> из <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: 7877fd59aff581eee5b62a1ca224dbf51c956069
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738678"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="2f2ff-102">\<> безопасности \<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="2f2ff-102">\<security> of \<netMsmqBinding></span></span>
<span data-ttu-id="2f2ff-103">Определяет параметры безопасности для привязки MSMQ.</span><span class="sxs-lookup"><span data-stu-id="2f2ff-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="2f2ff-104">Он указывает, включена ли поддержка транспорта или безопасности SOAP и, если поддержка включена, указывает используемые уровни защиты и режим проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="2f2ff-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
<span data-ttu-id="2f2ff-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2f2ff-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2f2ff-106">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2f2ff-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2f2ff-107">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="2f2ff-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="2f2ff-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netMsmqBinding >** ](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2f2ff-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="2f2ff-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="2f2ff-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="2f2ff-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<security >**</span><span class="sxs-lookup"><span data-stu-id="2f2ff-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f2ff-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f2ff-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f2ff-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2f2ff-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2f2ff-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2f2ff-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f2ff-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2f2ff-114">Attributes</span></span>  
  
|<span data-ttu-id="2f2ff-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2f2ff-115">Attribute</span></span>|<span data-ttu-id="2f2ff-116">Описание</span><span class="sxs-lookup"><span data-stu-id="2f2ff-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2f2ff-117">режим</span><span class="sxs-lookup"><span data-stu-id="2f2ff-117">mode</span></span>|<span data-ttu-id="2f2ff-118">Задает тип безопасности, который контролирует целостность, конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="2f2ff-118">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="2f2ff-119">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="2f2ff-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="2f2ff-120">-None: отключает безопасность.</span><span class="sxs-lookup"><span data-stu-id="2f2ff-120">-   None: This disables security.</span></span><br /><span data-ttu-id="2f2ff-121">-Transport: защита и проверка подлинности предоставляются транспортом.</span><span class="sxs-lookup"><span data-stu-id="2f2ff-121">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="2f2ff-122">Это значение связано с безопасностью сообщений между двумя диспетчерами очереди.</span><span class="sxs-lookup"><span data-stu-id="2f2ff-122">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="2f2ff-123">Между приложением и диспетчером очереди безопасность сообщений не обеспечивается.</span><span class="sxs-lookup"><span data-stu-id="2f2ff-123">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="2f2ff-124">Существующие Msmq-приложения функционально равноценны такому режиму безопасности.</span><span class="sxs-lookup"><span data-stu-id="2f2ff-124">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="2f2ff-125">-Message: определяет безопасность конечного приложения.</span><span class="sxs-lookup"><span data-stu-id="2f2ff-125">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="2f2ff-126">Безопасность на транспортном уровне не предоставляется.</span><span class="sxs-lookup"><span data-stu-id="2f2ff-126">There is no security offered at the transport layer.</span></span> <span data-ttu-id="2f2ff-127">Такие параметры аналогичны параметрам безопасности, предоставляемой другими стандартными привязками.</span><span class="sxs-lookup"><span data-stu-id="2f2ff-127">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="2f2ff-128">Оба: обеспечивают безопасность на уровне транспорта и сообщений протокола SOAP.</span><span class="sxs-lookup"><span data-stu-id="2f2ff-128">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="2f2ff-129">На обоих уровнях требуются одни и те же учетные данные.</span><span class="sxs-lookup"><span data-stu-id="2f2ff-129">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="2f2ff-130">Значение по умолчанию - Transport.</span><span class="sxs-lookup"><span data-stu-id="2f2ff-130">The default value is Transport.</span></span> <span data-ttu-id="2f2ff-131">Это атрибут типа <xref:System.ServiceModel.NetMsmqSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="2f2ff-131">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f2ff-132">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2f2ff-132">Child Elements</span></span>  
  
|<span data-ttu-id="2f2ff-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="2f2ff-133">Element</span></span>|<span data-ttu-id="2f2ff-134">Описание</span><span class="sxs-lookup"><span data-stu-id="2f2ff-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f2ff-135">сообщение \<</span><span class="sxs-lookup"><span data-stu-id="2f2ff-135">\<message></span></span>](message-of-netmsmqbinding.md)|<span data-ttu-id="2f2ff-136">Определяет параметры безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="2f2ff-136">Defines the SOAP message security settings.</span></span> <span data-ttu-id="2f2ff-137">Это элемент типа <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span><span class="sxs-lookup"><span data-stu-id="2f2ff-137">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="2f2ff-138">\<> транспорта</span><span class="sxs-lookup"><span data-stu-id="2f2ff-138">\<transport></span></span>](transport-of-netmsmqbinding.md)|<span data-ttu-id="2f2ff-139">Определяет параметры безопасности для транспорта MSMQ.</span><span class="sxs-lookup"><span data-stu-id="2f2ff-139">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="2f2ff-140">Это элемент типа <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="2f2ff-140">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2f2ff-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2f2ff-141">Parent Elements</span></span>  
  
|<span data-ttu-id="2f2ff-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="2f2ff-142">Element</span></span>|<span data-ttu-id="2f2ff-143">Описание</span><span class="sxs-lookup"><span data-stu-id="2f2ff-143">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2f2ff-144">привязка</span><span class="sxs-lookup"><span data-stu-id="2f2ff-144">binding</span></span>|<span data-ttu-id="2f2ff-145">Элемент Binding [\<netMsmqBinding >](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2f2ff-145">The binding element of the [\<netMsmqBinding>](netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2f2ff-146">См. также</span><span class="sxs-lookup"><span data-stu-id="2f2ff-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="2f2ff-147">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="2f2ff-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="2f2ff-148">Привязки</span><span class="sxs-lookup"><span data-stu-id="2f2ff-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2f2ff-149">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="2f2ff-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2f2ff-150">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="2f2ff-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="2f2ff-151">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="2f2ff-151">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="2f2ff-152">Очереди в WCF</span><span class="sxs-lookup"><span data-stu-id="2f2ff-152">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
