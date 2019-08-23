---
title: <allowedAudienceUris>
ms.date: 03/30/2017
ms.assetid: 0f4dc73d-d95d-4193-9755-7df4cf2b8e1c
ms.openlocfilehash: 03888600a89d72f5216c8c8cac21c9da96879ba8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919975"
---
# <a name="allowedaudienceuris"></a><span data-ttu-id="1b312-101">\<Алловедаудиенцеурис ></span><span class="sxs-lookup"><span data-stu-id="1b312-101">\<allowedAudienceUris></span></span>
<span data-ttu-id="1b312-102">Представляет коллекцию целевых универсальных кодов ресурса (URI), для которых может быть задан маркер безопасности <xref:System.IdentityModel.Tokens.SamlSecurityToken>, чтобы они считались допустимыми для экземпляра <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="1b312-102">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
 <span data-ttu-id="1b312-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1b312-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="1b312-104">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="1b312-104">\<behaviors></span></span>  
<span data-ttu-id="1b312-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1b312-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="1b312-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="1b312-106">\<behavior></span></span>  
<span data-ttu-id="1b312-107">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="1b312-107">\<serviceCredentials></span></span>  
<span data-ttu-id="1b312-108">\<Иссуедтокенаусентикатион ></span><span class="sxs-lookup"><span data-stu-id="1b312-108">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="1b312-109">\<Алловедаудиенцеурис ></span><span class="sxs-lookup"><span data-stu-id="1b312-109">\<allowedAudienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b312-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b312-110">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>
  <add allowedAudienceUri="String" />
</allowedAudienceUris>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b312-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1b312-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1b312-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1b312-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b312-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1b312-113">Attributes</span></span>  
 <span data-ttu-id="1b312-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="1b312-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1b312-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1b312-115">Child Elements</span></span>  
  
|<span data-ttu-id="1b312-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="1b312-116">Element</span></span>|<span data-ttu-id="1b312-117">Описание</span><span class="sxs-lookup"><span data-stu-id="1b312-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b312-118">\<add></span><span class="sxs-lookup"><span data-stu-id="1b312-118">\<add></span></span>](add-of-allowedaudienceuris.md)|<span data-ttu-id="1b312-119">Добавляет целевой универсальный код ресурса, для которого может быть задан маркер безопасности <xref:System.IdentityModel.Tokens.SamlSecurityToken>, чтобы считаться допустимым для экземпляра <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="1b312-119">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1b312-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1b312-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1b312-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="1b312-121">Element</span></span>|<span data-ttu-id="1b312-122">Описание</span><span class="sxs-lookup"><span data-stu-id="1b312-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b312-123">\<Иссуедтокенаусентикатион ></span><span class="sxs-lookup"><span data-stu-id="1b312-123">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="1b312-124">Задает маркер, выданный в качестве учетных данных службы.</span><span class="sxs-lookup"><span data-stu-id="1b312-124">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b312-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="1b312-125">Remarks</span></span>  
 <span data-ttu-id="1b312-126">Данную коллекцию следует использовать в федеративном приложении, которое использует службу маркеров безопасности (STS), выдающую маркеры безопасности <xref:System.IdentityModel.Tokens.SamlSecurityToken>.</span><span class="sxs-lookup"><span data-stu-id="1b312-126">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="1b312-127">При выпуске маркера безопасности служба STS также может указать универсальный код ресурса (URI) веб-служб, для которых предназначен маркер безопасности, добавив выражение <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> к маркеру безопасности.</span><span class="sxs-lookup"><span data-stu-id="1b312-127">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="1b312-128">Это позволяет коду <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> для веб-службы получателя проверить, что выданный маркер безопасности предназначен для данной службы, указав на необходимость выполнения соответствующей проверки. Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1b312-128">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
- <span data-ttu-id="1b312-129">Присвойте атрибуту `audienceUriMode` элемента `<issuedTokenAuthentication>` значение <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> или <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span><span class="sxs-lookup"><span data-stu-id="1b312-129">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
- <span data-ttu-id="1b312-130">Задайте набор допустимых универсальных кодов ресурса (URI), добавив их в данную коллекцию.</span><span class="sxs-lookup"><span data-stu-id="1b312-130">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="1b312-131">Дополнительные сведения см. в разделе <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="1b312-131">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="1b312-132">Дополнительные сведения об использовании этого элемента конфигурации см. в [разделе как Настройте учетные данные на](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)служба Федерации.</span><span class="sxs-lookup"><span data-stu-id="1b312-132">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b312-133">См. также</span><span class="sxs-lookup"><span data-stu-id="1b312-133">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>
- [<span data-ttu-id="1b312-134">\<Иссуедтокенаусентикатион ></span><span class="sxs-lookup"><span data-stu-id="1b312-134">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="1b312-135">\<add></span><span class="sxs-lookup"><span data-stu-id="1b312-135">\<add></span></span>](add-of-allowedaudienceuris.md)
- [<span data-ttu-id="1b312-136">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="1b312-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="1b312-137">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="1b312-137">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="1b312-138">Практическое руководство. Настройка учетных данных на служба федерации</span><span class="sxs-lookup"><span data-stu-id="1b312-138">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
