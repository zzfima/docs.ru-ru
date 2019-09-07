---
title: <security> из <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: 00a933892376c2dc9771752beaf76d4994554968
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399895"
---
# <a name="security-of-basichttpbinding"></a><span data-ttu-id="0469b-102">\<> \<безопасности BasicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="0469b-102">\<security> of \<basicHttpBinding></span></span>
<span data-ttu-id="0469b-103">Определяет возможности [ \<безопасности > BasicHttpBinding](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="0469b-103">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>  
  
<span data-ttu-id="0469b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0469b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0469b-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0469b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0469b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="0469b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="0469b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> basicHttpBinding**](basichttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="0469b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)</span></span>\
<span data-ttu-id="0469b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="0469b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="0469b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> безопасности**</span><span class="sxs-lookup"><span data-stu-id="0469b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0469b-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0469b-110">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0469b-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0469b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0469b-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0469b-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0469b-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0469b-113">Attributes</span></span>  
  
|<span data-ttu-id="0469b-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0469b-114">Attribute</span></span>|<span data-ttu-id="0469b-115">Описание</span><span class="sxs-lookup"><span data-stu-id="0469b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0469b-116">режим</span><span class="sxs-lookup"><span data-stu-id="0469b-116">mode</span></span>|<span data-ttu-id="0469b-117">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="0469b-117">Optional.</span></span> <span data-ttu-id="0469b-118">Задает тип используемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="0469b-118">Specifies the type of security that is used.</span></span> <span data-ttu-id="0469b-119">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="0469b-119">The default is `None`.</span></span> <span data-ttu-id="0469b-120">Это атрибут типа <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="0469b-120">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="0469b-121">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="0469b-121">mode Attribute</span></span>  
  
|<span data-ttu-id="0469b-122">Значение</span><span class="sxs-lookup"><span data-stu-id="0469b-122">Value</span></span>|<span data-ttu-id="0469b-123">Описание</span><span class="sxs-lookup"><span data-stu-id="0469b-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0469b-124">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="0469b-124">None</span></span>|<span data-ttu-id="0469b-125">— Сообщения не защищаются во время перемещения.</span><span class="sxs-lookup"><span data-stu-id="0469b-125">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="0469b-126">Transport</span><span class="sxs-lookup"><span data-stu-id="0469b-126">Transport</span></span>|<span data-ttu-id="0469b-127">Безопасность обеспечивается с помощью транспорта HTTPS.</span><span class="sxs-lookup"><span data-stu-id="0469b-127">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="0469b-128">Сообщения SOAP защищаются при помощи HTTPS.</span><span class="sxs-lookup"><span data-stu-id="0469b-128">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="0469b-129">Служба проходит проверку подлинности для клиента с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="0469b-129">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="0469b-130">Проверка подлинности клиента осуществляется с помощью предоставленного ClientCredentialType.</span><span class="sxs-lookup"><span data-stu-id="0469b-130">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="0469b-131">См. [> транспорта.\<](transport-of-basichttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="0469b-131">See the [\<transport>](transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="0469b-132">Сообщение</span><span class="sxs-lookup"><span data-stu-id="0469b-132">Message</span></span>|<span data-ttu-id="0469b-133">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="0469b-133">Security is provided using SOAP message security.</span></span> <span data-ttu-id="0469b-134">По умолчанию текст сообщений шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="0469b-134">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="0469b-135">Для этой привязки система требует, чтобы клиенту был предоставлен сертификат сервера с использованием внештатного канала.</span><span class="sxs-lookup"><span data-stu-id="0469b-135">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="0469b-136">Единственным допустимым значением `ClientCredentialType` для данной привязки является `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="0469b-136">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="0469b-137">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="0469b-137">TransportWithMessageCredential</span></span>|<span data-ttu-id="0469b-138">Целостность, конфиденциальность и проверка подлинности сервера обеспечиваются с помощью средств безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="0469b-138">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="0469b-139">Проверка подлинности клиента осуществляется при помощи механизма безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="0469b-139">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="0469b-140">Данный режим может использоваться, когда проверка подлинности клиента осуществляется с помощью имени пользователя/пароля и существует развернутый канал HTTP с обеспечением безопасности при передаче сообщений.</span><span class="sxs-lookup"><span data-stu-id="0469b-140">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="0469b-141">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="0469b-141">TransportCredentialOnly</span></span>|<span data-ttu-id="0469b-142">Данный режим не обеспечивает целостности и конфиденциальности сообщений.</span><span class="sxs-lookup"><span data-stu-id="0469b-142">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="0469b-143">Он предоставляет проверку подлинности клиента на основе http.</span><span class="sxs-lookup"><span data-stu-id="0469b-143">It provides http-based client authentication.</span></span> <span data-ttu-id="0469b-144">Этот режим следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="0469b-144">This mode should be used with caution.</span></span> <span data-ttu-id="0469b-145">Он должен использоваться в средах, где безопасность транспорта предоставляется другими средствами (например, IPSec), а инфраструктура WCF предоставляет только проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="0469b-145">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0469b-146">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0469b-146">Child Elements</span></span>  
  
|<span data-ttu-id="0469b-147">Элемент</span><span class="sxs-lookup"><span data-stu-id="0469b-147">Element</span></span>|<span data-ttu-id="0469b-148">Описание</span><span class="sxs-lookup"><span data-stu-id="0469b-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0469b-149">\<> транспорта</span><span class="sxs-lookup"><span data-stu-id="0469b-149">\<transport></span></span>](transport-of-basichttpbinding.md)|<span data-ttu-id="0469b-150">Определяет параметры безопасности транспорта для базовой службы HTTP.</span><span class="sxs-lookup"><span data-stu-id="0469b-150">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="0469b-151">Данный элемент соответствует <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="0469b-151">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="0469b-152">\<> сообщения</span><span class="sxs-lookup"><span data-stu-id="0469b-152">\<message></span></span>](message-of-basichttpbinding.md)|<span data-ttu-id="0469b-153">Определяет параметры безопасности сообщений для базовой службы HTTP.</span><span class="sxs-lookup"><span data-stu-id="0469b-153">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="0469b-154">Данный элемент соответствует <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="0469b-154">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0469b-155">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0469b-155">Parent Elements</span></span>  
  
|<span data-ttu-id="0469b-156">Элемент</span><span class="sxs-lookup"><span data-stu-id="0469b-156">Element</span></span>|<span data-ttu-id="0469b-157">Описание</span><span class="sxs-lookup"><span data-stu-id="0469b-157">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0469b-158">привязка</span><span class="sxs-lookup"><span data-stu-id="0469b-158">binding</span></span>|<span data-ttu-id="0469b-159">[ Элемент\<Binding > BasicHttpBinding](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="0469b-159">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0469b-160">Примечания</span><span class="sxs-lookup"><span data-stu-id="0469b-160">Remarks</span></span>  
 <span data-ttu-id="0469b-161">По умолчанию сообщение SOAP не защищено и проверка подлинности клиента не выполняется.</span><span class="sxs-lookup"><span data-stu-id="0469b-161">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="0469b-162">Данный элемент позволяет настроить дополнительные параметры безопасности для элемента `basicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="0469b-162">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0469b-163">См. также</span><span class="sxs-lookup"><span data-stu-id="0469b-163">See also</span></span>

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="0469b-164">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="0469b-164">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0469b-165">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="0469b-165">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="0469b-166">Привязки</span><span class="sxs-lookup"><span data-stu-id="0469b-166">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0469b-167">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="0469b-167">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0469b-168">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="0469b-168">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="0469b-169">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="0469b-169">\<binding></span></span>](../../../misc/binding.md)
