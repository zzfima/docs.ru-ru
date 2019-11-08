---
title: Элемент <security> для <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: b85c54c6507313522286e0c66504cfd0c8afb2b0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738722"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="df092-102">\<> безопасности элемента \<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="df092-102">\<security> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="df092-103">Определяет параметры безопасности элемента [\<ws2007FederationHttpBinding >](ws2007federationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="df092-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
<span data-ttu-id="df092-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="df092-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="df092-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="df092-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="df092-106">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="df092-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="df092-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ws2007FederationHttpBinding >** ](ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="df092-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="df092-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="df092-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="df092-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<security >**</span><span class="sxs-lookup"><span data-stu-id="df092-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df092-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df092-110">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/  Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               defaultProtectionLevel="none/sign/EncryptAndSign"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
      </message>
    </security>
  </binding>
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df092-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="df092-111">Attributes and Elements</span></span>  
 <span data-ttu-id="df092-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="df092-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df092-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="df092-113">Attributes</span></span>  
  
|<span data-ttu-id="df092-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="df092-114">Attribute</span></span>|<span data-ttu-id="df092-115">Описание</span><span class="sxs-lookup"><span data-stu-id="df092-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="df092-116">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="df092-116">Optional.</span></span> <span data-ttu-id="df092-117">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="df092-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="df092-118">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="df092-118">The default value is `Message`.</span></span> <span data-ttu-id="df092-119">Это атрибут типа <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="df092-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="df092-120">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="df092-120">mode Attribute</span></span>  
  
|<span data-ttu-id="df092-121">значения</span><span class="sxs-lookup"><span data-stu-id="df092-121">Value</span></span>|<span data-ttu-id="df092-122">Описание</span><span class="sxs-lookup"><span data-stu-id="df092-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="df092-123">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="df092-123">None</span></span>|<span data-ttu-id="df092-124">Во время передачи сообщение SOAP не защищено.</span><span class="sxs-lookup"><span data-stu-id="df092-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="df092-125">Сообщение</span><span class="sxs-lookup"><span data-stu-id="df092-125">Message</span></span>|<span data-ttu-id="df092-126">Целостность, конфиденциальность, проверка подлинности сервера и проверка подлинности клиента обеспечиваются с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="df092-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="df092-127">По умолчанию текст сообщений шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="df092-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="df092-128">Служба должна быть настроена с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="df092-128">The service must be configured with a certificate.</span></span> <span data-ttu-id="df092-129">Проверка подлинности клиента основана на маркере, выданного клиенту службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="df092-129">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="df092-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="df092-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="df092-131">Целостность, конфиденциальность и проверка подлинности сервера обеспечиваются с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="df092-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="df092-132">Служба должна быть настроена с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="df092-132">The service must be configured with a certificate.</span></span> <span data-ttu-id="df092-133">Проверка подлинности клиента выполняется с помощью средств безопасности сообщений SOAP и основана на маркере, выданном клиенту службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="df092-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="df092-134">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="df092-134">Child Elements</span></span>  
  
|<span data-ttu-id="df092-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="df092-135">Element</span></span>|<span data-ttu-id="df092-136">Описание</span><span class="sxs-lookup"><span data-stu-id="df092-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df092-137">сообщение \<</span><span class="sxs-lookup"><span data-stu-id="df092-137">\<message></span></span>](message-of-ws2007httpbinding.md)|<span data-ttu-id="df092-138">Определяет параметры безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="df092-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="df092-139">Это элемент типа <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="df092-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="df092-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="df092-140">Parent Elements</span></span>  
  
|<span data-ttu-id="df092-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="df092-141">Element</span></span>|<span data-ttu-id="df092-142">Описание</span><span class="sxs-lookup"><span data-stu-id="df092-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df092-143">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="df092-143">\<binding></span></span>](bindings.md)|<span data-ttu-id="df092-144">Определяет все возможности привязки [\<wsDualHttpBinding >](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="df092-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df092-145">См. также</span><span class="sxs-lookup"><span data-stu-id="df092-145">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="df092-146">Практическое руководство. Создание WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="df092-146">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="df092-147">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="df092-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="df092-148">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="df092-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="df092-149">Привязки</span><span class="sxs-lookup"><span data-stu-id="df092-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="df092-150">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="df092-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="df092-151">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="df092-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="df092-152">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="df092-152">\<binding></span></span>](bindings.md)
