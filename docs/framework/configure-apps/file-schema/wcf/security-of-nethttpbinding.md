---
title: <security> из <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: 97c52fa4f062ed0c65d5b1a8ca47a1439ab04cf5
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736490"
---
# <a name="security-of-nethttpbinding"></a><span data-ttu-id="701f1-102">\<> безопасности \<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="701f1-102">\<security> of \<netHttpBinding></span></span>

<span data-ttu-id="701f1-103">Определяет возможности безопасности [\<netHttpBinding >](nethttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="701f1-103">Defines the security capabilities of the [\<netHttpBinding>](nethttpbinding.md).</span></span>

<span data-ttu-id="701f1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="701f1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="701f1-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="701f1-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="701f1-106">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="701f1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="701f1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netHttpBinding >** ](nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="701f1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="701f1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="701f1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="701f1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<security >**</span><span class="sxs-lookup"><span data-stu-id="701f1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="701f1-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="701f1-110">Syntax</span></span>

```xml
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="701f1-111">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="701f1-111">Attributes and elements</span></span>

<span data-ttu-id="701f1-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="701f1-112">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="701f1-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="701f1-113">Attributes</span></span>

|<span data-ttu-id="701f1-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="701f1-114">Attribute</span></span>|<span data-ttu-id="701f1-115">Описание</span><span class="sxs-lookup"><span data-stu-id="701f1-115">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="701f1-116">режим</span><span class="sxs-lookup"><span data-stu-id="701f1-116">mode</span></span>|<span data-ttu-id="701f1-117">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="701f1-117">Optional.</span></span> <span data-ttu-id="701f1-118">Задает тип используемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="701f1-118">Specifies the type of security that is used.</span></span> <span data-ttu-id="701f1-119">Значение по умолчанию: `None`.</span><span class="sxs-lookup"><span data-stu-id="701f1-119">The default is `None`.</span></span> <span data-ttu-id="701f1-120">Это атрибут типа <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="701f1-120">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|

## <a name="mode-attribute"></a><span data-ttu-id="701f1-121">атрибут mode</span><span class="sxs-lookup"><span data-stu-id="701f1-121">mode attribute</span></span>

|<span data-ttu-id="701f1-122">значения</span><span class="sxs-lookup"><span data-stu-id="701f1-122">Value</span></span>|<span data-ttu-id="701f1-123">Описание</span><span class="sxs-lookup"><span data-stu-id="701f1-123">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="701f1-124">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="701f1-124">None</span></span>|<span data-ttu-id="701f1-125">— Сообщения не защищаются во время перемещения.</span><span class="sxs-lookup"><span data-stu-id="701f1-125">-   Messages are not secured during transfer.</span></span>|
|<span data-ttu-id="701f1-126">Transport</span><span class="sxs-lookup"><span data-stu-id="701f1-126">Transport</span></span>|<span data-ttu-id="701f1-127">Безопасность обеспечивается с помощью транспорта HTTPS.</span><span class="sxs-lookup"><span data-stu-id="701f1-127">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="701f1-128">Сообщения SOAP защищаются при помощи HTTPS.</span><span class="sxs-lookup"><span data-stu-id="701f1-128">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="701f1-129">Служба проходит проверку подлинности для клиента с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="701f1-129">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="701f1-130">Проверка подлинности клиента осуществляется с помощью предоставленного ClientCredentialType.</span><span class="sxs-lookup"><span data-stu-id="701f1-130">The client is authenticated using the ClientCredentialType supplied.</span></span>|
|<span data-ttu-id="701f1-131">Сообщение</span><span class="sxs-lookup"><span data-stu-id="701f1-131">Message</span></span>|<span data-ttu-id="701f1-132">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="701f1-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="701f1-133">По умолчанию текст сообщений шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="701f1-133">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="701f1-134">Для этой привязки система требует, чтобы клиенту был предоставлен сертификат сервера с использованием внештатного канала.</span><span class="sxs-lookup"><span data-stu-id="701f1-134">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="701f1-135">Единственным допустимым значением `ClientCredentialType` для данной привязки является `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="701f1-135">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|
|<span data-ttu-id="701f1-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="701f1-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="701f1-137">Целостность, конфиденциальность и проверка подлинности сервера обеспечиваются с помощью средств безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="701f1-137">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="701f1-138">Проверка подлинности клиента осуществляется при помощи механизма безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="701f1-138">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="701f1-139">Данный режим может использоваться, когда проверка подлинности клиента осуществляется с помощью имени пользователя/пароля и существует развернутый канал HTTP с обеспечением безопасности при передаче сообщений.</span><span class="sxs-lookup"><span data-stu-id="701f1-139">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|
|<span data-ttu-id="701f1-140">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="701f1-140">TransportCredentialOnly</span></span>|<span data-ttu-id="701f1-141">Данный режим не обеспечивает целостности и конфиденциальности сообщений.</span><span class="sxs-lookup"><span data-stu-id="701f1-141">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="701f1-142">Он предоставляет проверку подлинности клиента на основе http.</span><span class="sxs-lookup"><span data-stu-id="701f1-142">It provides http-based client authentication.</span></span> <span data-ttu-id="701f1-143">Этот режим следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="701f1-143">This mode should be used with caution.</span></span> <span data-ttu-id="701f1-144">Он должен использоваться в средах, где безопасность транспорта предоставляется другими средствами (например, IPSec), а инфраструктура WCF предоставляет только проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="701f1-144">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="701f1-145">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="701f1-145">Child elements</span></span>

|<span data-ttu-id="701f1-146">Элемент</span><span class="sxs-lookup"><span data-stu-id="701f1-146">Element</span></span>|<span data-ttu-id="701f1-147">Описание</span><span class="sxs-lookup"><span data-stu-id="701f1-147">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="701f1-148">\<> транспорта</span><span class="sxs-lookup"><span data-stu-id="701f1-148">\<transport></span></span>](transport-of-nethttpbinding.md)|<span data-ttu-id="701f1-149">Определяет параметры безопасности транспорта для базовой службы HTTP.</span><span class="sxs-lookup"><span data-stu-id="701f1-149">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="701f1-150">Данный элемент соответствует <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="701f1-150">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|
|[<span data-ttu-id="701f1-151">сообщение \<</span><span class="sxs-lookup"><span data-stu-id="701f1-151">\<message></span></span>](message-of-nethttpbinding.md)|<span data-ttu-id="701f1-152">Определяет параметры безопасности сообщений для базовой службы HTTP.</span><span class="sxs-lookup"><span data-stu-id="701f1-152">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="701f1-153">Данный элемент соответствует <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="701f1-153">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="701f1-154">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="701f1-154">Parent elements</span></span>

|<span data-ttu-id="701f1-155">Элемент</span><span class="sxs-lookup"><span data-stu-id="701f1-155">Element</span></span>|<span data-ttu-id="701f1-156">Описание</span><span class="sxs-lookup"><span data-stu-id="701f1-156">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="701f1-157">привязка</span><span class="sxs-lookup"><span data-stu-id="701f1-157">binding</span></span>|<span data-ttu-id="701f1-158">Элемент Binding [\<basicHttpBinding >](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="701f1-158">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|

## <a name="remarks"></a><span data-ttu-id="701f1-159">Заметки</span><span class="sxs-lookup"><span data-stu-id="701f1-159">Remarks</span></span>

 <span data-ttu-id="701f1-160">По умолчанию сообщение SOAP не защищено и проверка подлинности клиента не выполняется.</span><span class="sxs-lookup"><span data-stu-id="701f1-160">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="701f1-161">Данный элемент позволяет настроить дополнительные параметры безопасности для элемента `netHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="701f1-161">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="701f1-162">См. также</span><span class="sxs-lookup"><span data-stu-id="701f1-162">See also</span></span>

- <xref:System.ServiceModel.NetHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>  
- [<span data-ttu-id="701f1-163">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="701f1-163">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="701f1-164">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="701f1-164">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="701f1-165">Привязки</span><span class="sxs-lookup"><span data-stu-id="701f1-165">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="701f1-166">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="701f1-166">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="701f1-167">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="701f1-167">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="701f1-168">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="701f1-168">\<binding></span></span>](bindings.md)
