---
title: <allowedAudienceUris>
ms.date: 03/30/2017
ms.assetid: 0f4dc73d-d95d-4193-9755-7df4cf2b8e1c
ms.openlocfilehash: d079c0a03f0c88bab04e3fe2e857e0be4d3af11e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283612"
---
# <a name="allowedaudienceuris"></a><span data-ttu-id="54aec-101">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="54aec-101">\<allowedAudienceUris></span></span>
<span data-ttu-id="54aec-102">Представляет коллекцию целевых универсальных кодов ресурса (URI), для которых может быть задан маркер безопасности <xref:System.IdentityModel.Tokens.SamlSecurityToken>, чтобы они считались допустимыми для экземпляра <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="54aec-102">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
 <span data-ttu-id="54aec-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="54aec-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="54aec-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="54aec-104">\<behaviors></span></span>  
<span data-ttu-id="54aec-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="54aec-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="54aec-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="54aec-106">\<behavior></span></span>  
<span data-ttu-id="54aec-107">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="54aec-107">\<serviceCredentials></span></span>  
<span data-ttu-id="54aec-108">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="54aec-108">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="54aec-109">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="54aec-109">\<allowedAudienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54aec-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="54aec-110">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>
  <add allowedAudienceUri="String" />
</allowedAudienceUris>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54aec-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="54aec-111">Attributes and Elements</span></span>  
 <span data-ttu-id="54aec-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="54aec-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54aec-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="54aec-113">Attributes</span></span>  
 <span data-ttu-id="54aec-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="54aec-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="54aec-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="54aec-115">Child Elements</span></span>  
  
|<span data-ttu-id="54aec-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="54aec-116">Element</span></span>|<span data-ttu-id="54aec-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="54aec-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54aec-118">\<add></span><span class="sxs-lookup"><span data-stu-id="54aec-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)|<span data-ttu-id="54aec-119">Добавляет целевой универсальный код ресурса, для которого может быть задан маркер безопасности <xref:System.IdentityModel.Tokens.SamlSecurityToken>, чтобы считаться допустимым для экземпляра <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="54aec-119">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="54aec-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="54aec-120">Parent Elements</span></span>  
  
|<span data-ttu-id="54aec-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="54aec-121">Element</span></span>|<span data-ttu-id="54aec-122">Описание</span><span class="sxs-lookup"><span data-stu-id="54aec-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54aec-123">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="54aec-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="54aec-124">Задает маркер, выданный в качестве учетных данных службы.</span><span class="sxs-lookup"><span data-stu-id="54aec-124">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54aec-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="54aec-125">Remarks</span></span>  
 <span data-ttu-id="54aec-126">Данную коллекцию следует использовать в федеративном приложении, которое использует службу маркеров безопасности (STS), выдающую маркеры безопасности <xref:System.IdentityModel.Tokens.SamlSecurityToken>.</span><span class="sxs-lookup"><span data-stu-id="54aec-126">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="54aec-127">При выпуске маркера безопасности служба STS также может указать универсальный код ресурса (URI) веб-служб, для которых предназначен маркер безопасности, добавив выражение <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> к маркеру безопасности.</span><span class="sxs-lookup"><span data-stu-id="54aec-127">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="54aec-128">Это позволяет коду <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> для веб-службы получателя проверить, что выданный маркер безопасности предназначен для данной службы, указав на необходимость выполнения соответствующей проверки. Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="54aec-128">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
-   <span data-ttu-id="54aec-129">Присвойте атрибуту `audienceUriMode` элемента `<issuedTokenAuthentication>` значение <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> или <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span><span class="sxs-lookup"><span data-stu-id="54aec-129">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
-   <span data-ttu-id="54aec-130">Задайте набор допустимых универсальных кодов ресурса (URI), добавив их в данную коллекцию.</span><span class="sxs-lookup"><span data-stu-id="54aec-130">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="54aec-131">Дополнительные сведения см. в разделе <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="54aec-131">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="54aec-132">Дополнительные сведения об использовании данного элемента конфигурации см. в разделе [как: Настройка учетных данных службы федерации](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="54aec-132">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54aec-133">См. также</span><span class="sxs-lookup"><span data-stu-id="54aec-133">See also</span></span>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>
- [<span data-ttu-id="54aec-134">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="54aec-134">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="54aec-135">\<add></span><span class="sxs-lookup"><span data-stu-id="54aec-135">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)
- [<span data-ttu-id="54aec-136">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="54aec-136">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="54aec-137">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="54aec-137">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="54aec-138">Практическое руководство. Настройка учетных данных службы федерации</span><span class="sxs-lookup"><span data-stu-id="54aec-138">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
