---
title: '&lt;allowedAudienceUris&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f4dc73d-d95d-4193-9755-7df4cf2b8e1c
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b48449df95e9cf927cad805043c7419ec8c13be6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltallowedaudienceurisgt"></a><span data-ttu-id="e6353-102">&lt;allowedAudienceUris&gt;</span><span class="sxs-lookup"><span data-stu-id="e6353-102">&lt;allowedAudienceUris&gt;</span></span>
<span data-ttu-id="e6353-103">Представляет коллекцию целевых универсальных кодов ресурса (URI), для которых может быть задан маркер безопасности <xref:System.IdentityModel.Tokens.SamlSecurityToken>, чтобы они считались допустимыми для экземпляра <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="e6353-103">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
 <span data-ttu-id="e6353-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e6353-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e6353-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="e6353-105">\<behaviors></span></span>  
<span data-ttu-id="e6353-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e6353-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="e6353-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="e6353-107">\<behavior></span></span>  
<span data-ttu-id="e6353-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="e6353-108">\<serviceCredentials></span></span>  
<span data-ttu-id="e6353-109">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="e6353-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="e6353-110">\<allowedAudienceUris ></span><span class="sxs-lookup"><span data-stu-id="e6353-110">\<allowedAudienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6353-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6353-111">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>  
      <add allowedAudienceUri="String"/>  
</allowedAudienceUris>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6353-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e6353-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e6353-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e6353-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6353-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e6353-114">Attributes</span></span>  
 <span data-ttu-id="e6353-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e6353-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e6353-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e6353-116">Child Elements</span></span>  
  
|<span data-ttu-id="e6353-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="e6353-117">Element</span></span>|<span data-ttu-id="e6353-118">Описание</span><span class="sxs-lookup"><span data-stu-id="e6353-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6353-119">\<add></span><span class="sxs-lookup"><span data-stu-id="e6353-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)|<span data-ttu-id="e6353-120">Добавляет целевой универсальный код ресурса, для которого может быть задан маркер безопасности <xref:System.IdentityModel.Tokens.SamlSecurityToken>, чтобы считаться допустимым для экземпляра <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="e6353-120">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e6353-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e6353-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e6353-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="e6353-122">Element</span></span>|<span data-ttu-id="e6353-123">Описание</span><span class="sxs-lookup"><span data-stu-id="e6353-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6353-124">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="e6353-124">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="e6353-125">Задает маркер, выданный в качестве учетных данных службы.</span><span class="sxs-lookup"><span data-stu-id="e6353-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6353-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="e6353-126">Remarks</span></span>  
 <span data-ttu-id="e6353-127">Данную коллекцию следует использовать в федеративном приложении, которое использует службу маркеров безопасности (STS), выдающую маркеры безопасности <xref:System.IdentityModel.Tokens.SamlSecurityToken>.</span><span class="sxs-lookup"><span data-stu-id="e6353-127">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="e6353-128">При выпуске маркера безопасности служба STS также может указать универсальный код ресурса (URI) веб-служб, для которых предназначен маркер безопасности, добавив выражение <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> к маркеру безопасности.</span><span class="sxs-lookup"><span data-stu-id="e6353-128">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="e6353-129">Это позволяет коду <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> для веб-службы получателя проверить, что выданный маркер безопасности предназначен для данной службы, указав на необходимость выполнения соответствующей проверки. Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e6353-129">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
-   <span data-ttu-id="e6353-130">Присвойте атрибуту `audienceUriMode` элемента `<issuedTokenAuthentication>` значение <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> или <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span><span class="sxs-lookup"><span data-stu-id="e6353-130">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
-   <span data-ttu-id="e6353-131">Задайте набор допустимых универсальных кодов ресурса (URI), добавив их в данную коллекцию.</span><span class="sxs-lookup"><span data-stu-id="e6353-131">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="e6353-132">Для получения дополнительной информации см. <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="e6353-132">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="e6353-133">Дополнительные сведения об использовании данного элемента конфигурации в разделе [как: Настройка учетных данных службы федерации](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="e6353-133">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6353-134">См. также</span><span class="sxs-lookup"><span data-stu-id="e6353-134">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>  
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>  
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>  
 [<span data-ttu-id="e6353-135">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="e6353-135">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [<span data-ttu-id="e6353-136">\<add></span><span class="sxs-lookup"><span data-stu-id="e6353-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)  
 [<span data-ttu-id="e6353-137">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="e6353-137">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="e6353-138">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e6353-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="e6353-139">Как: настройте учетные данные для службы федерации</span><span class="sxs-lookup"><span data-stu-id="e6353-139">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
