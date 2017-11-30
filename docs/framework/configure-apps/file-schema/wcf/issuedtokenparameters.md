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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ef68585054d61de8c25b7e3effd1d72063d4589c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltissuedtokenparametersgt"></a><span data-ttu-id="85ef3-102">&lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="85ef3-102">&lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="85ef3-103">Задает параметры маркера безопасности, выданного в федеративном сценарии безопасности.</span><span class="sxs-lookup"><span data-stu-id="85ef3-103">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
 <span data-ttu-id="85ef3-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="85ef3-104">\<system.serviceModel></span></span>  
<span data-ttu-id="85ef3-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="85ef3-105">\<bindings></span></span>  
<span data-ttu-id="85ef3-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="85ef3-106">\<customBinding></span></span>  
<span data-ttu-id="85ef3-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="85ef3-107">\<binding></span></span>  
<span data-ttu-id="85ef3-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="85ef3-108">\<security></span></span>  
<span data-ttu-id="85ef3-109">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="85ef3-109">\<issuedTokenParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85ef3-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85ef3-110">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="85ef3-111">Тип</span><span class="sxs-lookup"><span data-stu-id="85ef3-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85ef3-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="85ef3-112">Attributes and Elements</span></span>  
 <span data-ttu-id="85ef3-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="85ef3-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85ef3-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="85ef3-114">Attributes</span></span>  
  
|<span data-ttu-id="85ef3-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="85ef3-115">Attribute</span></span>|<span data-ttu-id="85ef3-116">Описание</span><span class="sxs-lookup"><span data-stu-id="85ef3-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="85ef3-117">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="85ef3-117">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="85ef3-118">Задает версии спецификаций безопасности (WS-Security, WS-Trust, WS-Secure Conversation и WS-Security Policy), которые должны поддерживаться привязкой.</span><span class="sxs-lookup"><span data-stu-id="85ef3-118">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="85ef3-119">Это значение имеет тип <xref:System.ServiceModel.MessageSecurityVersion>.</span><span class="sxs-lookup"><span data-stu-id="85ef3-119">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="85ef3-120">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="85ef3-120">inclusionMode</span></span>|<span data-ttu-id="85ef3-121">Задает требования включения маркера.</span><span class="sxs-lookup"><span data-stu-id="85ef3-121">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="85ef3-122">Это атрибут типа <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span><span class="sxs-lookup"><span data-stu-id="85ef3-122">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="85ef3-123">keySize</span><span class="sxs-lookup"><span data-stu-id="85ef3-123">keySize</span></span>|<span data-ttu-id="85ef3-124">Целое число, которое задает размер ключа маркера.</span><span class="sxs-lookup"><span data-stu-id="85ef3-124">An integer that specifies the token key size.</span></span> <span data-ttu-id="85ef3-125">Значение по умолчанию — 256.</span><span class="sxs-lookup"><span data-stu-id="85ef3-125">The default value is 256.</span></span>|  
|<span data-ttu-id="85ef3-126">keyType</span><span class="sxs-lookup"><span data-stu-id="85ef3-126">keyType</span></span>|<span data-ttu-id="85ef3-127">Допустимое значение <xref:System.IdentityModel.Tokens.SecurityKeyType>, которое задает тип ключа.</span><span class="sxs-lookup"><span data-stu-id="85ef3-127">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="85ef3-128">Значение по умолчанию — `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="85ef3-128">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="85ef3-129">tokenType</span><span class="sxs-lookup"><span data-stu-id="85ef3-129">tokenType</span></span>|<span data-ttu-id="85ef3-130">Строка, задающая тип маркера.</span><span class="sxs-lookup"><span data-stu-id="85ef3-130">A string that specifies the token type.</span></span> <span data-ttu-id="85ef3-131">Значение по умолчанию - http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML.</span><span class="sxs-lookup"><span data-stu-id="85ef3-131">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85ef3-132">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="85ef3-132">Child Elements</span></span>  
  
|<span data-ttu-id="85ef3-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="85ef3-133">Element</span></span>|<span data-ttu-id="85ef3-134">Описание</span><span class="sxs-lookup"><span data-stu-id="85ef3-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85ef3-135">\<additionalRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="85ef3-135">\<additionalRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/additionalrequestparameters-element.md)|<span data-ttu-id="85ef3-136">Коллекция элементов конфигурации, задающих дополнительные параметры запросов.</span><span class="sxs-lookup"><span data-stu-id="85ef3-136">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="85ef3-137">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="85ef3-137">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="85ef3-138">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="85ef3-138">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="85ef3-139">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="85ef3-139">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="85ef3-140">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="85ef3-140">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="85ef3-141">Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="85ef3-141">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="85ef3-142">\<издатель ></span><span class="sxs-lookup"><span data-stu-id="85ef3-142">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer-of-issuedtokenparameters.md)|<span data-ttu-id="85ef3-143">Элемент конфигурации, задающий конечную точку, выдавшую текущий маркер.</span><span class="sxs-lookup"><span data-stu-id="85ef3-143">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="85ef3-144">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="85ef3-144">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="85ef3-145">Элемент конфигурации, задающий адрес конечной точки метаданных поставщика маркера.</span><span class="sxs-lookup"><span data-stu-id="85ef3-145">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="85ef3-146">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="85ef3-146">Parent Elements</span></span>  
  
|<span data-ttu-id="85ef3-147">Элемент</span><span class="sxs-lookup"><span data-stu-id="85ef3-147">Element</span></span>|<span data-ttu-id="85ef3-148">Описание</span><span class="sxs-lookup"><span data-stu-id="85ef3-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85ef3-149">\<secureConversationBootstrap ></span><span class="sxs-lookup"><span data-stu-id="85ef3-149">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="85ef3-150">Задает значения по умолчанию, используемые для инициализации службы безопасного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="85ef3-150">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="85ef3-151">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="85ef3-151">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="85ef3-152">Задает параметры безопасности для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="85ef3-152">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85ef3-153">См. также</span><span class="sxs-lookup"><span data-stu-id="85ef3-153">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="85ef3-154">Привязки</span><span class="sxs-lookup"><span data-stu-id="85ef3-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="85ef3-155">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="85ef3-155">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="85ef3-156">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="85ef3-156">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="85ef3-157">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="85ef3-157">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="85ef3-158">Как: Создание пользовательской привязки, с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="85ef3-158">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="85ef3-159">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="85ef3-159">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)  
 [<span data-ttu-id="85ef3-160">Службы идентификации и проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="85ef3-160">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="85ef3-161">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="85ef3-161">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="85ef3-162">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="85ef3-162">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="85ef3-163">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="85ef3-163">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
