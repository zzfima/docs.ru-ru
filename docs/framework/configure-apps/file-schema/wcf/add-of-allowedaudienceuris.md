---
title: "&lt;add&gt; для &lt;allowedAudienceUris&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e7b7637-e0ea-4a91-988f-6b6ef28d9fc3
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d4de490107ed905b5acbda057f2cd53a306e6d75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltallowedaudienceurisgt"></a><span data-ttu-id="06235-102">&lt;add&gt; для &lt;allowedAudienceUris&gt;</span><span class="sxs-lookup"><span data-stu-id="06235-102">&lt;add&gt; of &lt;allowedAudienceUris&gt;</span></span>
<span data-ttu-id="06235-103">Добавляет целевой универсальный код ресурса, для которого может быть задан маркер безопасности <xref:System.IdentityModel.Tokens.SamlSecurityToken>, чтобы считаться допустимым для экземпляра <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="06235-103">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
 <span data-ttu-id="06235-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="06235-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="06235-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="06235-105">\<behaviors></span></span>  
<span data-ttu-id="06235-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="06235-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="06235-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="06235-107">\<behavior></span></span>  
<span data-ttu-id="06235-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="06235-108">\<serviceCredentials></span></span>  
<span data-ttu-id="06235-109">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="06235-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="06235-110">\<allowedAudienceUris ></span><span class="sxs-lookup"><span data-stu-id="06235-110">\<allowedAudienceUris></span></span>  
<span data-ttu-id="06235-111">\<Добавить > элемент для \<allowedAudienceUris ></span><span class="sxs-lookup"><span data-stu-id="06235-111">\<add> element for \<allowedAudienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06235-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06235-112">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>   
   <add allowedAudienceUri="String"/>  
</allowedAudienceUris>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06235-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="06235-113">Attributes and Elements</span></span>  
 <span data-ttu-id="06235-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="06235-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06235-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="06235-115">Attributes</span></span>  
  
|<span data-ttu-id="06235-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="06235-116">Attribute</span></span>|<span data-ttu-id="06235-117">Описание</span><span class="sxs-lookup"><span data-stu-id="06235-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="06235-118">allowedAudienceUri</span><span class="sxs-lookup"><span data-stu-id="06235-118">allowedAudienceUri</span></span>|<span data-ttu-id="06235-119">Строка, содержащая целевой универсальный код ресурса, для которого может быть задан маркер безопасности <xref:System.IdentityModel.Tokens.SamlSecurityToken>, чтобы считаться допустимым в экземпляре <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="06235-119">A string that contains a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06235-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="06235-120">Child Elements</span></span>  
 <span data-ttu-id="06235-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="06235-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06235-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="06235-122">Parent Elements</span></span>  
  
|<span data-ttu-id="06235-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="06235-123">Element</span></span>|<span data-ttu-id="06235-124">Описание</span><span class="sxs-lookup"><span data-stu-id="06235-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06235-125">\<allowedAudienceUris ></span><span class="sxs-lookup"><span data-stu-id="06235-125">\<allowedAudienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md)|<span data-ttu-id="06235-126">Представляет коллекцию целевых универсальных кодов ресурса (URI), для которых может быть задан маркер безопасности <xref:System.IdentityModel.Tokens.SamlSecurityToken>, чтобы они считались допустимыми для экземпляра <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="06235-126">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06235-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="06235-127">Remarks</span></span>  
 <span data-ttu-id="06235-128">Данную коллекцию следует использовать в федеративном приложении, которое использует службу маркеров безопасности (STS), выдающую маркеры безопасности <xref:System.IdentityModel.Tokens.SamlSecurityToken>.</span><span class="sxs-lookup"><span data-stu-id="06235-128">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="06235-129">При выпуске маркера безопасности служба STS также может указать универсальный код ресурса (URI) веб-служб, для которых предназначен маркер безопасности, добавив выражение <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> к маркеру безопасности.</span><span class="sxs-lookup"><span data-stu-id="06235-129">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="06235-130">Это позволяет коду <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> для веб-службы получателя проверить, что выданный маркер безопасности предназначен для данной службы, указав на необходимость выполнения соответствующей проверки. Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="06235-130">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
-   <span data-ttu-id="06235-131">Присвойте атрибуту `audienceUriMode` элемента `<issuedTokenAuthentication>` значение <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> или <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span><span class="sxs-lookup"><span data-stu-id="06235-131">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
-   <span data-ttu-id="06235-132">Задайте набор допустимых универсальных кодов ресурса (URI), добавив их в данную коллекцию.</span><span class="sxs-lookup"><span data-stu-id="06235-132">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="06235-133">Для получения дополнительной информации см. <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="06235-133">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="06235-134">Дополнительные сведения об использовании данного элемента конфигурации в разделе [как: Настройка учетных данных службы федерации](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="06235-134">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06235-135">См. также</span><span class="sxs-lookup"><span data-stu-id="06235-135">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>  
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>  
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>  
 [<span data-ttu-id="06235-136">\<allowedAudienceUris ></span><span class="sxs-lookup"><span data-stu-id="06235-136">\<allowedAudienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md)  
 [<span data-ttu-id="06235-137">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="06235-137">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [<span data-ttu-id="06235-138">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="06235-138">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="06235-139">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="06235-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="06235-140">Как: настройте учетные данные для службы федерации</span><span class="sxs-lookup"><span data-stu-id="06235-140">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
