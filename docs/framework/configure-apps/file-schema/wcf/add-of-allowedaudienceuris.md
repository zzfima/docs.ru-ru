---
title: <add> из <allowedAudienceUris>
ms.date: 03/30/2017
ms.assetid: 4e7b7637-e0ea-4a91-988f-6b6ef28d9fc3
ms.openlocfilehash: 64f0dd5c97ddfcd2fffd8ff4820d02af8c1ced54
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926883"
---
# <a name="add-of-allowedaudienceuris"></a><span data-ttu-id="a08f4-102">\<Добавление > \<> алловедаудиенцеурис</span><span class="sxs-lookup"><span data-stu-id="a08f4-102">\<add> of \<allowedAudienceUris></span></span>
<span data-ttu-id="a08f4-103">Добавляет целевой универсальный код ресурса, для которого может быть задан маркер безопасности <xref:System.IdentityModel.Tokens.SamlSecurityToken>, чтобы считаться допустимым для экземпляра <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="a08f4-103">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
 <span data-ttu-id="a08f4-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a08f4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a08f4-105">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="a08f4-105">\<behaviors></span></span>  
<span data-ttu-id="a08f4-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a08f4-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="a08f4-107">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="a08f4-107">\<behavior></span></span>  
<span data-ttu-id="a08f4-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="a08f4-108">\<serviceCredentials></span></span>  
<span data-ttu-id="a08f4-109">\<Иссуедтокенаусентикатион ></span><span class="sxs-lookup"><span data-stu-id="a08f4-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="a08f4-110">\<Алловедаудиенцеурис ></span><span class="sxs-lookup"><span data-stu-id="a08f4-110">\<allowedAudienceUris></span></span>  
<span data-ttu-id="a08f4-111">\<Добавление элемента > для \<алловедаудиенцеурис ></span><span class="sxs-lookup"><span data-stu-id="a08f4-111">\<add> element for \<allowedAudienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a08f4-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a08f4-112">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>
  <add allowedAudienceUri="String" />
</allowedAudienceUris>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a08f4-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a08f4-113">Attributes and Elements</span></span>  
 <span data-ttu-id="a08f4-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a08f4-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a08f4-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a08f4-115">Attributes</span></span>  
  
|<span data-ttu-id="a08f4-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a08f4-116">Attribute</span></span>|<span data-ttu-id="a08f4-117">Описание</span><span class="sxs-lookup"><span data-stu-id="a08f4-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a08f4-118">allowedAudienceUri</span><span class="sxs-lookup"><span data-stu-id="a08f4-118">allowedAudienceUri</span></span>|<span data-ttu-id="a08f4-119">Строка, содержащая целевой универсальный код ресурса, для которого может быть задан маркер безопасности <xref:System.IdentityModel.Tokens.SamlSecurityToken>, чтобы считаться допустимым в экземпляре <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="a08f4-119">A string that contains a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a08f4-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a08f4-120">Child Elements</span></span>  
 <span data-ttu-id="a08f4-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="a08f4-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a08f4-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a08f4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a08f4-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="a08f4-123">Element</span></span>|<span data-ttu-id="a08f4-124">Описание</span><span class="sxs-lookup"><span data-stu-id="a08f4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a08f4-125">\<Алловедаудиенцеурис ></span><span class="sxs-lookup"><span data-stu-id="a08f4-125">\<allowedAudienceUris></span></span>](allowedaudienceuris.md)|<span data-ttu-id="a08f4-126">Представляет коллекцию целевых универсальных кодов ресурса (URI), для которых может быть задан маркер безопасности <xref:System.IdentityModel.Tokens.SamlSecurityToken>, чтобы они считались допустимыми для экземпляра <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="a08f4-126">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a08f4-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="a08f4-127">Remarks</span></span>  
 <span data-ttu-id="a08f4-128">Данную коллекцию следует использовать в федеративном приложении, которое использует службу маркеров безопасности (STS), выдающую маркеры безопасности <xref:System.IdentityModel.Tokens.SamlSecurityToken>.</span><span class="sxs-lookup"><span data-stu-id="a08f4-128">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="a08f4-129">При выпуске маркера безопасности служба STS также может указать универсальный код ресурса (URI) веб-служб, для которых предназначен маркер безопасности, добавив выражение <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> к маркеру безопасности.</span><span class="sxs-lookup"><span data-stu-id="a08f4-129">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="a08f4-130">Это позволяет коду <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> для веб-службы получателя проверить, что выданный маркер безопасности предназначен для данной службы, указав на необходимость выполнения соответствующей проверки. Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a08f4-130">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
- <span data-ttu-id="a08f4-131">Присвойте атрибуту `audienceUriMode` элемента `<issuedTokenAuthentication>` значение <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> или <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span><span class="sxs-lookup"><span data-stu-id="a08f4-131">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
- <span data-ttu-id="a08f4-132">Задайте набор допустимых универсальных кодов ресурса (URI), добавив их в данную коллекцию.</span><span class="sxs-lookup"><span data-stu-id="a08f4-132">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="a08f4-133">Дополнительные сведения см. в разделе <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="a08f4-133">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="a08f4-134">Дополнительные сведения об использовании этого элемента конфигурации см. в [разделе как Настройте учетные данные на](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)служба Федерации.</span><span class="sxs-lookup"><span data-stu-id="a08f4-134">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a08f4-135">См. также</span><span class="sxs-lookup"><span data-stu-id="a08f4-135">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>
- [<span data-ttu-id="a08f4-136">\<Алловедаудиенцеурис ></span><span class="sxs-lookup"><span data-stu-id="a08f4-136">\<allowedAudienceUris></span></span>](allowedaudienceuris.md)
- [<span data-ttu-id="a08f4-137">\<Иссуедтокенаусентикатион ></span><span class="sxs-lookup"><span data-stu-id="a08f4-137">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="a08f4-138">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="a08f4-138">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="a08f4-139">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="a08f4-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a08f4-140">Практическое руководство. Настройка учетных данных на служба федерации</span><span class="sxs-lookup"><span data-stu-id="a08f4-140">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
