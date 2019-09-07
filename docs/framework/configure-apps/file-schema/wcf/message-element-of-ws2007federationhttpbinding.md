---
title: Элемент <message> для <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: b1128bda6068a1fe3d8f5bb5ac29cc349f023b5b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397851"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="26ea0-102">\<элемент Message > элемента \<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="26ea0-102">\<message> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="26ea0-103">Определяет параметры безопасности на уровне сообщений для [ \<элемента ws2007FederationHttpBinding >](ws2007federationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="26ea0-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
<span data-ttu-id="26ea0-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="26ea0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="26ea0-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="26ea0-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="26ea0-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="26ea0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="26ea0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ws2007FederationHttpBinding >** ](ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="26ea0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="26ea0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="26ea0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="26ea0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> безопасности**](security-element-of-ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="26ea0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-element-of-ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="26ea0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> сообщения**</span><span class="sxs-lookup"><span data-stu-id="26ea0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26ea0-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="26ea0-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26ea0-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="26ea0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="26ea0-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="26ea0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26ea0-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="26ea0-114">Attributes</span></span>  
  
|<span data-ttu-id="26ea0-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="26ea0-115">Attribute</span></span>|<span data-ttu-id="26ea0-116">Описание</span><span class="sxs-lookup"><span data-stu-id="26ea0-116">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="26ea0-117">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="26ea0-117">Optional.</span></span> <span data-ttu-id="26ea0-118">Задает алгоритмы шифрования сообщений, сигнатуры и ключей.</span><span class="sxs-lookup"><span data-stu-id="26ea0-118">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="26ea0-119">Алгоритмы и размеры ключей определяются классом <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="26ea0-119">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="26ea0-120">Эти алгоритмы соответствуют алгоритмам, заданным в спецификации языка политики безопасности (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="26ea0-120">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="26ea0-121">В следующей таблице приводятся возможные значения.</span><span class="sxs-lookup"><span data-stu-id="26ea0-121">See the following table for possible values.</span></span> <span data-ttu-id="26ea0-122">Значение по умолчанию - Basic256.</span><span class="sxs-lookup"><span data-stu-id="26ea0-122">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="26ea0-123">Задает тип выдаваемого ключа.</span><span class="sxs-lookup"><span data-stu-id="26ea0-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="26ea0-124">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="26ea0-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="26ea0-125">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="26ea0-125">-   SymmetricKey</span></span><br /><span data-ttu-id="26ea0-126">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="26ea0-126">-   PublicKey</span></span><br /><span data-ttu-id="26ea0-127">-Беареркэй</span><span class="sxs-lookup"><span data-stu-id="26ea0-127">-   BearerKey</span></span><br /><br /> <span data-ttu-id="26ea0-128">Значение по умолчанию - SymmetricKey.</span><span class="sxs-lookup"><span data-stu-id="26ea0-128">The default is SymmetricKey.</span></span> <span data-ttu-id="26ea0-129">Это атрибут типа <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="26ea0-129">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="26ea0-130">Универсальный код ресурса (URI), который задает тип выдаваемых маркеров.</span><span class="sxs-lookup"><span data-stu-id="26ea0-130">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="26ea0-131">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="26ea0-131">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="26ea0-132">Значение, которое определяет, должен ли проводиться обмен учетными данными службы в рамках процесса согласования, или эти данные доступны вне диапазона.</span><span class="sxs-lookup"><span data-stu-id="26ea0-132">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="26ea0-133">Значением по умолчанию является `true`, означающее, что учетные данные службы согласуются.</span><span class="sxs-lookup"><span data-stu-id="26ea0-133">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="26ea0-134">Атрибут algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="26ea0-134">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="26ea0-135">Значение</span><span class="sxs-lookup"><span data-stu-id="26ea0-135">Value</span></span>|<span data-ttu-id="26ea0-136">Описание</span><span class="sxs-lookup"><span data-stu-id="26ea0-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="26ea0-137">Basic128</span><span class="sxs-lookup"><span data-stu-id="26ea0-137">Basic128</span></span>|<span data-ttu-id="26ea0-138">Используется шифрование Aes128, Sha1 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="26ea0-138">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="26ea0-139">Basic192</span><span class="sxs-lookup"><span data-stu-id="26ea0-139">Basic192</span></span>|<span data-ttu-id="26ea0-140">Используется шифрование Aes192, Sha1 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="26ea0-140">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="26ea0-141">Basic256</span><span class="sxs-lookup"><span data-stu-id="26ea0-141">Basic256</span></span>|<span data-ttu-id="26ea0-142">Используется шифрование Aes256, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="26ea0-142">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="26ea0-143">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="26ea0-143">Basic256Rsa15</span></span>|<span data-ttu-id="26ea0-144">Используется Aes256 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="26ea0-144">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="26ea0-145">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="26ea0-145">Basic192Rsa15</span></span>|<span data-ttu-id="26ea0-146">Используется Aes192 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="26ea0-146">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="26ea0-147">TripleDes</span><span class="sxs-lookup"><span data-stu-id="26ea0-147">TripleDes</span></span>|<span data-ttu-id="26ea0-148">Используется шифрование TripleDes, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="26ea0-148">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="26ea0-149">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="26ea0-149">Basic128Rsa15</span></span>|<span data-ttu-id="26ea0-150">Используется Aes128 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="26ea0-150">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="26ea0-151">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="26ea0-151">TripleDesRsa15</span></span>|<span data-ttu-id="26ea0-152">Используется TripleDes для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="26ea0-152">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="26ea0-153">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="26ea0-153">Basic128Sha256</span></span>|<span data-ttu-id="26ea0-154">Используется Aes256 для шифрования сообщения, Sha256 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="26ea0-154">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="26ea0-155">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="26ea0-155">Basic192Sha256</span></span>|<span data-ttu-id="26ea0-156">Используется Aes192 для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="26ea0-156">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="26ea0-157">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="26ea0-157">Basic256Sha256</span></span>|<span data-ttu-id="26ea0-158">Используется Aes256 для шифрования сообщения, Sha256 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="26ea0-158">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="26ea0-159">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="26ea0-159">TripleDesSha256</span></span>|<span data-ttu-id="26ea0-160">Используется TripleDes для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="26ea0-160">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="26ea0-161">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="26ea0-161">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="26ea0-162">Используется Aes128 для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="26ea0-162">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="26ea0-163">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="26ea0-163">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="26ea0-164">Используется Aes192 для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="26ea0-164">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="26ea0-165">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="26ea0-165">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="26ea0-166">Используется Aes256 для шифрования сообщения, Sha256 для хэша и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="26ea0-166">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="26ea0-167">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="26ea0-167">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="26ea0-168">Используется TripleDes для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="26ea0-168">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26ea0-169">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="26ea0-169">Child Elements</span></span>  
  
|<span data-ttu-id="26ea0-170">Элемент</span><span class="sxs-lookup"><span data-stu-id="26ea0-170">Element</span></span>|<span data-ttu-id="26ea0-171">Описание</span><span class="sxs-lookup"><span data-stu-id="26ea0-171">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26ea0-172">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="26ea0-172">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="26ea0-173">Задает коллекцию типов утверждений для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="26ea0-173">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="26ea0-174">Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="26ea0-174">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[<span data-ttu-id="26ea0-175">\<issuer></span><span class="sxs-lookup"><span data-stu-id="26ea0-175">\<issuer></span></span>](issuer.md)|<span data-ttu-id="26ea0-176">Задает конечную точку, которая выдает маркер безопасности.</span><span class="sxs-lookup"><span data-stu-id="26ea0-176">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="26ea0-177">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="26ea0-177">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[<span data-ttu-id="26ea0-178">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="26ea0-178">\<issuerMetadata></span></span>](issuermetadata.md)|<span data-ttu-id="26ea0-179">Задает адрес конечной точки издателя.</span><span class="sxs-lookup"><span data-stu-id="26ea0-179">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="26ea0-180">\<Токенрекуестпараметерс ></span><span class="sxs-lookup"><span data-stu-id="26ea0-180">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="26ea0-181">Коллекция параметров запроса маркера.</span><span class="sxs-lookup"><span data-stu-id="26ea0-181">A collection of token request parameters.</span></span> <span data-ttu-id="26ea0-182">Каждый параметр представляет собой элемент XML.</span><span class="sxs-lookup"><span data-stu-id="26ea0-182">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="26ea0-183">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="26ea0-183">Parent Elements</span></span>  
  
|<span data-ttu-id="26ea0-184">Элемент</span><span class="sxs-lookup"><span data-stu-id="26ea0-184">Element</span></span>|<span data-ttu-id="26ea0-185">Описание</span><span class="sxs-lookup"><span data-stu-id="26ea0-185">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26ea0-186">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="26ea0-186">\<security></span></span>](security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="26ea0-187">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="26ea0-187">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="26ea0-188">См. также</span><span class="sxs-lookup"><span data-stu-id="26ea0-188">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="26ea0-189">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="26ea0-189">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="26ea0-190">Привязки</span><span class="sxs-lookup"><span data-stu-id="26ea0-190">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="26ea0-191">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="26ea0-191">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="26ea0-192">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="26ea0-192">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="26ea0-193">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="26ea0-193">\<binding></span></span>](../../../misc/binding.md)
