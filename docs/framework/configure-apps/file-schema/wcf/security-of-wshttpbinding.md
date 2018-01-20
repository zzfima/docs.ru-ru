---
title: "&lt;security&gt; для &lt;wsHttpBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
caps.latest.revision: "18"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: dda6e48d3d2fec7f3ad6b9dd665e8a1092a47d60
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="ltsecuritygt-of-ltwshttpbindinggt"></a><span data-ttu-id="ca17f-102">&lt;security&gt; для &lt;wsHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="ca17f-102">&lt;security&gt; of &lt;wsHttpBinding&gt;</span></span>
<span data-ttu-id="ca17f-103">Представляет функциональные возможности безопасности [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="ca17f-103">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="ca17f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ca17f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ca17f-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="ca17f-105">\<bindings></span></span>  
<span data-ttu-id="ca17f-106">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="ca17f-106">\<wsHttpBinding></span></span>  
<span data-ttu-id="ca17f-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="ca17f-107">\<binding></span></span>  
<span data-ttu-id="ca17f-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="ca17f-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca17f-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca17f-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithMessageCredential">  
   <transport  
         clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      realm="string"   
      defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      defaultRealm="string" />  
   <message  
            clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
       establishSecurityContext="Boolean"   
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca17f-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ca17f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ca17f-111">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ca17f-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca17f-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ca17f-112">Attributes</span></span>  
  
|<span data-ttu-id="ca17f-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ca17f-113">Attribute</span></span>|<span data-ttu-id="ca17f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ca17f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca17f-115">режим</span><span class="sxs-lookup"><span data-stu-id="ca17f-115">mode</span></span>|<span data-ttu-id="ca17f-116">— Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="ca17f-116">-   Optional.</span></span> <span data-ttu-id="ca17f-117">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="ca17f-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="ca17f-118">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="ca17f-118">The default is `Message`.</span></span><br /><span data-ttu-id="ca17f-119">-Этот атрибут имеет тип <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="ca17f-119">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="ca17f-120">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="ca17f-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="ca17f-121">Значение</span><span class="sxs-lookup"><span data-stu-id="ca17f-121">Value</span></span>|<span data-ttu-id="ca17f-122">Описание</span><span class="sxs-lookup"><span data-stu-id="ca17f-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ca17f-123">Нет</span><span class="sxs-lookup"><span data-stu-id="ca17f-123">None</span></span>|<span data-ttu-id="ca17f-124">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="ca17f-124">Security is disabled.</span></span>|  
|<span data-ttu-id="ca17f-125">Transport</span><span class="sxs-lookup"><span data-stu-id="ca17f-125">Transport</span></span>|<span data-ttu-id="ca17f-126">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ca17f-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="ca17f-127">Необходимо настроить службу с использованием сертификата SSL.</span><span class="sxs-lookup"><span data-stu-id="ca17f-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="ca17f-128">Сообщение полностью защищено с помощью HTTPS, а проверка подлинности выполняется клиентом с помощью SSL-сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="ca17f-128">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="ca17f-129">Проверка подлинности клиента контролируется посредством атрибута `ClientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="ca17f-129">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="ca17f-130">из [ \<транспорта >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="ca17f-130">of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="ca17f-131">Сообщение</span><span class="sxs-lookup"><span data-stu-id="ca17f-131">Message</span></span>|<span data-ttu-id="ca17f-132">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="ca17f-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="ca17f-133">По умолчанию текст сообщений SOAP шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="ca17f-133">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="ca17f-134">Этот режим предоставляет множество функций, например сведения о доступности учетных данных службы для клиентов на внештатных каналах, об используемом наборе алгоритмов и об уровне защиты, применяемом к тексту сообщения через свойство Security.Message.</span><span class="sxs-lookup"><span data-stu-id="ca17f-134">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="ca17f-135">Проверка подлинности клиента выполняется один раз за сеанс, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="ca17f-135">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="ca17f-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="ca17f-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="ca17f-137">В данном режиме HTTPS обеспечивает целостность, конфиденциальность и проверку подлинности сервера, а механизм безопасности сообщений SOAP обеспечивает проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="ca17f-137">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="ca17f-138">По умолчанию проверка подлинности клиента выполняется один раз за сеанс, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="ca17f-138">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca17f-139">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ca17f-139">Child Elements</span></span>  
  
|<span data-ttu-id="ca17f-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="ca17f-140">Element</span></span>|<span data-ttu-id="ca17f-141">Описание:</span><span class="sxs-lookup"><span data-stu-id="ca17f-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca17f-142">\<transport></span><span class="sxs-lookup"><span data-stu-id="ca17f-142">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)|<span data-ttu-id="ca17f-143">Определяет параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="ca17f-143">Defines the transport security settings.</span></span> <span data-ttu-id="ca17f-144">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="ca17f-144">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="ca17f-145">\<message></span><span class="sxs-lookup"><span data-stu-id="ca17f-145">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)|<span data-ttu-id="ca17f-146">Определяет параметры безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="ca17f-146">Defines the security settings for the message.</span></span> <span data-ttu-id="ca17f-147">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="ca17f-147">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ca17f-148">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ca17f-148">Parent Elements</span></span>  
  
|<span data-ttu-id="ca17f-149">Элемент</span><span class="sxs-lookup"><span data-stu-id="ca17f-149">Element</span></span>|<span data-ttu-id="ca17f-150">Описание:</span><span class="sxs-lookup"><span data-stu-id="ca17f-150">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca17f-151">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="ca17f-151">\<wsHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="ca17f-152">Привязка безопасности для приложений транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="ca17f-152">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca17f-153">Примечания</span><span class="sxs-lookup"><span data-stu-id="ca17f-153">Remarks</span></span>  
 <span data-ttu-id="ca17f-154">Класс WSHttpBinding предназначен для взаимодействия со службами, реализующими спецификации WS-\*.</span><span class="sxs-lookup"><span data-stu-id="ca17f-154">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="ca17f-155">Безопасность транспорта для этой привязки обеспечивается посредством протокола SSL по протоколам HTTP или HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ca17f-155">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca17f-156">См. также</span><span class="sxs-lookup"><span data-stu-id="ca17f-156">See Also</span></span>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.WSHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 [<span data-ttu-id="ca17f-157">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="ca17f-157">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="ca17f-158">Привязки</span><span class="sxs-lookup"><span data-stu-id="ca17f-158">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="ca17f-159">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="ca17f-159">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="ca17f-160">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="ca17f-160">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="ca17f-161">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="ca17f-161">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
