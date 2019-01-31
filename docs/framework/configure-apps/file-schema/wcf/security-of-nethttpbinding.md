---
title: <security> из <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: f2750036aa4d3fbe41062ad041e50ff3a4be32b5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283975"
---
# <a name="security-of-nethttpbinding"></a><span data-ttu-id="be637-102">\<Безопасность > из \<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="be637-102">\<security> of \<netHttpBinding></span></span>

<span data-ttu-id="be637-103">Определяет возможности безопасности [ \<basicHttpBinding >](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="be637-103">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>

<span data-ttu-id="be637-104">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="be637-104">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="be637-105">\<привязки > \\</span><span class="sxs-lookup"><span data-stu-id="be637-105">\<bindings>\\</span></span>
<span data-ttu-id="be637-106">\<netHttpBinding > \\</span><span class="sxs-lookup"><span data-stu-id="be637-106">\<netHttpBinding>\\</span></span>
<span data-ttu-id="be637-107">\<Привязка > \\</span><span class="sxs-lookup"><span data-stu-id="be637-107">\<binding>\\</span></span>
<span data-ttu-id="be637-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="be637-108">\<security></span></span>

## <a name="syntax"></a><span data-ttu-id="be637-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be637-109">Syntax</span></span>

```xml
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="be637-110">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="be637-110">Attributes and elements</span></span>

<span data-ttu-id="be637-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="be637-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="be637-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="be637-112">Attributes</span></span>

|<span data-ttu-id="be637-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="be637-113">Attribute</span></span>|<span data-ttu-id="be637-114">Описание</span><span class="sxs-lookup"><span data-stu-id="be637-114">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="be637-115">режим</span><span class="sxs-lookup"><span data-stu-id="be637-115">mode</span></span>|<span data-ttu-id="be637-116">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="be637-116">Optional.</span></span> <span data-ttu-id="be637-117">Задает тип используемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="be637-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="be637-118">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="be637-118">The default is `None`.</span></span> <span data-ttu-id="be637-119">Это атрибут типа <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="be637-119">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|

## <a name="mode-attribute"></a><span data-ttu-id="be637-120">Атрибут Mode</span><span class="sxs-lookup"><span data-stu-id="be637-120">mode attribute</span></span>

|<span data-ttu-id="be637-121">Значение</span><span class="sxs-lookup"><span data-stu-id="be637-121">Value</span></span>|<span data-ttu-id="be637-122">Описание</span><span class="sxs-lookup"><span data-stu-id="be637-122">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="be637-123">Нет</span><span class="sxs-lookup"><span data-stu-id="be637-123">None</span></span>|<span data-ttu-id="be637-124">-Сообщения не защищены во время передачи.</span><span class="sxs-lookup"><span data-stu-id="be637-124">-   Messages are not secured during transfer.</span></span>|
|<span data-ttu-id="be637-125">Transport</span><span class="sxs-lookup"><span data-stu-id="be637-125">Transport</span></span>|<span data-ttu-id="be637-126">Безопасность обеспечивается с помощью транспорта HTTPS.</span><span class="sxs-lookup"><span data-stu-id="be637-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="be637-127">Сообщения SOAP защищаются при помощи HTTPS.</span><span class="sxs-lookup"><span data-stu-id="be637-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="be637-128">Служба проходит проверку подлинности для клиента с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="be637-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="be637-129">Проверка подлинности клиента осуществляется с помощью предоставленного ClientCredentialType.</span><span class="sxs-lookup"><span data-stu-id="be637-129">The client is authenticated using the ClientCredentialType supplied.</span></span>|
|<span data-ttu-id="be637-130">Сообщение</span><span class="sxs-lookup"><span data-stu-id="be637-130">Message</span></span>|<span data-ttu-id="be637-131">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="be637-131">Security is provided using SOAP message security.</span></span> <span data-ttu-id="be637-132">По умолчанию текст сообщений шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="be637-132">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="be637-133">Для этой привязки система требует, чтобы клиенту был предоставлен сертификат сервера с использованием внештатного канала.</span><span class="sxs-lookup"><span data-stu-id="be637-133">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="be637-134">Единственным допустимым значением `ClientCredentialType` для данной привязки является `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="be637-134">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|
|<span data-ttu-id="be637-135">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="be637-135">TransportWithMessageCredential</span></span>|<span data-ttu-id="be637-136">Целостность, конфиденциальность и проверка подлинности сервера обеспечиваются с помощью средств безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="be637-136">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="be637-137">Проверка подлинности клиента осуществляется при помощи механизма безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="be637-137">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="be637-138">Данный режим может использоваться, когда проверка подлинности клиента осуществляется с помощью имени пользователя/пароля и существует развернутый канал HTTP с обеспечением безопасности при передаче сообщений.</span><span class="sxs-lookup"><span data-stu-id="be637-138">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|
|<span data-ttu-id="be637-139">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="be637-139">TransportCredentialOnly</span></span>|<span data-ttu-id="be637-140">Данный режим не обеспечивает целостности и конфиденциальности сообщений.</span><span class="sxs-lookup"><span data-stu-id="be637-140">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="be637-141">Он предоставляет проверку подлинности клиента на основе http.</span><span class="sxs-lookup"><span data-stu-id="be637-141">It provides http-based client authentication.</span></span> <span data-ttu-id="be637-142">Этот режим следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="be637-142">This mode should be used with caution.</span></span> <span data-ttu-id="be637-143">Он должен использоваться в средах, где безопасность транспорта обеспечивается другими средствами (например, IPSec), а только проверку подлинности клиента с помощью инфраструктуры WCF.</span><span class="sxs-lookup"><span data-stu-id="be637-143">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="be637-144">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="be637-144">Child elements</span></span>

|<span data-ttu-id="be637-145">Элемент</span><span class="sxs-lookup"><span data-stu-id="be637-145">Element</span></span>|<span data-ttu-id="be637-146">Описание:</span><span class="sxs-lookup"><span data-stu-id="be637-146">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="be637-147">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="be637-147">\<transport></span></span>](transport-of-nethttpbinding.md)|<span data-ttu-id="be637-148">Определяет параметры безопасности транспорта для базовой службы HTTP.</span><span class="sxs-lookup"><span data-stu-id="be637-148">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="be637-149">Данный элемент соответствует <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="be637-149">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|
|[<span data-ttu-id="be637-150">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="be637-150">\<message></span></span>](message-of-nethttpbinding.md)|<span data-ttu-id="be637-151">Определяет параметры безопасности сообщений для базовой службы HTTP.</span><span class="sxs-lookup"><span data-stu-id="be637-151">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="be637-152">Данный элемент соответствует <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="be637-152">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="be637-153">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="be637-153">Parent elements</span></span>

|<span data-ttu-id="be637-154">Элемент</span><span class="sxs-lookup"><span data-stu-id="be637-154">Element</span></span>|<span data-ttu-id="be637-155">Описание</span><span class="sxs-lookup"><span data-stu-id="be637-155">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="be637-156">привязка</span><span class="sxs-lookup"><span data-stu-id="be637-156">binding</span></span>|<span data-ttu-id="be637-157">Элемент привязки [ \<basicHttpBinding >](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="be637-157">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|

## <a name="remarks"></a><span data-ttu-id="be637-158">Примечания</span><span class="sxs-lookup"><span data-stu-id="be637-158">Remarks</span></span>

 <span data-ttu-id="be637-159">По умолчанию сообщение SOAP не защищено и проверка подлинности клиента не выполняется.</span><span class="sxs-lookup"><span data-stu-id="be637-159">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="be637-160">Данный элемент позволяет настроить дополнительные параметры безопасности для элемента `netHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="be637-160">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="be637-161">См. также</span><span class="sxs-lookup"><span data-stu-id="be637-161">See also</span></span>

- <xref:System.ServiceModel.NetHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>  
- [<span data-ttu-id="be637-162">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="be637-162">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="be637-163">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="be637-163">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="be637-164">Привязки</span><span class="sxs-lookup"><span data-stu-id="be637-164">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="be637-165">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="be637-165">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="be637-166">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="be637-166">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="be637-167">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="be637-167">\<binding></span></span>](../../../misc/binding.md)
