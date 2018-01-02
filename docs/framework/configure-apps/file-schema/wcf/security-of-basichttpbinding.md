---
title: "&lt;security&gt; для &lt;basicHttpBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
caps.latest.revision: "16"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: c0ef60cdb53ed504d1738e4e17329f7420943312
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltbasichttpbindinggt"></a><span data-ttu-id="4dfe7-102">&lt;security&gt; для &lt;basicHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="4dfe7-102">&lt;security&gt; of &lt;basicHttpBinding&gt;</span></span>
<span data-ttu-id="4dfe7-103">Определяет возможности безопасности [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="4dfe7-103">Defines the security capabilities of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="4dfe7-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4dfe7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4dfe7-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="4dfe7-105">\<bindings></span></span>  
<span data-ttu-id="4dfe7-106">\<basicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="4dfe7-106">\<basicHttpBinding></span></span>  
<span data-ttu-id="4dfe7-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="4dfe7-107">\<binding></span></span>  
<span data-ttu-id="4dfe7-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="4dfe7-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dfe7-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4dfe7-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">  
   <transport  
      clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      realm="string" />  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4dfe7-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4dfe7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4dfe7-111">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4dfe7-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4dfe7-112">Attributes</span></span>  
  
|<span data-ttu-id="4dfe7-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4dfe7-113">Attribute</span></span>|<span data-ttu-id="4dfe7-114">Описание</span><span class="sxs-lookup"><span data-stu-id="4dfe7-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4dfe7-115">режим</span><span class="sxs-lookup"><span data-stu-id="4dfe7-115">mode</span></span>|<span data-ttu-id="4dfe7-116">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-116">Optional.</span></span> <span data-ttu-id="4dfe7-117">Задает тип используемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="4dfe7-118">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-118">The default is `None`.</span></span> <span data-ttu-id="4dfe7-119">Это атрибут типа <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-119">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="4dfe7-120">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="4dfe7-120">mode Attribute</span></span>  
  
|<span data-ttu-id="4dfe7-121">Значение</span><span class="sxs-lookup"><span data-stu-id="4dfe7-121">Value</span></span>|<span data-ttu-id="4dfe7-122">Описание</span><span class="sxs-lookup"><span data-stu-id="4dfe7-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4dfe7-123">Нет</span><span class="sxs-lookup"><span data-stu-id="4dfe7-123">None</span></span>|<span data-ttu-id="4dfe7-124">-Во время передачи сообщения не защищены.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-124">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="4dfe7-125">Transport</span><span class="sxs-lookup"><span data-stu-id="4dfe7-125">Transport</span></span>|<span data-ttu-id="4dfe7-126">Безопасность обеспечивается с помощью транспорта HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="4dfe7-127">Сообщения SOAP защищаются при помощи HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="4dfe7-128">Служба проходит проверку подлинности для клиента с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="4dfe7-129">Проверка подлинности клиента осуществляется с помощью предоставленного ClientCredentialType.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-129">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="4dfe7-130">В разделе [ \<транспорта >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="4dfe7-130">See the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="4dfe7-131">Сообщение</span><span class="sxs-lookup"><span data-stu-id="4dfe7-131">Message</span></span>|<span data-ttu-id="4dfe7-132">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="4dfe7-133">По умолчанию текст сообщений шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-133">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="4dfe7-134">Для этой привязки система требует, чтобы клиенту был предоставлен сертификат сервера с использованием внештатного канала.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-134">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="4dfe7-135">Единственным допустимым значением `ClientCredentialType` для данной привязки является `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-135">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="4dfe7-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="4dfe7-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="4dfe7-137">Целостность, конфиденциальность и проверка подлинности сервера обеспечиваются с помощью средств безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-137">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="4dfe7-138">Проверка подлинности клиента осуществляется при помощи механизма безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-138">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="4dfe7-139">Данный режим может использоваться, когда проверка подлинности клиента осуществляется с помощью имени пользователя/пароля и существует развернутый канал HTTP с обеспечением безопасности при передаче сообщений.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-139">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="4dfe7-140">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="4dfe7-140">TransportCredentialOnly</span></span>|<span data-ttu-id="4dfe7-141">Данный режим не обеспечивает целостности и конфиденциальности сообщений.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-141">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="4dfe7-142">Он предоставляет проверку подлинности клиента на основе http.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-142">It provides http-based client authentication.</span></span> <span data-ttu-id="4dfe7-143">Этот режим следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-143">This mode should be used with caution.</span></span> <span data-ttu-id="4dfe7-144">Он должен использоваться в тех средах, где безопасность транспорта обеспечивается другими средствами (например, IPSec), а инфраструктура [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] обеспечивает только проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-144">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4dfe7-145">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4dfe7-145">Child Elements</span></span>  
  
|<span data-ttu-id="4dfe7-146">Элемент</span><span class="sxs-lookup"><span data-stu-id="4dfe7-146">Element</span></span>|<span data-ttu-id="4dfe7-147">Описание:</span><span class="sxs-lookup"><span data-stu-id="4dfe7-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4dfe7-148">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="4dfe7-148">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)|<span data-ttu-id="4dfe7-149">Определяет параметры безопасности транспорта для базовой службы HTTP.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-149">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="4dfe7-150">Данный элемент соответствует <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-150">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="4dfe7-151">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="4dfe7-151">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-basichttpbinding.md)|<span data-ttu-id="4dfe7-152">Определяет параметры безопасности сообщений для базовой службы HTTP.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-152">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="4dfe7-153">Данный элемент соответствует <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-153">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4dfe7-154">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4dfe7-154">Parent Elements</span></span>  
  
|<span data-ttu-id="4dfe7-155">Элемент</span><span class="sxs-lookup"><span data-stu-id="4dfe7-155">Element</span></span>|<span data-ttu-id="4dfe7-156">Описание</span><span class="sxs-lookup"><span data-stu-id="4dfe7-156">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4dfe7-157">привязка</span><span class="sxs-lookup"><span data-stu-id="4dfe7-157">binding</span></span>|<span data-ttu-id="4dfe7-158">Элемент привязки для [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="4dfe7-158">The binding element of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4dfe7-159">Примечания</span><span class="sxs-lookup"><span data-stu-id="4dfe7-159">Remarks</span></span>  
 <span data-ttu-id="4dfe7-160">По умолчанию сообщение SOAP не защищено и проверка подлинности клиента не выполняется.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-160">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="4dfe7-161">Данный элемент позволяет настроить дополнительные параметры безопасности для элемента `basicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-161">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dfe7-162">См. также</span><span class="sxs-lookup"><span data-stu-id="4dfe7-162">See Also</span></span>  
 <xref:System.ServiceModel.BasicHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="4dfe7-163">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="4dfe7-163">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="4dfe7-164">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="4dfe7-164">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="4dfe7-165">Привязки</span><span class="sxs-lookup"><span data-stu-id="4dfe7-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="4dfe7-166">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="4dfe7-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="4dfe7-167">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="4dfe7-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="4dfe7-168">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="4dfe7-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
