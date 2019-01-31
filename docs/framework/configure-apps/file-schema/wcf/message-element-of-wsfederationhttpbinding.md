---
title: Элемент <message> для <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: 3e3b48476f2928bc1daecfb1c2f9989bbb2e5f33
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55274174"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="dd963-102">\<сообщение > элемент \<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="dd963-102">\<message> element of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="dd963-103">Определяет параметры безопасности уровня сообщений для [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="dd963-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="dd963-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="dd963-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dd963-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="dd963-105">\<bindings></span></span>  
<span data-ttu-id="dd963-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="dd963-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="dd963-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="dd963-107">\<binding></span></span>  
<span data-ttu-id="dd963-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="dd963-108">\<security></span></span>  
<span data-ttu-id="dd963-109">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="dd963-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd963-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd963-110">Syntax</span></span>  
  
```xml  
<wsFederationBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
        <issuer address="Uri">
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuer>
        <issuerMetadata address="String">
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuerMetadata>
        <tokenRequestParameters>
          <xmlElement>
          </xmlElement>
        </tokenRequestParameters>
      </message>
    </security>
  </binding>
</wsFederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd963-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dd963-111">Attributes and Elements</span></span>  
 <span data-ttu-id="dd963-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dd963-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd963-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dd963-113">Attributes</span></span>  
  
|<span data-ttu-id="dd963-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dd963-114">Attribute</span></span>|<span data-ttu-id="dd963-115">Описание</span><span class="sxs-lookup"><span data-stu-id="dd963-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dd963-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="dd963-116">algorithmSuite</span></span>|<span data-ttu-id="dd963-117">Задает алгоритмы шифрования сообщений и ключей.</span><span class="sxs-lookup"><span data-stu-id="dd963-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="dd963-118">Допустимые значения этого атрибута см. в таблице «Атрибут algorithmSuite».</span><span class="sxs-lookup"><span data-stu-id="dd963-118">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="dd963-119">Значение по умолчанию — `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="dd963-119">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="dd963-120">Это атрибут типа <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="dd963-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="dd963-121">Эти алгоритмы соответствуют алгоритмам, заданным в спецификации языка политики безопасности (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="dd963-121">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="dd963-122">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="dd963-122">issuedKeyType</span></span>|<span data-ttu-id="dd963-123">Задает тип выдаваемого ключа.</span><span class="sxs-lookup"><span data-stu-id="dd963-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="dd963-124">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="dd963-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="dd963-125">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="dd963-125">-   SymmetricKey</span></span><br /><span data-ttu-id="dd963-126">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="dd963-126">-   PublicKey</span></span><br /><br /> <span data-ttu-id="dd963-127">Значение по умолчанию — `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="dd963-127">The default is `SymmetricKey`.</span></span> <span data-ttu-id="dd963-128">Это атрибут типа <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="dd963-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="dd963-129">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="dd963-129">issuedTokenType</span></span>|<span data-ttu-id="dd963-130">Строка, содержащая универсальный код ресурса (URI), который задает тип выдаваемых маркеров.</span><span class="sxs-lookup"><span data-stu-id="dd963-130">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="dd963-131">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="dd963-131">The default is `null`.</span></span>|  
|<span data-ttu-id="dd963-132">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="dd963-132">negotiateServiceCredential</span></span>|<span data-ttu-id="dd963-133">Логическое значение, которое определяет, должен ли проводиться обмен учетными данными службы в рамках процесса согласования, или допустимо использование внештатного канала.</span><span class="sxs-lookup"><span data-stu-id="dd963-133">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="dd963-134">Значением по умолчанию является `true`, означающее, что учетные данные службы согласуются.</span><span class="sxs-lookup"><span data-stu-id="dd963-134">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="dd963-135">Атрибут algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="dd963-135">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="dd963-136">Значение</span><span class="sxs-lookup"><span data-stu-id="dd963-136">Value</span></span>|<span data-ttu-id="dd963-137">Описание</span><span class="sxs-lookup"><span data-stu-id="dd963-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dd963-138">Basic128</span><span class="sxs-lookup"><span data-stu-id="dd963-138">Basic128</span></span>|<span data-ttu-id="dd963-139">Используется шифрование Basic128, Sha1 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="dd963-139">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dd963-140">Basic192</span><span class="sxs-lookup"><span data-stu-id="dd963-140">Basic192</span></span>|<span data-ttu-id="dd963-141">Используется шифрование Basic192, Sha1 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="dd963-141">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dd963-142">Basic256</span><span class="sxs-lookup"><span data-stu-id="dd963-142">Basic256</span></span>|<span data-ttu-id="dd963-143">Используется шифрование Basic256, Sha1 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="dd963-143">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dd963-144">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="dd963-144">Basic256Rsa15</span></span>|<span data-ttu-id="dd963-145">Используется Basic256 для шифрования сообщения, Sha1 для хэша и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="dd963-145">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="dd963-146">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="dd963-146">Basic192Rsa15</span></span>|<span data-ttu-id="dd963-147">Используется Basic192 для шифрования сообщения, Sha1 для хэша и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="dd963-147">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="dd963-148">TripleDes</span><span class="sxs-lookup"><span data-stu-id="dd963-148">TripleDes</span></span>|<span data-ttu-id="dd963-149">Используется шифрование TripleDes, Sha1 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="dd963-149">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dd963-150">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="dd963-150">Basic128Rsa15</span></span>|<span data-ttu-id="dd963-151">Используется Basic128 для шифрования сообщения, Sha1 для хэша и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="dd963-151">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="dd963-152">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="dd963-152">TripleDesRsa15</span></span>|<span data-ttu-id="dd963-153">Используется TripleDes для шифрования сообщения, Sha1 для хэша и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="dd963-153">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="dd963-154">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="dd963-154">Basic128Sha256</span></span>|<span data-ttu-id="dd963-155">Используется Basic128 для шифрования сообщения, Sha256 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="dd963-155">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dd963-156">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="dd963-156">Basic192Sha256</span></span>|<span data-ttu-id="dd963-157">Используется Basic192 для шифрования сообщения, Sha256 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="dd963-157">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dd963-158">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="dd963-158">Basic256Sha256</span></span>|<span data-ttu-id="dd963-159">Используется Basic256 для шифрования сообщения, Sha256 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="dd963-159">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dd963-160">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="dd963-160">TripleDesSha256</span></span>|<span data-ttu-id="dd963-161">Используется TripleDes для шифрования сообщения, Sha256 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="dd963-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dd963-162">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="dd963-162">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="dd963-163">Используется Basic128 для шифрования сообщения, Sha256 для хэша и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="dd963-163">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="dd963-164">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="dd963-164">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="dd963-165">Используется Aes192 для шифрования сообщения, Sha256 для хэша и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="dd963-165">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="dd963-166">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="dd963-166">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="dd963-167">Используется Basic256 для шифрования сообщения, Sha256 для хэша и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="dd963-167">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="dd963-168">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="dd963-168">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="dd963-169">Используется TripleDes для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="dd963-169">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dd963-170">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dd963-170">Child Elements</span></span>  
  
|<span data-ttu-id="dd963-171">Элемент</span><span class="sxs-lookup"><span data-stu-id="dd963-171">Element</span></span>|<span data-ttu-id="dd963-172">Описание:</span><span class="sxs-lookup"><span data-stu-id="dd963-172">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd963-173">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="dd963-173">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="dd963-174">Задает коллекцию типов утверждений для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="dd963-174">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="dd963-175">Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="dd963-175">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="dd963-176">issuer</span><span class="sxs-lookup"><span data-stu-id="dd963-176">issuer</span></span>|<span data-ttu-id="dd963-177">Задает конечную точку, которая выдает маркер безопасности.</span><span class="sxs-lookup"><span data-stu-id="dd963-177">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="dd963-178">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="dd963-178">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="dd963-179">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="dd963-179">issuerMetadata</span></span>|<span data-ttu-id="dd963-180">Задает адрес конечной точки издателя.</span><span class="sxs-lookup"><span data-stu-id="dd963-180">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="dd963-181">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="dd963-181">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="dd963-182">Коллекция параметров запроса маркера.</span><span class="sxs-lookup"><span data-stu-id="dd963-182">A collection of token request parameters.</span></span> <span data-ttu-id="dd963-183">Каждый параметр представляет собой элемент XML.</span><span class="sxs-lookup"><span data-stu-id="dd963-183">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dd963-184">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dd963-184">Parent Elements</span></span>  
  
|<span data-ttu-id="dd963-185">Элемент</span><span class="sxs-lookup"><span data-stu-id="dd963-185">Element</span></span>|<span data-ttu-id="dd963-186">Описание</span><span class="sxs-lookup"><span data-stu-id="dd963-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd963-187">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="dd963-187">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="dd963-188">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="dd963-188">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dd963-189">См. также</span><span class="sxs-lookup"><span data-stu-id="dd963-189">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
 `System.ServiceModel.Configuration.FederatedMessageSecurityElement`
- [<span data-ttu-id="dd963-190">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="dd963-190">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="dd963-191">Привязки</span><span class="sxs-lookup"><span data-stu-id="dd963-191">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="dd963-192">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="dd963-192">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="dd963-193">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="dd963-193">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="dd963-194">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="dd963-194">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
