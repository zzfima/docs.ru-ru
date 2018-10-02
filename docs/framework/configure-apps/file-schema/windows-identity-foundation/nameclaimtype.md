---
title: '&lt;nameClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: bd4033b2edea7450b66c25f446669b3ded65e9af
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2018
ms.locfileid: "47459834"
---
# <a name="ltnameclaimtypegt"></a><span data-ttu-id="61381-102">&lt;nameClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="61381-102">&lt;nameClaimType&gt;</span></span>
<span data-ttu-id="61381-103">Задает тип утверждения, указывающее <xref:System.Security.Principal.IIdentity.Name%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="61381-103">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="61381-104">Тип утверждения используется для поиска <xref:System.Security.Claims.Claim> в коллекцию <xref:System.Security.Claims.ClaimsIdentity> объектов, возвращенных <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> метод данного обработчика токенов.</span><span class="sxs-lookup"><span data-stu-id="61381-104">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="61381-105">Задайте значение соответствующее утверждение имени <xref:System.Security.Principal.IIdentity> созданные из этого обработчика токенов.</span><span class="sxs-lookup"><span data-stu-id="61381-105">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
 <span data-ttu-id="61381-106">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="61381-106">\<system.identityModel></span></span>  
<span data-ttu-id="61381-107">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="61381-107">\<identityConfiguration></span></span>  
<span data-ttu-id="61381-108">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="61381-108">\<securityTokenHandlers></span></span>  
<span data-ttu-id="61381-109">\<add></span><span class="sxs-lookup"><span data-stu-id="61381-109">\<add></span></span>  
<span data-ttu-id="61381-110">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="61381-110">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="61381-111">\<nameClaimType ></span><span class="sxs-lookup"><span data-stu-id="61381-111">\<nameClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61381-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61381-112">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <nameClaimType value=xs:string>  
          </nameClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61381-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="61381-113">Attributes and Elements</span></span>  
 <span data-ttu-id="61381-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="61381-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61381-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="61381-115">Attributes</span></span>  
  
|<span data-ttu-id="61381-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="61381-116">Attribute</span></span>|<span data-ttu-id="61381-117">Описание</span><span class="sxs-lookup"><span data-stu-id="61381-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="61381-118">value</span><span class="sxs-lookup"><span data-stu-id="61381-118">value</span></span>|<span data-ttu-id="61381-119">Строка, указывающая URI, представляющий тип требования утверждения для <xref:System.Security.Principal.IIdentity.Name%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="61381-119">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="61381-120">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="61381-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61381-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="61381-121">Child Elements</span></span>  
 <span data-ttu-id="61381-122">Нет</span><span class="sxs-lookup"><span data-stu-id="61381-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="61381-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="61381-123">Parent Elements</span></span>  
  
|<span data-ttu-id="61381-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="61381-124">Element</span></span>|<span data-ttu-id="61381-125">Описание</span><span class="sxs-lookup"><span data-stu-id="61381-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61381-126">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="61381-126">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="61381-127">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класс или класс, производный от любого из этих классов.</span><span class="sxs-lookup"><span data-stu-id="61381-127">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61381-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="61381-128">Remarks</span></span>  
 <span data-ttu-id="61381-129">`<nameClaimType>` Наборов элементов <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> свойство при <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> объект инициализирован из конфигурации.</span><span class="sxs-lookup"><span data-stu-id="61381-129">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61381-130">Пример</span><span class="sxs-lookup"><span data-stu-id="61381-130">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="61381-131">См. также</span><span class="sxs-lookup"><span data-stu-id="61381-131">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
