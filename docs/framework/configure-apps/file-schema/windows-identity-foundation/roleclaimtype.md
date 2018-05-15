---
title: '&lt;roleClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 909df1bd6054d9737f91c30c3c6b2d68b932281c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltroleclaimtypegt"></a><span data-ttu-id="b07bb-102">&lt;roleClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="b07bb-102">&lt;roleClaimType&gt;</span></span>
<span data-ttu-id="b07bb-103">Указывает тип утверждения, который определяет тип утверждения роли в коллекцию <xref:System.Security.Claims.ClaimsIdentity> объектов, возвращенных <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> метод обработчика токенов.</span><span class="sxs-lookup"><span data-stu-id="b07bb-103">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="b07bb-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="b07bb-104">\<system.identityModel></span></span>  
<span data-ttu-id="b07bb-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b07bb-105">\<identityConfiguration></span></span>  
<span data-ttu-id="b07bb-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="b07bb-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b07bb-107">\<add></span><span class="sxs-lookup"><span data-stu-id="b07bb-107">\<add></span></span>  
<span data-ttu-id="b07bb-108">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="b07bb-108">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="b07bb-109">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="b07bb-109">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b07bb-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b07bb-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <roleClaimType value=xs:string>  
          </roleClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b07bb-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b07bb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b07bb-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b07bb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b07bb-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b07bb-113">Attributes</span></span>  
  
|<span data-ttu-id="b07bb-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b07bb-114">Attribute</span></span>|<span data-ttu-id="b07bb-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b07bb-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b07bb-116">value</span><span class="sxs-lookup"><span data-stu-id="b07bb-116">value</span></span>|<span data-ttu-id="b07bb-117">Строка, указывающая URI, который представляет тип утверждений утверждения для типа утверждения роли.</span><span class="sxs-lookup"><span data-stu-id="b07bb-117">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b07bb-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b07bb-118">Child Elements</span></span>  
 <span data-ttu-id="b07bb-119">Нет</span><span class="sxs-lookup"><span data-stu-id="b07bb-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b07bb-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b07bb-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b07bb-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="b07bb-121">Element</span></span>|<span data-ttu-id="b07bb-122">Описание</span><span class="sxs-lookup"><span data-stu-id="b07bb-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b07bb-123">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="b07bb-123">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="b07bb-124">Обеспечивает настройку для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса или производного класса от любого из этих классов.</span><span class="sxs-lookup"><span data-stu-id="b07bb-124">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b07bb-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="b07bb-125">Remarks</span></span>  
 <span data-ttu-id="b07bb-126">`<roleClaimType>` Наборы элементов <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> свойство при <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> инициализации объекта из конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b07bb-126">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b07bb-127">Пример</span><span class="sxs-lookup"><span data-stu-id="b07bb-127">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b07bb-128">См. также</span><span class="sxs-lookup"><span data-stu-id="b07bb-128">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
