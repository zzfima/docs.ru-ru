---
title: '&lt;RoleClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 565bf30d334c62c8132c60f411e89f7b260c54f1
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47084349"
---
# <a name="ltroleclaimtypegt"></a><span data-ttu-id="3a973-102">&lt;RoleClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="3a973-102">&lt;roleClaimType&gt;</span></span>
<span data-ttu-id="3a973-103">Указывает тип утверждения, определяет тип утверждения роли в коллекции <xref:System.Security.Claims.ClaimsIdentity> объектов, возвращенных <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> метод из обработчика токенов.</span><span class="sxs-lookup"><span data-stu-id="3a973-103">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="3a973-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="3a973-104">\<system.identityModel></span></span>  
<span data-ttu-id="3a973-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3a973-105">\<identityConfiguration></span></span>  
<span data-ttu-id="3a973-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="3a973-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="3a973-107">\<add></span><span class="sxs-lookup"><span data-stu-id="3a973-107">\<add></span></span>  
<span data-ttu-id="3a973-108">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="3a973-108">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="3a973-109">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="3a973-109">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a973-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a973-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a973-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3a973-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3a973-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3a973-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a973-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3a973-113">Attributes</span></span>  
  
|<span data-ttu-id="3a973-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3a973-114">Attribute</span></span>|<span data-ttu-id="3a973-115">Описание</span><span class="sxs-lookup"><span data-stu-id="3a973-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3a973-116">value</span><span class="sxs-lookup"><span data-stu-id="3a973-116">value</span></span>|<span data-ttu-id="3a973-117">Строка, указывающая URI, представляющий тип требования утверждения для тип утверждения роли.</span><span class="sxs-lookup"><span data-stu-id="3a973-117">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a973-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3a973-118">Child Elements</span></span>  
 <span data-ttu-id="3a973-119">Нет</span><span class="sxs-lookup"><span data-stu-id="3a973-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a973-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3a973-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3a973-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="3a973-121">Element</span></span>|<span data-ttu-id="3a973-122">Описание</span><span class="sxs-lookup"><span data-stu-id="3a973-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a973-123">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="3a973-123">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="3a973-124">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класс или класс, производный от любого из этих классов.</span><span class="sxs-lookup"><span data-stu-id="3a973-124">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a973-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="3a973-125">Remarks</span></span>  
 <span data-ttu-id="3a973-126">`<roleClaimType>` Наборов элементов <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> свойство при <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> объект инициализирован из конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3a973-126">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a973-127">Пример</span><span class="sxs-lookup"><span data-stu-id="3a973-127">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a973-128">См. также</span><span class="sxs-lookup"><span data-stu-id="3a973-128">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
