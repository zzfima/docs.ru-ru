---
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 6b40bd6edd27f4c3b4b530387417311e1f93a921
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283599"
---
# <a name="issuedtokenparameters"></a><span data-ttu-id="49950-101">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="49950-101">\<issuedTokenParameters></span></span>
<span data-ttu-id="49950-102">Задает параметры маркера безопасности, выданного в федеративном сценарии безопасности.</span><span class="sxs-lookup"><span data-stu-id="49950-102">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
 <span data-ttu-id="49950-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="49950-103">\<system.serviceModel></span></span>  
<span data-ttu-id="49950-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="49950-104">\<bindings></span></span>  
<span data-ttu-id="49950-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="49950-105">\<customBinding></span></span>  
<span data-ttu-id="49950-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="49950-106">\<binding></span></span>  
<span data-ttu-id="49950-107">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="49950-107">\<security></span></span>  
<span data-ttu-id="49950-108">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="49950-108">\<issuedTokenParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49950-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49950-109">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="49950-110">Тип</span><span class="sxs-lookup"><span data-stu-id="49950-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49950-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="49950-111">Attributes and Elements</span></span>  
 <span data-ttu-id="49950-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="49950-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49950-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="49950-113">Attributes</span></span>  
  
|<span data-ttu-id="49950-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="49950-114">Attribute</span></span>|<span data-ttu-id="49950-115">Описание</span><span class="sxs-lookup"><span data-stu-id="49950-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="49950-116">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="49950-116">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="49950-117">Задает версии спецификаций безопасности (WS-Security, WS-Trust, WS-Secure Conversation и WS-Security Policy), которые должны поддерживаться привязкой.</span><span class="sxs-lookup"><span data-stu-id="49950-117">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="49950-118">Это значение имеет тип <xref:System.ServiceModel.MessageSecurityVersion>.</span><span class="sxs-lookup"><span data-stu-id="49950-118">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="49950-119">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="49950-119">inclusionMode</span></span>|<span data-ttu-id="49950-120">Задает требования включения маркера.</span><span class="sxs-lookup"><span data-stu-id="49950-120">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="49950-121">Это атрибут типа <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span><span class="sxs-lookup"><span data-stu-id="49950-121">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="49950-122">keySize</span><span class="sxs-lookup"><span data-stu-id="49950-122">keySize</span></span>|<span data-ttu-id="49950-123">Целое число, которое задает размер ключа маркера.</span><span class="sxs-lookup"><span data-stu-id="49950-123">An integer that specifies the token key size.</span></span> <span data-ttu-id="49950-124">Значение по умолчанию — 256.</span><span class="sxs-lookup"><span data-stu-id="49950-124">The default value is 256.</span></span>|  
|<span data-ttu-id="49950-125">keyType</span><span class="sxs-lookup"><span data-stu-id="49950-125">keyType</span></span>|<span data-ttu-id="49950-126">Допустимое значение <xref:System.IdentityModel.Tokens.SecurityKeyType>, которое задает тип ключа.</span><span class="sxs-lookup"><span data-stu-id="49950-126">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="49950-127">Значение по умолчанию — `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="49950-127">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="49950-128">tokenType</span><span class="sxs-lookup"><span data-stu-id="49950-128">tokenType</span></span>|<span data-ttu-id="49950-129">Строка, задающая тип маркера.</span><span class="sxs-lookup"><span data-stu-id="49950-129">A string that specifies the token type.</span></span> <span data-ttu-id="49950-130">Значение по умолчанию - "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span><span class="sxs-lookup"><span data-stu-id="49950-130">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="49950-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="49950-131">Child Elements</span></span>  
  
|<span data-ttu-id="49950-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="49950-132">Element</span></span>|<span data-ttu-id="49950-133">Описание</span><span class="sxs-lookup"><span data-stu-id="49950-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49950-134">\<additionalRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="49950-134">\<additionalRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/additionalrequestparameters-element.md)|<span data-ttu-id="49950-135">Коллекция элементов конфигурации, задающих дополнительные параметры запросов.</span><span class="sxs-lookup"><span data-stu-id="49950-135">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="49950-136">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="49950-136">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="49950-137">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="49950-137">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="49950-138">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="49950-138">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="49950-139">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="49950-139">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="49950-140">Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="49950-140">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="49950-141">\<issuer></span><span class="sxs-lookup"><span data-stu-id="49950-141">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer-of-issuedtokenparameters.md)|<span data-ttu-id="49950-142">Элемент конфигурации, задающий конечную точку, выдавшую текущий маркер.</span><span class="sxs-lookup"><span data-stu-id="49950-142">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="49950-143">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="49950-143">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="49950-144">Элемент конфигурации, задающий адрес конечной точки метаданных поставщика маркера.</span><span class="sxs-lookup"><span data-stu-id="49950-144">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="49950-145">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="49950-145">Parent Elements</span></span>  
  
|<span data-ttu-id="49950-146">Элемент</span><span class="sxs-lookup"><span data-stu-id="49950-146">Element</span></span>|<span data-ttu-id="49950-147">Описание</span><span class="sxs-lookup"><span data-stu-id="49950-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49950-148">\<secureConversationBootstrap ></span><span class="sxs-lookup"><span data-stu-id="49950-148">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="49950-149">Задает значения по умолчанию, используемые для инициализации службы безопасного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="49950-149">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="49950-150">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="49950-150">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="49950-151">Задает параметры безопасности для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="49950-151">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="49950-152">См. также</span><span class="sxs-lookup"><span data-stu-id="49950-152">See also</span></span>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="49950-153">Привязки</span><span class="sxs-lookup"><span data-stu-id="49950-153">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="49950-154">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="49950-154">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="49950-155">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="49950-155">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="49950-156">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="49950-156">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="49950-157">Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="49950-157">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="49950-158">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="49950-158">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="49950-159">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="49950-159">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="49950-160">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="49950-160">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="49950-161">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="49950-161">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="49950-162">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="49950-162">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
