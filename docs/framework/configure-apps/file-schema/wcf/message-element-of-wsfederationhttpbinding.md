---
title: Элемент <message> для <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: 8e0903dd1313e68e2de65730e129079199ebe2f2
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738979"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="4f240-102">\<сообщение > элемента \<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="4f240-102">\<message> element of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="4f240-103">Определяет параметры безопасности на уровне сообщений для [\<wsFederationHttpBinding >](wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="4f240-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
<span data-ttu-id="4f240-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4f240-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4f240-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4f240-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4f240-106">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="4f240-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="4f240-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="4f240-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="4f240-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="4f240-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="4f240-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<security >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="4f240-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="4f240-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**сообщение >**</span><span class="sxs-lookup"><span data-stu-id="4f240-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f240-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f240-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f240-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4f240-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4f240-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4f240-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f240-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4f240-114">Attributes</span></span>  
  
|<span data-ttu-id="4f240-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4f240-115">Attribute</span></span>|<span data-ttu-id="4f240-116">Описание</span><span class="sxs-lookup"><span data-stu-id="4f240-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4f240-117">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="4f240-117">algorithmSuite</span></span>|<span data-ttu-id="4f240-118">Задает алгоритмы шифрования сообщений и ключей.</span><span class="sxs-lookup"><span data-stu-id="4f240-118">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="4f240-119">Допустимые значения этого атрибута см. в таблице «Атрибут algorithmSuite».</span><span class="sxs-lookup"><span data-stu-id="4f240-119">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="4f240-120">Значение по умолчанию — `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="4f240-120">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="4f240-121">Это атрибут типа <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="4f240-121">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="4f240-122">Эти алгоритмы соответствуют алгоритмам, заданным в спецификации языка политики безопасности (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="4f240-122">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="4f240-123">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="4f240-123">issuedKeyType</span></span>|<span data-ttu-id="4f240-124">Задает тип выдаваемого ключа.</span><span class="sxs-lookup"><span data-stu-id="4f240-124">Specifies the type of key to be issued.</span></span> <span data-ttu-id="4f240-125">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="4f240-125">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="4f240-126">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="4f240-126">-   SymmetricKey</span></span><br /><span data-ttu-id="4f240-127">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="4f240-127">-   PublicKey</span></span><br /><br /> <span data-ttu-id="4f240-128">Значение по умолчанию: `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="4f240-128">The default is `SymmetricKey`.</span></span> <span data-ttu-id="4f240-129">Это атрибут типа <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="4f240-129">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="4f240-130">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="4f240-130">issuedTokenType</span></span>|<span data-ttu-id="4f240-131">Строка, содержащая универсальный код ресурса (URI), который задает тип выдаваемых маркеров.</span><span class="sxs-lookup"><span data-stu-id="4f240-131">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="4f240-132">Значение по умолчанию: `null`.</span><span class="sxs-lookup"><span data-stu-id="4f240-132">The default is `null`.</span></span>|  
|<span data-ttu-id="4f240-133">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="4f240-133">negotiateServiceCredential</span></span>|<span data-ttu-id="4f240-134">Логическое значение, которое определяет, должен ли проводиться обмен учетными данными службы в рамках процесса согласования, или допустимо использование внештатного канала.</span><span class="sxs-lookup"><span data-stu-id="4f240-134">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="4f240-135">Значением по умолчанию является `true`, означающее, что учетные данные службы согласуются.</span><span class="sxs-lookup"><span data-stu-id="4f240-135">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="4f240-136">Атрибут algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="4f240-136">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="4f240-137">значения</span><span class="sxs-lookup"><span data-stu-id="4f240-137">Value</span></span>|<span data-ttu-id="4f240-138">Описание</span><span class="sxs-lookup"><span data-stu-id="4f240-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4f240-139">Basic128</span><span class="sxs-lookup"><span data-stu-id="4f240-139">Basic128</span></span>|<span data-ttu-id="4f240-140">Используется шифрование Basic128, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="4f240-140">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="4f240-141">Basic192</span><span class="sxs-lookup"><span data-stu-id="4f240-141">Basic192</span></span>|<span data-ttu-id="4f240-142">Используется шифрование Basic192, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="4f240-142">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="4f240-143">Basic256</span><span class="sxs-lookup"><span data-stu-id="4f240-143">Basic256</span></span>|<span data-ttu-id="4f240-144">Используется шифрование Basic256, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="4f240-144">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="4f240-145">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="4f240-145">Basic256Rsa15</span></span>|<span data-ttu-id="4f240-146">Используется Basic256 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="4f240-146">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="4f240-147">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="4f240-147">Basic192Rsa15</span></span>|<span data-ttu-id="4f240-148">Используется Basic192 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="4f240-148">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="4f240-149">TripleDes</span><span class="sxs-lookup"><span data-stu-id="4f240-149">TripleDes</span></span>|<span data-ttu-id="4f240-150">Используется шифрование TripleDes, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="4f240-150">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="4f240-151">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="4f240-151">Basic128Rsa15</span></span>|<span data-ttu-id="4f240-152">Используется Basic128 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="4f240-152">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="4f240-153">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="4f240-153">TripleDesRsa15</span></span>|<span data-ttu-id="4f240-154">Используется TripleDes для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="4f240-154">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="4f240-155">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="4f240-155">Basic128Sha256</span></span>|<span data-ttu-id="4f240-156">Используется Basic128 для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="4f240-156">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="4f240-157">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="4f240-157">Basic192Sha256</span></span>|<span data-ttu-id="4f240-158">Используется Basic192 для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="4f240-158">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="4f240-159">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="4f240-159">Basic256Sha256</span></span>|<span data-ttu-id="4f240-160">Используется Basic256 для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="4f240-160">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="4f240-161">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="4f240-161">TripleDesSha256</span></span>|<span data-ttu-id="4f240-162">Используется TripleDes для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="4f240-162">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="4f240-163">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="4f240-163">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="4f240-164">Используется Basic128 для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="4f240-164">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="4f240-165">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="4f240-165">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="4f240-166">Используется Aes192 для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="4f240-166">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="4f240-167">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="4f240-167">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="4f240-168">Используется Basic256 для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="4f240-168">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="4f240-169">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="4f240-169">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="4f240-170">Используется TripleDes для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="4f240-170">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f240-171">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4f240-171">Child Elements</span></span>  
  
|<span data-ttu-id="4f240-172">Элемент</span><span class="sxs-lookup"><span data-stu-id="4f240-172">Element</span></span>|<span data-ttu-id="4f240-173">Описание</span><span class="sxs-lookup"><span data-stu-id="4f240-173">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f240-174">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="4f240-174">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="4f240-175">Задает коллекцию типов утверждений для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="4f240-175">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="4f240-176">Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="4f240-176">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="4f240-177">issuer</span><span class="sxs-lookup"><span data-stu-id="4f240-177">issuer</span></span>|<span data-ttu-id="4f240-178">Задает конечную точку, которая выдает маркер безопасности.</span><span class="sxs-lookup"><span data-stu-id="4f240-178">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="4f240-179">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="4f240-179">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="4f240-180">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="4f240-180">issuerMetadata</span></span>|<span data-ttu-id="4f240-181">Задает адрес конечной точки издателя.</span><span class="sxs-lookup"><span data-stu-id="4f240-181">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="4f240-182">\<Токенрекуестпараметерс ></span><span class="sxs-lookup"><span data-stu-id="4f240-182">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="4f240-183">Коллекция параметров запроса маркера.</span><span class="sxs-lookup"><span data-stu-id="4f240-183">A collection of token request parameters.</span></span> <span data-ttu-id="4f240-184">Каждый параметр представляет собой элемент XML.</span><span class="sxs-lookup"><span data-stu-id="4f240-184">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4f240-185">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4f240-185">Parent Elements</span></span>  
  
|<span data-ttu-id="4f240-186">Элемент</span><span class="sxs-lookup"><span data-stu-id="4f240-186">Element</span></span>|<span data-ttu-id="4f240-187">Описание</span><span class="sxs-lookup"><span data-stu-id="4f240-187">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f240-188">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="4f240-188">\<security></span></span>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="4f240-189">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="4f240-189">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f240-190">См. также</span><span class="sxs-lookup"><span data-stu-id="4f240-190">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="4f240-191">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="4f240-191">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="4f240-192">Привязки</span><span class="sxs-lookup"><span data-stu-id="4f240-192">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4f240-193">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="4f240-193">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="4f240-194">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="4f240-194">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="4f240-195">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="4f240-195">\<binding></span></span>](bindings.md)
