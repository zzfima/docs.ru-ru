---
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 8432463ff62e4b5e54a491b574cc6a5285efe220
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397956"
---
# <a name="issuedtokenparameters"></a><span data-ttu-id="b7723-101">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="b7723-101">\<issuedTokenParameters></span></span>
<span data-ttu-id="b7723-102">Задает параметры маркера безопасности, выданного в федеративном сценарии безопасности.</span><span class="sxs-lookup"><span data-stu-id="b7723-102">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
<span data-ttu-id="b7723-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b7723-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b7723-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b7723-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b7723-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="b7723-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="b7723-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="b7723-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="b7723-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="b7723-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="b7723-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> безопасности**](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="b7723-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="b7723-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuedTokenParameters >**</span><span class="sxs-lookup"><span data-stu-id="b7723-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenParameters>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7723-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b7723-110">Syntax</span></span>  
  
```xml  
<issuedTokenParameters defaultMessageSecurityVersion="System.ServiceModel.MessageSecurityVersion"
                       inclusionMode="AlwaysToInitiator/AlwaysToRecipient/Never/Once"
                       keySize="Integer"
                       keyType="AsymmetricKey/BearerKey/SymmetricKey"
                       tokenType="String">
  <additionalRequestParameters />
  <claimTypeRequirements>
    <add claimType="URI"
         isOptional="Boolean" />
  </claimTypeRequirements>
  <issuer address="String"
          binding="" />
  <issuerMetadata address="String" />
</issuedTokenParameters>
```  
  
## <a name="type"></a><span data-ttu-id="b7723-111">Тип</span><span class="sxs-lookup"><span data-stu-id="b7723-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7723-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b7723-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b7723-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b7723-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7723-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b7723-114">Attributes</span></span>  
  
|<span data-ttu-id="b7723-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b7723-115">Attribute</span></span>|<span data-ttu-id="b7723-116">Описание</span><span class="sxs-lookup"><span data-stu-id="b7723-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b7723-117">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="b7723-117">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="b7723-118">Задает версии спецификаций безопасности (WS-Security, WS-Trust, WS-Secure Conversation и WS-Security Policy), которые должны поддерживаться привязкой.</span><span class="sxs-lookup"><span data-stu-id="b7723-118">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="b7723-119">Это значение имеет тип <xref:System.ServiceModel.MessageSecurityVersion>.</span><span class="sxs-lookup"><span data-stu-id="b7723-119">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="b7723-120">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="b7723-120">inclusionMode</span></span>|<span data-ttu-id="b7723-121">Задает требования включения маркера.</span><span class="sxs-lookup"><span data-stu-id="b7723-121">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="b7723-122">Это атрибут типа <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span><span class="sxs-lookup"><span data-stu-id="b7723-122">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="b7723-123">keySize</span><span class="sxs-lookup"><span data-stu-id="b7723-123">keySize</span></span>|<span data-ttu-id="b7723-124">Целое число, которое задает размер ключа маркера.</span><span class="sxs-lookup"><span data-stu-id="b7723-124">An integer that specifies the token key size.</span></span> <span data-ttu-id="b7723-125">Значение по умолчанию — 256.</span><span class="sxs-lookup"><span data-stu-id="b7723-125">The default value is 256.</span></span>|  
|<span data-ttu-id="b7723-126">keyType</span><span class="sxs-lookup"><span data-stu-id="b7723-126">keyType</span></span>|<span data-ttu-id="b7723-127">Допустимое значение <xref:System.IdentityModel.Tokens.SecurityKeyType>, которое задает тип ключа.</span><span class="sxs-lookup"><span data-stu-id="b7723-127">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="b7723-128">Значение по умолчанию — `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="b7723-128">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="b7723-129">tokenType</span><span class="sxs-lookup"><span data-stu-id="b7723-129">tokenType</span></span>|<span data-ttu-id="b7723-130">Строка, задающая тип маркера.</span><span class="sxs-lookup"><span data-stu-id="b7723-130">A string that specifies the token type.</span></span> <span data-ttu-id="b7723-131">Значение по умолчанию - "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span><span class="sxs-lookup"><span data-stu-id="b7723-131">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7723-132">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b7723-132">Child Elements</span></span>  
  
|<span data-ttu-id="b7723-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="b7723-133">Element</span></span>|<span data-ttu-id="b7723-134">Описание</span><span class="sxs-lookup"><span data-stu-id="b7723-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7723-135">\<Аддитионалрекуестпараметерс ></span><span class="sxs-lookup"><span data-stu-id="b7723-135">\<additionalRequestParameters></span></span>](additionalrequestparameters-element.md)|<span data-ttu-id="b7723-136">Коллекция элементов конфигурации, задающих дополнительные параметры запросов.</span><span class="sxs-lookup"><span data-stu-id="b7723-136">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="b7723-137">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="b7723-137">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="b7723-138">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="b7723-138">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="b7723-139">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="b7723-139">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="b7723-140">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="b7723-140">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="b7723-141">Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="b7723-141">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="b7723-142">\<issuer></span><span class="sxs-lookup"><span data-stu-id="b7723-142">\<issuer></span></span>](issuer-of-issuedtokenparameters.md)|<span data-ttu-id="b7723-143">Элемент конфигурации, задающий конечную точку, выдавшую текущий маркер.</span><span class="sxs-lookup"><span data-stu-id="b7723-143">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="b7723-144">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="b7723-144">\<issuerMetadata></span></span>](issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="b7723-145">Элемент конфигурации, задающий адрес конечной точки метаданных поставщика маркера.</span><span class="sxs-lookup"><span data-stu-id="b7723-145">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b7723-146">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b7723-146">Parent Elements</span></span>  
  
|<span data-ttu-id="b7723-147">Элемент</span><span class="sxs-lookup"><span data-stu-id="b7723-147">Element</span></span>|<span data-ttu-id="b7723-148">Описание</span><span class="sxs-lookup"><span data-stu-id="b7723-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7723-149">\<Секуреконверсатионбутстрап ></span><span class="sxs-lookup"><span data-stu-id="b7723-149">\<secureConversationBootstrap></span></span>](secureconversationbootstrap.md)|<span data-ttu-id="b7723-150">Задает значения по умолчанию, используемые для инициализации службы безопасного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="b7723-150">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="b7723-151">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="b7723-151">\<security></span></span>](security-of-custombinding.md)|<span data-ttu-id="b7723-152">Задает параметры безопасности для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="b7723-152">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b7723-153">См. также</span><span class="sxs-lookup"><span data-stu-id="b7723-153">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b7723-154">Привязки</span><span class="sxs-lookup"><span data-stu-id="b7723-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b7723-155">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="b7723-155">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b7723-156">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="b7723-156">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b7723-157">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="b7723-157">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="b7723-158">Практическое руководство. Создание пользовательской привязки с помощью SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="b7723-158">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="b7723-159">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="b7723-159">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="b7723-160">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="b7723-160">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="b7723-161">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="b7723-161">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="b7723-162">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="b7723-162">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="b7723-163">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="b7723-163">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
