---
title: "&lt;безопасность&gt; для &lt;netHttpBinding"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cbe36a801565af0d3664e5c827f8ce903be3b5c7
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="ltsecuritygt-of-ltnethttpbinding"></a><span data-ttu-id="9ab9c-102">&lt;безопасность&gt; для &lt;netHttpBinding</span><span class="sxs-lookup"><span data-stu-id="9ab9c-102">&lt;security&gt; of &lt;netHttpBinding</span></span>
<span data-ttu-id="9ab9c-103">Определяет возможности безопасности [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="9ab9c-103">Defines the security capabilities of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="9ab9c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9ab9c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9ab9c-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="9ab9c-105">\<bindings></span></span>  
<span data-ttu-id="9ab9c-106">\<Привязка netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="9ab9c-106">\<netHttpBinding></span></span>  
<span data-ttu-id="9ab9c-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="9ab9c-107">\<binding></span></span>  
<span data-ttu-id="9ab9c-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="9ab9c-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ab9c-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ab9c-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ab9c-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9ab9c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9ab9c-111">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ab9c-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9ab9c-112">Attributes</span></span>  
  
|<span data-ttu-id="9ab9c-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9ab9c-113">Attribute</span></span>|<span data-ttu-id="9ab9c-114">Описание</span><span class="sxs-lookup"><span data-stu-id="9ab9c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9ab9c-115">режим</span><span class="sxs-lookup"><span data-stu-id="9ab9c-115">mode</span></span>|<span data-ttu-id="9ab9c-116">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-116">Optional.</span></span> <span data-ttu-id="9ab9c-117">Задает тип используемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="9ab9c-118">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-118">The default is `None`.</span></span> <span data-ttu-id="9ab9c-119">Этот атрибут имеет тип <!--zz <xref:System.ServiceModel.NetHttpSecurityMode> --> `System.ServiceModel.NetHttpSecurityMode`.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-119">This attribute is of type <!--zz <xref:System.ServiceModel.NetHttpSecurityMode> -->`System.ServiceModel.NetHttpSecurityMode`.</span></span>|
  
## <a name="mode-attribute"></a><span data-ttu-id="9ab9c-120">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="9ab9c-120">mode Attribute</span></span>  
  
|<span data-ttu-id="9ab9c-121">Значение</span><span class="sxs-lookup"><span data-stu-id="9ab9c-121">Value</span></span>|<span data-ttu-id="9ab9c-122">Описание</span><span class="sxs-lookup"><span data-stu-id="9ab9c-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9ab9c-123">Нет</span><span class="sxs-lookup"><span data-stu-id="9ab9c-123">None</span></span>|<span data-ttu-id="9ab9c-124">-Во время передачи сообщения не защищены.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-124">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="9ab9c-125">Transport</span><span class="sxs-lookup"><span data-stu-id="9ab9c-125">Transport</span></span>|<span data-ttu-id="9ab9c-126">Безопасность обеспечивается с помощью транспорта HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="9ab9c-127">Сообщения SOAP защищаются при помощи HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="9ab9c-128">Служба проходит проверку подлинности для клиента с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="9ab9c-129">Проверка подлинности клиента осуществляется с помощью предоставленного ClientCredentialType.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-129">The client is authenticated using the ClientCredentialType supplied.</span></span>|  
|<span data-ttu-id="9ab9c-130">Сообщение</span><span class="sxs-lookup"><span data-stu-id="9ab9c-130">Message</span></span>|<span data-ttu-id="9ab9c-131">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-131">Security is provided using SOAP message security.</span></span> <span data-ttu-id="9ab9c-132">По умолчанию текст сообщений шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-132">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="9ab9c-133">Для этой привязки система требует, чтобы клиенту был предоставлен сертификат сервера с использованием внештатного канала.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-133">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="9ab9c-134">Единственным допустимым значением `ClientCredentialType` для данной привязки является `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-134">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="9ab9c-135">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="9ab9c-135">TransportWithMessageCredential</span></span>|<span data-ttu-id="9ab9c-136">Целостность, конфиденциальность и проверка подлинности сервера обеспечиваются с помощью средств безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-136">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="9ab9c-137">Проверка подлинности клиента осуществляется при помощи механизма безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-137">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="9ab9c-138">Данный режим может использоваться, когда проверка подлинности клиента осуществляется с помощью имени пользователя/пароля и существует развернутый канал HTTP с обеспечением безопасности при передаче сообщений.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-138">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="9ab9c-139">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="9ab9c-139">TransportCredentialOnly</span></span>|<span data-ttu-id="9ab9c-140">Данный режим не обеспечивает целостности и конфиденциальности сообщений.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-140">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="9ab9c-141">Он предоставляет проверку подлинности клиента на основе http.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-141">It provides http-based client authentication.</span></span> <span data-ttu-id="9ab9c-142">Этот режим следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-142">This mode should be used with caution.</span></span> <span data-ttu-id="9ab9c-143">Он должен использоваться в тех средах, где безопасность транспорта обеспечивается другими средствами (например, IPSec), а инфраструктура [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] обеспечивает только проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-143">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ab9c-144">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9ab9c-144">Child Elements</span></span>  
  
|<span data-ttu-id="9ab9c-145">Элемент</span><span class="sxs-lookup"><span data-stu-id="9ab9c-145">Element</span></span>|<span data-ttu-id="9ab9c-146">Описание:</span><span class="sxs-lookup"><span data-stu-id="9ab9c-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ab9c-147">\<transport></span><span class="sxs-lookup"><span data-stu-id="9ab9c-147">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nethttpbinding.md)|<span data-ttu-id="9ab9c-148">Определяет параметры безопасности транспорта для базовой службы HTTP.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-148">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="9ab9c-149">Данный элемент соответствует <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-149">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="9ab9c-150">\<message></span><span class="sxs-lookup"><span data-stu-id="9ab9c-150">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-nethttpbinding.md)|<span data-ttu-id="9ab9c-151">Определяет параметры безопасности сообщений для базовой службы HTTP.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-151">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="9ab9c-152">Этот элемент соответствует <!--zz <xref:System.ServiceModel.NetHttpMessageSecurity> --> `System.ServiceModel.NetHttpMessageSecurity`.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-152">This element corresponds to <!--zz <xref:System.ServiceModel.NetHttpMessageSecurity> --> `System.ServiceModel.NetHttpMessageSecurity`.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9ab9c-153">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9ab9c-153">Parent Elements</span></span>  
  
|<span data-ttu-id="9ab9c-154">Элемент</span><span class="sxs-lookup"><span data-stu-id="9ab9c-154">Element</span></span>|<span data-ttu-id="9ab9c-155">Описание</span><span class="sxs-lookup"><span data-stu-id="9ab9c-155">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9ab9c-156">привязка</span><span class="sxs-lookup"><span data-stu-id="9ab9c-156">binding</span></span>|<span data-ttu-id="9ab9c-157">Элемент привязки для [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="9ab9c-157">The binding element of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ab9c-158">Примечания</span><span class="sxs-lookup"><span data-stu-id="9ab9c-158">Remarks</span></span>  
 <span data-ttu-id="9ab9c-159">По умолчанию сообщение SOAP не защищено и проверка подлинности клиента не выполняется.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-159">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="9ab9c-160">Данный элемент позволяет настроить дополнительные параметры безопасности для элемента `netHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-160">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ab9c-161">См. также</span><span class="sxs-lookup"><span data-stu-id="9ab9c-161">See Also</span></span>  
 <xref:System.ServiceModel.NetHttpBinding.Security%2A>  
 <span data-ttu-id="9ab9c-162"><xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A></span><span class="sxs-lookup"><span data-stu-id="9ab9c-162"><xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A></span></span>    
 [<span data-ttu-id="9ab9c-163">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="9ab9c-163">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="9ab9c-164">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="9ab9c-164">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="9ab9c-165">Привязки</span><span class="sxs-lookup"><span data-stu-id="9ab9c-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="9ab9c-166">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="9ab9c-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="9ab9c-167">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="9ab9c-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="9ab9c-168">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="9ab9c-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
