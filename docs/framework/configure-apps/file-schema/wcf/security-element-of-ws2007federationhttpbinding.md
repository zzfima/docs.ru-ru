---
title: Элемент &lt;security&gt; &lt;ws2007FederationHttpBinding&gt;
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
author: BrucePerlerMS
ms.openlocfilehash: 6451d4c3cdcf649ae959012826eb433732d87c54
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47172658"
---
# <a name="ltsecuritygt-element-of-ltws2007federationhttpbindinggt"></a><span data-ttu-id="5e989-102">Элемент &lt;security&gt; &lt;ws2007FederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="5e989-102">&lt;security&gt; element of &lt;ws2007FederationHttpBinding&gt;</span></span>
<span data-ttu-id="5e989-103">Определяет параметры безопасности [ \<ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="5e989-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="5e989-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5e989-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5e989-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="5e989-105">\<bindings></span></span>  
<span data-ttu-id="5e989-106">\<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="5e989-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="5e989-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="5e989-107">\<binding></span></span>  
<span data-ttu-id="5e989-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="5e989-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e989-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e989-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e989-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5e989-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5e989-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5e989-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e989-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5e989-112">Attributes</span></span>  
  
|<span data-ttu-id="5e989-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5e989-113">Attribute</span></span>|<span data-ttu-id="5e989-114">Описание</span><span class="sxs-lookup"><span data-stu-id="5e989-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="5e989-115">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="5e989-115">Optional.</span></span> <span data-ttu-id="5e989-116">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="5e989-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="5e989-117">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="5e989-117">The default value is `Message`.</span></span> <span data-ttu-id="5e989-118">Это атрибут типа <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="5e989-118">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="5e989-119">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="5e989-119">mode Attribute</span></span>  
  
|<span data-ttu-id="5e989-120">Значение</span><span class="sxs-lookup"><span data-stu-id="5e989-120">Value</span></span>|<span data-ttu-id="5e989-121">Описание</span><span class="sxs-lookup"><span data-stu-id="5e989-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5e989-122">Нет</span><span class="sxs-lookup"><span data-stu-id="5e989-122">None</span></span>|<span data-ttu-id="5e989-123">Во время передачи сообщение SOAP не защищено.</span><span class="sxs-lookup"><span data-stu-id="5e989-123">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="5e989-124">Сообщение</span><span class="sxs-lookup"><span data-stu-id="5e989-124">Message</span></span>|<span data-ttu-id="5e989-125">Целостность, конфиденциальность, проверка подлинности сервера и проверка подлинности клиента обеспечиваются с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="5e989-125">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="5e989-126">По умолчанию текст сообщений шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="5e989-126">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="5e989-127">Служба должна быть настроена с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="5e989-127">The service must be configured with a certificate.</span></span> <span data-ttu-id="5e989-128">Проверка подлинности клиента основана на маркере, выданного клиенту службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="5e989-128">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="5e989-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="5e989-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="5e989-130">Целостность, конфиденциальность и проверка подлинности сервера обеспечиваются с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5e989-130">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="5e989-131">Служба должна быть настроена с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="5e989-131">The service must be configured with a certificate.</span></span> <span data-ttu-id="5e989-132">Проверка подлинности клиента выполняется с помощью средств безопасности сообщений SOAP и основана на маркере, выданном клиенту службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="5e989-132">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5e989-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5e989-133">Child Elements</span></span>  
  
|<span data-ttu-id="5e989-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="5e989-134">Element</span></span>|<span data-ttu-id="5e989-135">Описание</span><span class="sxs-lookup"><span data-stu-id="5e989-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e989-136">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="5e989-136">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="5e989-137">Определяет параметры безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="5e989-137">Defines the settings for the message-level security.</span></span> <span data-ttu-id="5e989-138">Это элемент типа <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="5e989-138">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5e989-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5e989-139">Parent Elements</span></span>  
  
|<span data-ttu-id="5e989-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="5e989-140">Element</span></span>|<span data-ttu-id="5e989-141">Описание</span><span class="sxs-lookup"><span data-stu-id="5e989-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e989-142">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="5e989-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="5e989-143">Определяет все возможности привязки [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="5e989-143">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5e989-144">См. также</span><span class="sxs-lookup"><span data-stu-id="5e989-144">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpSecurity>  
 <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>  
 [<span data-ttu-id="5e989-145">Практическое руководство. Создание WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="5e989-145">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="5e989-146">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="5e989-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="5e989-147">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="5e989-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="5e989-148">Привязки</span><span class="sxs-lookup"><span data-stu-id="5e989-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="5e989-149">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="5e989-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="5e989-150">Использование привязок для настройки службы Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="5e989-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="5e989-151">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="5e989-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
