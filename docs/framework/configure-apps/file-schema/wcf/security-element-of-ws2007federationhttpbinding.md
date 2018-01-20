---
title: "Элемент &lt;security&gt; &lt;ws2007FederationHttpBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 0358b8cd0ddc91baf4028fa8a3f06d032c3f117b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="ltsecuritygt-element-of-ltws2007federationhttpbindinggt"></a><span data-ttu-id="27dbf-102">Элемент &lt;security&gt; &lt;ws2007FederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="27dbf-102">&lt;security&gt; element of &lt;ws2007FederationHttpBinding&gt;</span></span>
<span data-ttu-id="27dbf-103">Определяет параметры безопасности [ \<ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="27dbf-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="27dbf-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="27dbf-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="27dbf-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="27dbf-105">\<bindings></span></span>  
<span data-ttu-id="27dbf-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="27dbf-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="27dbf-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="27dbf-107">\<binding></span></span>  
<span data-ttu-id="27dbf-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="27dbf-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27dbf-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27dbf-109">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>  
    <binding >  
        <security mode="None/Message/TransportWithMessageCredential">  
           <message negotiateServiceCredential="Boolean"  
                algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/ Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
                defaultProtectionLevel="none/sign/EncryptAndSign"   
                issuedTokenType="string"   
                issuedKeyType="SymmetricKey/PublicKey"  
           </message>  
        </security>  
    </binding>  
</ws2007FederationBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27dbf-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="27dbf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="27dbf-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="27dbf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27dbf-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="27dbf-112">Attributes</span></span>  
  
|<span data-ttu-id="27dbf-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="27dbf-113">Attribute</span></span>|<span data-ttu-id="27dbf-114">Описание</span><span class="sxs-lookup"><span data-stu-id="27dbf-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="27dbf-115">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="27dbf-115">Optional.</span></span> <span data-ttu-id="27dbf-116">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="27dbf-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="27dbf-117">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="27dbf-117">The default value is `Message`.</span></span> <span data-ttu-id="27dbf-118">Это атрибут типа <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="27dbf-118">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="27dbf-119">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="27dbf-119">mode Attribute</span></span>  
  
|<span data-ttu-id="27dbf-120">Значение</span><span class="sxs-lookup"><span data-stu-id="27dbf-120">Value</span></span>|<span data-ttu-id="27dbf-121">Описание</span><span class="sxs-lookup"><span data-stu-id="27dbf-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="27dbf-122">Нет</span><span class="sxs-lookup"><span data-stu-id="27dbf-122">None</span></span>|<span data-ttu-id="27dbf-123">Во время передачи сообщение SOAP не защищено.</span><span class="sxs-lookup"><span data-stu-id="27dbf-123">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="27dbf-124">Сообщение</span><span class="sxs-lookup"><span data-stu-id="27dbf-124">Message</span></span>|<span data-ttu-id="27dbf-125">Целостность, конфиденциальность, проверка подлинности сервера и проверка подлинности клиента обеспечиваются с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="27dbf-125">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="27dbf-126">По умолчанию текст сообщений шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="27dbf-126">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="27dbf-127">Служба должна быть настроена с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="27dbf-127">The service must be configured with a certificate.</span></span> <span data-ttu-id="27dbf-128">Проверка подлинности клиента основана на маркере, выданного клиенту службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="27dbf-128">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="27dbf-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="27dbf-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="27dbf-130">Целостность, конфиденциальность и проверка подлинности сервера обеспечиваются с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="27dbf-130">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="27dbf-131">Служба должна быть настроена с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="27dbf-131">The service must be configured with a certificate.</span></span> <span data-ttu-id="27dbf-132">Проверка подлинности клиента выполняется с помощью средств безопасности сообщений SOAP и основана на маркере, выданном клиенту службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="27dbf-132">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27dbf-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="27dbf-133">Child Elements</span></span>  
  
|<span data-ttu-id="27dbf-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="27dbf-134">Element</span></span>|<span data-ttu-id="27dbf-135">Описание:</span><span class="sxs-lookup"><span data-stu-id="27dbf-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27dbf-136">\<message></span><span class="sxs-lookup"><span data-stu-id="27dbf-136">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="27dbf-137">Определяет параметры безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="27dbf-137">Defines the settings for the message-level security.</span></span> <span data-ttu-id="27dbf-138">Это элемент типа <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="27dbf-138">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="27dbf-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="27dbf-139">Parent Elements</span></span>  
  
|<span data-ttu-id="27dbf-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="27dbf-140">Element</span></span>|<span data-ttu-id="27dbf-141">Описание:</span><span class="sxs-lookup"><span data-stu-id="27dbf-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27dbf-142">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="27dbf-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="27dbf-143">Определяет все возможности [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="27dbf-143">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27dbf-144">См. также</span><span class="sxs-lookup"><span data-stu-id="27dbf-144">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpSecurity>  
 <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>  
 [<span data-ttu-id="27dbf-145">Практическое руководство. Создание WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="27dbf-145">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="27dbf-146">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="27dbf-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="27dbf-147">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="27dbf-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="27dbf-148">Привязки</span><span class="sxs-lookup"><span data-stu-id="27dbf-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="27dbf-149">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="27dbf-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="27dbf-150">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="27dbf-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="27dbf-151">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="27dbf-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
