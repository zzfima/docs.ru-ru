---
title: '&lt;issuedTokenParameters&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4fdb110302de05fd7dac3c318b8cd4bf83c0155b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltissuedtokenparametersgt"></a><span data-ttu-id="543af-102">&lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="543af-102">&lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="543af-103">Задает параметры маркера безопасности, выданного в федеративном сценарии безопасности.</span><span class="sxs-lookup"><span data-stu-id="543af-103">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
 <span data-ttu-id="543af-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="543af-104">\<system.serviceModel></span></span>  
<span data-ttu-id="543af-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="543af-105">\<bindings></span></span>  
<span data-ttu-id="543af-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="543af-106">\<customBinding></span></span>  
<span data-ttu-id="543af-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="543af-107">\<binding></span></span>  
<span data-ttu-id="543af-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="543af-108">\<security></span></span>  
<span data-ttu-id="543af-109">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="543af-109">\<issuedTokenParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="543af-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="543af-110">Syntax</span></span>  
  
```xml  
<issuedTokenParameters   
      DefaultMessageSecurityVersion="System.ServiceModel.MessageSecurityVersion"  
      inclusionMode="AlwaysToInitiator/AlwaysToRecipient/Never/Once"  
      keySize="Integer"  
   keyType="AsymmetricKey/BearerKey/SymmetricKey"  
      tokenType="String" >  
   <additionalRequestParameters />  
      <claimTypeRequirements>  
            <add claimType="URI"  
           isOptional="Boolean" />  
      </claimTypeRequirements>  
      <issuer address="String"   
                      binding=" " />  
      <issuerMetadata address="String" />   
</issuedTokenParameters>  
```  
  
## <a name="type"></a><span data-ttu-id="543af-111">Тип</span><span class="sxs-lookup"><span data-stu-id="543af-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="543af-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="543af-112">Attributes and Elements</span></span>  
 <span data-ttu-id="543af-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="543af-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="543af-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="543af-114">Attributes</span></span>  
  
|<span data-ttu-id="543af-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="543af-115">Attribute</span></span>|<span data-ttu-id="543af-116">Описание</span><span class="sxs-lookup"><span data-stu-id="543af-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="543af-117">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="543af-117">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="543af-118">Задает версии спецификаций безопасности (WS-Security, WS-Trust, WS-Secure Conversation и WS-Security Policy), которые должны поддерживаться привязкой.</span><span class="sxs-lookup"><span data-stu-id="543af-118">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="543af-119">Это значение имеет тип <xref:System.ServiceModel.MessageSecurityVersion>.</span><span class="sxs-lookup"><span data-stu-id="543af-119">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="543af-120">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="543af-120">inclusionMode</span></span>|<span data-ttu-id="543af-121">Задает требования включения маркера.</span><span class="sxs-lookup"><span data-stu-id="543af-121">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="543af-122">Это атрибут типа <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span><span class="sxs-lookup"><span data-stu-id="543af-122">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="543af-123">keySize</span><span class="sxs-lookup"><span data-stu-id="543af-123">keySize</span></span>|<span data-ttu-id="543af-124">Целое число, которое задает размер ключа маркера.</span><span class="sxs-lookup"><span data-stu-id="543af-124">An integer that specifies the token key size.</span></span> <span data-ttu-id="543af-125">Значение по умолчанию — 256.</span><span class="sxs-lookup"><span data-stu-id="543af-125">The default value is 256.</span></span>|  
|<span data-ttu-id="543af-126">keyType</span><span class="sxs-lookup"><span data-stu-id="543af-126">keyType</span></span>|<span data-ttu-id="543af-127">Допустимое значение <xref:System.IdentityModel.Tokens.SecurityKeyType>, которое задает тип ключа.</span><span class="sxs-lookup"><span data-stu-id="543af-127">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="543af-128">Значение по умолчанию — `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="543af-128">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="543af-129">tokenType</span><span class="sxs-lookup"><span data-stu-id="543af-129">tokenType</span></span>|<span data-ttu-id="543af-130">Строка, задающая тип маркера.</span><span class="sxs-lookup"><span data-stu-id="543af-130">A string that specifies the token type.</span></span> <span data-ttu-id="543af-131">Значение по умолчанию - http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML.</span><span class="sxs-lookup"><span data-stu-id="543af-131">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="543af-132">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="543af-132">Child Elements</span></span>  
  
|<span data-ttu-id="543af-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="543af-133">Element</span></span>|<span data-ttu-id="543af-134">Описание</span><span class="sxs-lookup"><span data-stu-id="543af-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="543af-135">\<additionalRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="543af-135">\<additionalRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/additionalrequestparameters-element.md)|<span data-ttu-id="543af-136">Коллекция элементов конфигурации, задающих дополнительные параметры запросов.</span><span class="sxs-lookup"><span data-stu-id="543af-136">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="543af-137">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="543af-137">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="543af-138">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="543af-138">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="543af-139">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="543af-139">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="543af-140">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="543af-140">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="543af-141">Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="543af-141">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="543af-142">\<издатель ></span><span class="sxs-lookup"><span data-stu-id="543af-142">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer-of-issuedtokenparameters.md)|<span data-ttu-id="543af-143">Элемент конфигурации, задающий конечную точку, выдавшую текущий маркер.</span><span class="sxs-lookup"><span data-stu-id="543af-143">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="543af-144">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="543af-144">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="543af-145">Элемент конфигурации, задающий адрес конечной точки метаданных поставщика маркера.</span><span class="sxs-lookup"><span data-stu-id="543af-145">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="543af-146">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="543af-146">Parent Elements</span></span>  
  
|<span data-ttu-id="543af-147">Элемент</span><span class="sxs-lookup"><span data-stu-id="543af-147">Element</span></span>|<span data-ttu-id="543af-148">Описание</span><span class="sxs-lookup"><span data-stu-id="543af-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="543af-149">\<secureConversationBootstrap ></span><span class="sxs-lookup"><span data-stu-id="543af-149">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="543af-150">Задает значения по умолчанию, используемые для инициализации службы безопасного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="543af-150">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="543af-151">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="543af-151">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="543af-152">Задает параметры безопасности для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="543af-152">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="543af-153">См. также</span><span class="sxs-lookup"><span data-stu-id="543af-153">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="543af-154">Привязки</span><span class="sxs-lookup"><span data-stu-id="543af-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="543af-155">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="543af-155">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="543af-156">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="543af-156">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="543af-157">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="543af-157">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="543af-158">Как: Создание пользовательской привязки, с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="543af-158">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="543af-159">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="543af-159">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)  
 [<span data-ttu-id="543af-160">Службы идентификации и проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="543af-160">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="543af-161">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="543af-161">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="543af-162">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="543af-162">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="543af-163">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="543af-163">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
