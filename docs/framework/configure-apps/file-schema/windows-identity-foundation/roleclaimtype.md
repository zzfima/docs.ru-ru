---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 0ce2e06ee895d09de193bac1fe7038e71794dda4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942543"
---
# <a name="roleclaimtype"></a><span data-ttu-id="aca0d-101">\<Ролеклаимтипе ></span><span class="sxs-lookup"><span data-stu-id="aca0d-101">\<roleClaimType></span></span>
<span data-ttu-id="aca0d-102">Указывает тип утверждения, определяющего утверждения типа роли в коллекции <xref:System.Security.Claims.ClaimsIdentity> объектов, возвращаемых <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> методом обработчика маркеров.</span><span class="sxs-lookup"><span data-stu-id="aca0d-102">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="aca0d-103">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="aca0d-103">\<system.identityModel></span></span>  
<span data-ttu-id="aca0d-104">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="aca0d-104">\<identityConfiguration></span></span>  
<span data-ttu-id="aca0d-105">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="aca0d-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="aca0d-106">\<add></span><span class="sxs-lookup"><span data-stu-id="aca0d-106">\<add></span></span>  
<span data-ttu-id="aca0d-107">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="aca0d-107">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="aca0d-108">\<Ролеклаимтипе ></span><span class="sxs-lookup"><span data-stu-id="aca0d-108">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aca0d-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aca0d-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aca0d-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aca0d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="aca0d-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aca0d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aca0d-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aca0d-112">Attributes</span></span>  
  
|<span data-ttu-id="aca0d-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="aca0d-113">Attribute</span></span>|<span data-ttu-id="aca0d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="aca0d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aca0d-115">value</span><span class="sxs-lookup"><span data-stu-id="aca0d-115">value</span></span>|<span data-ttu-id="aca0d-116">Строка, указывающая URI, который представляет тип утверждения, используемого для типа утверждения роли.</span><span class="sxs-lookup"><span data-stu-id="aca0d-116">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aca0d-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aca0d-117">Child Elements</span></span>  
 <span data-ttu-id="aca0d-118">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="aca0d-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aca0d-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aca0d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="aca0d-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="aca0d-120">Element</span></span>|<span data-ttu-id="aca0d-121">Описание</span><span class="sxs-lookup"><span data-stu-id="aca0d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aca0d-122">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="aca0d-122">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="aca0d-123">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , класса или производного класса любого из этих классов.</span><span class="sxs-lookup"><span data-stu-id="aca0d-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aca0d-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="aca0d-124">Remarks</span></span>  
 <span data-ttu-id="aca0d-125">Элемент задает свойство при<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> инициализации объекта из конфигурации. <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> `<roleClaimType>`</span><span class="sxs-lookup"><span data-stu-id="aca0d-125">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aca0d-126">Пример</span><span class="sxs-lookup"><span data-stu-id="aca0d-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="aca0d-127">См. также</span><span class="sxs-lookup"><span data-stu-id="aca0d-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
