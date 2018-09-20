---
title: '&lt;security&gt; для &lt;basicHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 2adb5736cca59d42ab3c62d61513bbfd80a4be04
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2018
ms.locfileid: "46480530"
---
# <a name="ltsecuritygt-of-ltbasichttpbindinggt"></a><span data-ttu-id="3eddd-102">&lt;security&gt; для &lt;basicHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="3eddd-102">&lt;security&gt; of &lt;basicHttpBinding&gt;</span></span>
<span data-ttu-id="3eddd-103">Определяет возможности безопасности [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="3eddd-103">Defines the security capabilities of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="3eddd-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3eddd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3eddd-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="3eddd-105">\<bindings></span></span>  
<span data-ttu-id="3eddd-106">\<basicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="3eddd-106">\<basicHttpBinding></span></span>  
<span data-ttu-id="3eddd-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="3eddd-107">\<binding></span></span>  
<span data-ttu-id="3eddd-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="3eddd-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eddd-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3eddd-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3eddd-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3eddd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3eddd-111">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3eddd-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3eddd-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3eddd-112">Attributes</span></span>  
  
|<span data-ttu-id="3eddd-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3eddd-113">Attribute</span></span>|<span data-ttu-id="3eddd-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3eddd-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3eddd-115">режим</span><span class="sxs-lookup"><span data-stu-id="3eddd-115">mode</span></span>|<span data-ttu-id="3eddd-116">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="3eddd-116">Optional.</span></span> <span data-ttu-id="3eddd-117">Задает тип используемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="3eddd-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="3eddd-118">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="3eddd-118">The default is `None`.</span></span> <span data-ttu-id="3eddd-119">Это атрибут типа <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="3eddd-119">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="3eddd-120">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="3eddd-120">mode Attribute</span></span>  
  
|<span data-ttu-id="3eddd-121">Значение</span><span class="sxs-lookup"><span data-stu-id="3eddd-121">Value</span></span>|<span data-ttu-id="3eddd-122">Описание</span><span class="sxs-lookup"><span data-stu-id="3eddd-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3eddd-123">Нет</span><span class="sxs-lookup"><span data-stu-id="3eddd-123">None</span></span>|<span data-ttu-id="3eddd-124">-Сообщения не защищены во время передачи.</span><span class="sxs-lookup"><span data-stu-id="3eddd-124">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="3eddd-125">Transport</span><span class="sxs-lookup"><span data-stu-id="3eddd-125">Transport</span></span>|<span data-ttu-id="3eddd-126">Безопасность обеспечивается с помощью транспорта HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3eddd-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="3eddd-127">Сообщения SOAP защищаются при помощи HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3eddd-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="3eddd-128">Служба проходит проверку подлинности для клиента с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="3eddd-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="3eddd-129">Проверка подлинности клиента осуществляется с помощью предоставленного ClientCredentialType.</span><span class="sxs-lookup"><span data-stu-id="3eddd-129">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="3eddd-130">См. в разделе [ \<транспорта >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="3eddd-130">See the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="3eddd-131">Сообщение</span><span class="sxs-lookup"><span data-stu-id="3eddd-131">Message</span></span>|<span data-ttu-id="3eddd-132">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="3eddd-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="3eddd-133">По умолчанию текст сообщений шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="3eddd-133">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="3eddd-134">Для этой привязки система требует, чтобы клиенту был предоставлен сертификат сервера с использованием внештатного канала.</span><span class="sxs-lookup"><span data-stu-id="3eddd-134">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="3eddd-135">Единственным допустимым значением `ClientCredentialType` для данной привязки является `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="3eddd-135">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="3eddd-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="3eddd-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="3eddd-137">Целостность, конфиденциальность и проверка подлинности сервера обеспечиваются с помощью средств безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="3eddd-137">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="3eddd-138">Проверка подлинности клиента осуществляется при помощи механизма безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="3eddd-138">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="3eddd-139">Данный режим может использоваться, когда проверка подлинности клиента осуществляется с помощью имени пользователя/пароля и существует развернутый канал HTTP с обеспечением безопасности при передаче сообщений.</span><span class="sxs-lookup"><span data-stu-id="3eddd-139">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="3eddd-140">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="3eddd-140">TransportCredentialOnly</span></span>|<span data-ttu-id="3eddd-141">Данный режим не обеспечивает целостности и конфиденциальности сообщений.</span><span class="sxs-lookup"><span data-stu-id="3eddd-141">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="3eddd-142">Он предоставляет проверку подлинности клиента на основе http.</span><span class="sxs-lookup"><span data-stu-id="3eddd-142">It provides http-based client authentication.</span></span> <span data-ttu-id="3eddd-143">Этот режим следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="3eddd-143">This mode should be used with caution.</span></span> <span data-ttu-id="3eddd-144">Он должен использоваться в средах, где безопасность транспорта обеспечивается другими средствами (например, IPSec), а только проверку подлинности клиента с помощью инфраструктуры WCF.</span><span class="sxs-lookup"><span data-stu-id="3eddd-144">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3eddd-145">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3eddd-145">Child Elements</span></span>  
  
|<span data-ttu-id="3eddd-146">Элемент</span><span class="sxs-lookup"><span data-stu-id="3eddd-146">Element</span></span>|<span data-ttu-id="3eddd-147">Описание</span><span class="sxs-lookup"><span data-stu-id="3eddd-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3eddd-148">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="3eddd-148">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)|<span data-ttu-id="3eddd-149">Определяет параметры безопасности транспорта для базовой службы HTTP.</span><span class="sxs-lookup"><span data-stu-id="3eddd-149">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="3eddd-150">Данный элемент соответствует <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="3eddd-150">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="3eddd-151">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="3eddd-151">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-basichttpbinding.md)|<span data-ttu-id="3eddd-152">Определяет параметры безопасности сообщений для базовой службы HTTP.</span><span class="sxs-lookup"><span data-stu-id="3eddd-152">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="3eddd-153">Данный элемент соответствует <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="3eddd-153">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3eddd-154">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3eddd-154">Parent Elements</span></span>  
  
|<span data-ttu-id="3eddd-155">Элемент</span><span class="sxs-lookup"><span data-stu-id="3eddd-155">Element</span></span>|<span data-ttu-id="3eddd-156">Описание</span><span class="sxs-lookup"><span data-stu-id="3eddd-156">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3eddd-157">привязка</span><span class="sxs-lookup"><span data-stu-id="3eddd-157">binding</span></span>|<span data-ttu-id="3eddd-158">Элемент привязки [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="3eddd-158">The binding element of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3eddd-159">Примечания</span><span class="sxs-lookup"><span data-stu-id="3eddd-159">Remarks</span></span>  
 <span data-ttu-id="3eddd-160">По умолчанию сообщение SOAP не защищено и проверка подлинности клиента не выполняется.</span><span class="sxs-lookup"><span data-stu-id="3eddd-160">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="3eddd-161">Данный элемент позволяет настроить дополнительные параметры безопасности для элемента `basicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="3eddd-161">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eddd-162">См. также</span><span class="sxs-lookup"><span data-stu-id="3eddd-162">See Also</span></span>  
 <xref:System.ServiceModel.BasicHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="3eddd-163">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="3eddd-163">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="3eddd-164">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="3eddd-164">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="3eddd-165">Привязки</span><span class="sxs-lookup"><span data-stu-id="3eddd-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="3eddd-166">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="3eddd-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="3eddd-167">Использование привязок для настройки службы Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="3eddd-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="3eddd-168">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="3eddd-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
