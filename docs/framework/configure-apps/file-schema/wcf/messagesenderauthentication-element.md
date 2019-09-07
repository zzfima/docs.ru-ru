---
title: Элемент <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: bab0e50d7feba3ea55d505be07cfa41427a5cbbc
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397790"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="fd67f-102">\<Элемент > Мессажесендераусентикатион</span><span class="sxs-lookup"><span data-stu-id="fd67f-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="fd67f-103">Задает параметры проверки подлинности для одноранговых отправителей сообщений.</span><span class="sxs-lookup"><span data-stu-id="fd67f-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="fd67f-104">Дополнительные сведения о одноранговых программах см. в разделе одноранговая [сеть](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="fd67f-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
<span data-ttu-id="fd67f-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fd67f-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fd67f-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fd67f-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fd67f-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="fd67f-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="fd67f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="fd67f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="fd67f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="fd67f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="fd67f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="fd67f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="fd67f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Одноранговые >** ](peer-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="fd67f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="fd67f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Мессажесендераусентикатион >**</span><span class="sxs-lookup"><span data-stu-id="fd67f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd67f-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd67f-113">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd67f-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fd67f-114">Attributes and Elements</span></span>  
 <span data-ttu-id="fd67f-115">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fd67f-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd67f-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fd67f-116">Attributes</span></span>  
  
|<span data-ttu-id="fd67f-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fd67f-117">Attribute</span></span>|<span data-ttu-id="fd67f-118">Описание</span><span class="sxs-lookup"><span data-stu-id="fd67f-118">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="fd67f-119">Тип и сборка, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="fd67f-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="fd67f-120">Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="fd67f-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="fd67f-121">Задает один из трех режимов для проверки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="fd67f-121">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="fd67f-122">Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="fd67f-122">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="fd67f-123">Один из режимов, используемых для проверки списков отозванных сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="fd67f-123">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="fd67f-124">Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="fd67f-124">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="fd67f-125">Данное значение используется при согласовании сертификата службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="fd67f-125">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="fd67f-126">Проверка выполняется для хранилища **доверенных лиц** в указанном расположении магазина.</span><span class="sxs-lookup"><span data-stu-id="fd67f-126">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="fd67f-127">Атрибут customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="fd67f-127">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="fd67f-128">Значение</span><span class="sxs-lookup"><span data-stu-id="fd67f-128">Value</span></span>|<span data-ttu-id="fd67f-129">Описание</span><span class="sxs-lookup"><span data-stu-id="fd67f-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fd67f-130">String</span><span class="sxs-lookup"><span data-stu-id="fd67f-130">String</span></span>|<span data-ttu-id="fd67f-131">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="fd67f-131">Optional.</span></span> <span data-ttu-id="fd67f-132">Задает имя типа и сборку, а также другие данные, используемые для поиска типа.</span><span class="sxs-lookup"><span data-stu-id="fd67f-132">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="fd67f-133">Требуется, как минимум, пространство имен и имя типа.</span><span class="sxs-lookup"><span data-stu-id="fd67f-133">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="fd67f-134">К дополнительным сведениям относятся: имя сборки, номер версии, язык и региональные параметры и маркер открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="fd67f-134">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="fd67f-135">Атрибут certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="fd67f-135">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="fd67f-136">Значение</span><span class="sxs-lookup"><span data-stu-id="fd67f-136">Value</span></span>|<span data-ttu-id="fd67f-137">Описание</span><span class="sxs-lookup"><span data-stu-id="fd67f-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fd67f-138">Перечисление</span><span class="sxs-lookup"><span data-stu-id="fd67f-138">Enumeration</span></span>|<span data-ttu-id="fd67f-139">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="fd67f-139">Optional.</span></span> <span data-ttu-id="fd67f-140">Одно из следующих значений: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="fd67f-140">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="fd67f-141">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="fd67f-141">The default is `ChainTrust`.</span></span> <span data-ttu-id="fd67f-142">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="fd67f-142">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="fd67f-143">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="fd67f-143">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="fd67f-144">Атрибут revocationMode</span><span class="sxs-lookup"><span data-stu-id="fd67f-144">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="fd67f-145">Значение</span><span class="sxs-lookup"><span data-stu-id="fd67f-145">Value</span></span>|<span data-ttu-id="fd67f-146">Описание</span><span class="sxs-lookup"><span data-stu-id="fd67f-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fd67f-147">Перечисление</span><span class="sxs-lookup"><span data-stu-id="fd67f-147">Enumeration</span></span>|<span data-ttu-id="fd67f-148">Одно из следующих значений: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="fd67f-148">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="fd67f-149">Значение по умолчанию — `Online`.</span><span class="sxs-lookup"><span data-stu-id="fd67f-149">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="fd67f-150">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="fd67f-150">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="fd67f-151">Атрибут trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="fd67f-151">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="fd67f-152">Значение</span><span class="sxs-lookup"><span data-stu-id="fd67f-152">Value</span></span>|<span data-ttu-id="fd67f-153">Описание</span><span class="sxs-lookup"><span data-stu-id="fd67f-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fd67f-154">Перечисление</span><span class="sxs-lookup"><span data-stu-id="fd67f-154">Enumeration</span></span>|<span data-ttu-id="fd67f-155">Одно из следующих значений: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="fd67f-155">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="fd67f-156">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="fd67f-156">The default is `CurrentUser`.</span></span> <span data-ttu-id="fd67f-157">Если клиентское приложение выполняется под учетной записью системы, сертификат обычно находится в расположении `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="fd67f-157">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="fd67f-158">Если клиентское приложение выполняется под учетной записью пользователя, то сертификат обычно находится в расположении `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="fd67f-158">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="fd67f-159">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="fd67f-159">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fd67f-160">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fd67f-160">Child Elements</span></span>  
 <span data-ttu-id="fd67f-161">Нет.</span><span class="sxs-lookup"><span data-stu-id="fd67f-161">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fd67f-162">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fd67f-162">Parent Elements</span></span>  
  
|<span data-ttu-id="fd67f-163">Элемент</span><span class="sxs-lookup"><span data-stu-id="fd67f-163">Element</span></span>|<span data-ttu-id="fd67f-164">Описание</span><span class="sxs-lookup"><span data-stu-id="fd67f-164">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd67f-165">\<Одноранговые ></span><span class="sxs-lookup"><span data-stu-id="fd67f-165">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="fd67f-166">Задает учетные данные, используемые для проверки подлинности клиента при подключении к одноранговой службе.</span><span class="sxs-lookup"><span data-stu-id="fd67f-166">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd67f-167">Примечания</span><span class="sxs-lookup"><span data-stu-id="fd67f-167">Remarks</span></span>  
 <span data-ttu-id="fd67f-168">Этот элемент должен быть настроен, если выбрана проверка подлинности сообщения.</span><span class="sxs-lookup"><span data-stu-id="fd67f-168">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="fd67f-169">Для выходных каналов каждое сообщение подписывается с помощью сертификата, [ \<предоставленного сертификатом >](certificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="fd67f-169">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="fd67f-170">Во всех сообщениях перед доставкой приложению проверяются учетные данные сообщения с помощью модуля проверки, заданного атрибутом `customCertificateValidatorType` этого элемента.</span><span class="sxs-lookup"><span data-stu-id="fd67f-170">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="fd67f-171">Модуль проверки может принять или отклонить учетные данные.</span><span class="sxs-lookup"><span data-stu-id="fd67f-171">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd67f-172">Пример</span><span class="sxs-lookup"><span data-stu-id="fd67f-172">Example</span></span>  
 <span data-ttu-id="fd67f-173">В приведенном ниже примере кода устанавливается режим проверки отправителя сообщения `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="fd67f-173">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <messageSenderAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="fd67f-174">См. также</span><span class="sxs-lookup"><span data-stu-id="fd67f-174">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="fd67f-175">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="fd67f-175">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="fd67f-176">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="fd67f-176">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="fd67f-177">[Проверка подлинности сообщений однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="fd67f-177">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="fd67f-178">[Пользовательская проверка подлинности однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="fd67f-178">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="fd67f-179">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="fd67f-179">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
