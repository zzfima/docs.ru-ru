---
title: Элемент <message> для <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: f05bd90bd2e4c7e1fd606518d9e5cb8d4e5ad974
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61767576"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="cbdfa-102">\<сообщение > элемент \<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="cbdfa-102">\<message> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="cbdfa-103">Определяет параметры безопасности уровня сообщений для [ \<ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="cbdfa-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cbdfa-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cbdfa-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="cbdfa-105">\<bindings></span></span>  
<span data-ttu-id="cbdfa-106">\<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="cbdfa-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="cbdfa-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="cbdfa-107">\<binding></span></span>  
<span data-ttu-id="cbdfa-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="cbdfa-108">\<security></span></span>  
<span data-ttu-id="cbdfa-109">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="cbdfa-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbdfa-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cbdfa-110">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
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
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cbdfa-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cbdfa-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cbdfa-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cbdfa-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cbdfa-113">Attributes</span></span>  
  
|<span data-ttu-id="cbdfa-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cbdfa-114">Attribute</span></span>|<span data-ttu-id="cbdfa-115">Описание</span><span class="sxs-lookup"><span data-stu-id="cbdfa-115">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="cbdfa-116">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-116">Optional.</span></span> <span data-ttu-id="cbdfa-117">Задает алгоритмы шифрования сообщений, сигнатуры и ключей.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-117">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="cbdfa-118">Алгоритмы и размеры ключей определяются классом <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-118">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="cbdfa-119">Эти алгоритмы соответствуют алгоритмам, заданным в спецификации языка политики безопасности (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="cbdfa-119">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="cbdfa-120">В следующей таблице приводятся возможные значения.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-120">See the following table for possible values.</span></span> <span data-ttu-id="cbdfa-121">Значение по умолчанию - Basic256.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-121">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="cbdfa-122">Задает тип выдаваемого ключа.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-122">Specifies the type of key to be issued.</span></span> <span data-ttu-id="cbdfa-123">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="cbdfa-123">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="cbdfa-124">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="cbdfa-124">-   SymmetricKey</span></span><br /><span data-ttu-id="cbdfa-125">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="cbdfa-125">-   PublicKey</span></span><br /><span data-ttu-id="cbdfa-126">-BearerKey</span><span class="sxs-lookup"><span data-stu-id="cbdfa-126">-   BearerKey</span></span><br /><br /> <span data-ttu-id="cbdfa-127">Значение по умолчанию - SymmetricKey.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-127">The default is SymmetricKey.</span></span> <span data-ttu-id="cbdfa-128">Это атрибут типа <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="cbdfa-129">Универсальный код ресурса (URI), который задает тип выдаваемых маркеров.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-129">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="cbdfa-130">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-130">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="cbdfa-131">Значение, которое определяет, должен ли проводиться обмен учетными данными службы в рамках процесса согласования, или эти данные доступны вне диапазона.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-131">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="cbdfa-132">Значением по умолчанию является `true`, означающее, что учетные данные службы согласуются.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-132">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="cbdfa-133">Атрибут algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="cbdfa-133">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="cbdfa-134">Значение</span><span class="sxs-lookup"><span data-stu-id="cbdfa-134">Value</span></span>|<span data-ttu-id="cbdfa-135">Описание</span><span class="sxs-lookup"><span data-stu-id="cbdfa-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cbdfa-136">Basic128</span><span class="sxs-lookup"><span data-stu-id="cbdfa-136">Basic128</span></span>|<span data-ttu-id="cbdfa-137">Используется шифрование Aes128, Sha1 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-137">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="cbdfa-138">Basic192</span><span class="sxs-lookup"><span data-stu-id="cbdfa-138">Basic192</span></span>|<span data-ttu-id="cbdfa-139">Используется шифрование Aes192, Sha1 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-139">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="cbdfa-140">Basic256</span><span class="sxs-lookup"><span data-stu-id="cbdfa-140">Basic256</span></span>|<span data-ttu-id="cbdfa-141">Используется шифрование Aes256, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-141">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="cbdfa-142">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="cbdfa-142">Basic256Rsa15</span></span>|<span data-ttu-id="cbdfa-143">Используется Aes256 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-143">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="cbdfa-144">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="cbdfa-144">Basic192Rsa15</span></span>|<span data-ttu-id="cbdfa-145">Используется Aes192 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-145">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="cbdfa-146">TripleDes</span><span class="sxs-lookup"><span data-stu-id="cbdfa-146">TripleDes</span></span>|<span data-ttu-id="cbdfa-147">Используется шифрование TripleDes, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-147">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="cbdfa-148">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="cbdfa-148">Basic128Rsa15</span></span>|<span data-ttu-id="cbdfa-149">Используется Aes128 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-149">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="cbdfa-150">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="cbdfa-150">TripleDesRsa15</span></span>|<span data-ttu-id="cbdfa-151">Используется TripleDes для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-151">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="cbdfa-152">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="cbdfa-152">Basic128Sha256</span></span>|<span data-ttu-id="cbdfa-153">Используется Aes256 для шифрования сообщения, Sha256 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-153">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="cbdfa-154">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="cbdfa-154">Basic192Sha256</span></span>|<span data-ttu-id="cbdfa-155">Используется Aes192 для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-155">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="cbdfa-156">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="cbdfa-156">Basic256Sha256</span></span>|<span data-ttu-id="cbdfa-157">Используется Aes256 для шифрования сообщения, Sha256 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-157">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="cbdfa-158">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="cbdfa-158">TripleDesSha256</span></span>|<span data-ttu-id="cbdfa-159">Используется TripleDes для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-159">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="cbdfa-160">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="cbdfa-160">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="cbdfa-161">Используется Aes128 для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-161">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="cbdfa-162">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="cbdfa-162">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="cbdfa-163">Используется Aes192 для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-163">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="cbdfa-164">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="cbdfa-164">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="cbdfa-165">Используется Aes256 для шифрования сообщения, Sha256 для хэша и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-165">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="cbdfa-166">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="cbdfa-166">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="cbdfa-167">Используется TripleDes для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-167">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cbdfa-168">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cbdfa-168">Child Elements</span></span>  
  
|<span data-ttu-id="cbdfa-169">Элемент</span><span class="sxs-lookup"><span data-stu-id="cbdfa-169">Element</span></span>|<span data-ttu-id="cbdfa-170">Описание</span><span class="sxs-lookup"><span data-stu-id="cbdfa-170">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cbdfa-171">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="cbdfa-171">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="cbdfa-172">Задает коллекцию типов утверждений для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-172">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="cbdfa-173">Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-173">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[<span data-ttu-id="cbdfa-174">\<issuer></span><span class="sxs-lookup"><span data-stu-id="cbdfa-174">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|<span data-ttu-id="cbdfa-175">Задает конечную точку, которая выдает маркер безопасности.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-175">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="cbdfa-176">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-176">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[<span data-ttu-id="cbdfa-177">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="cbdfa-177">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|<span data-ttu-id="cbdfa-178">Задает адрес конечной точки издателя.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-178">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="cbdfa-179">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="cbdfa-179">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="cbdfa-180">Коллекция параметров запроса маркера.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-180">A collection of token request parameters.</span></span> <span data-ttu-id="cbdfa-181">Каждый параметр представляет собой элемент XML.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-181">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cbdfa-182">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cbdfa-182">Parent Elements</span></span>  
  
|<span data-ttu-id="cbdfa-183">Элемент</span><span class="sxs-lookup"><span data-stu-id="cbdfa-183">Element</span></span>|<span data-ttu-id="cbdfa-184">Описание</span><span class="sxs-lookup"><span data-stu-id="cbdfa-184">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cbdfa-185">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="cbdfa-185">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="cbdfa-186">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="cbdfa-186">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cbdfa-187">См. также</span><span class="sxs-lookup"><span data-stu-id="cbdfa-187">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="cbdfa-188">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="cbdfa-188">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="cbdfa-189">Привязки</span><span class="sxs-lookup"><span data-stu-id="cbdfa-189">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="cbdfa-190">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="cbdfa-190">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="cbdfa-191">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="cbdfa-191">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="cbdfa-192">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="cbdfa-192">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
