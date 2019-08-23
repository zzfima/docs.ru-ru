---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 47366c5bb2bd9228268fce3ae6e1fb5ad457dab1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942622"
---
# <a name="nameclaimtype"></a><span data-ttu-id="8f75d-101">\<Намеклаимтипе ></span><span class="sxs-lookup"><span data-stu-id="8f75d-101">\<nameClaimType></span></span>
<span data-ttu-id="8f75d-102">Задает тип утверждения, указывающий <xref:System.Security.Principal.IIdentity.Name%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="8f75d-102">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="8f75d-103">Тип утверждения используется для поиска <xref:System.Security.Claims.Claim> в <xref:System.Security.Claims.ClaimsIdentity> коллекции объектов, возвращаемых <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> методом этого обработчика маркеров.</span><span class="sxs-lookup"><span data-stu-id="8f75d-103">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="8f75d-104">Затем значение соответствующего утверждения задается в качестве имени объекта, <xref:System.Security.Principal.IIdentity> созданного из этого обработчика маркеров.</span><span class="sxs-lookup"><span data-stu-id="8f75d-104">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
 <span data-ttu-id="8f75d-105">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="8f75d-105">\<system.identityModel></span></span>  
<span data-ttu-id="8f75d-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="8f75d-106">\<identityConfiguration></span></span>  
<span data-ttu-id="8f75d-107">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="8f75d-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="8f75d-108">\<add></span><span class="sxs-lookup"><span data-stu-id="8f75d-108">\<add></span></span>  
<span data-ttu-id="8f75d-109">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="8f75d-109">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="8f75d-110">\<Намеклаимтипе ></span><span class="sxs-lookup"><span data-stu-id="8f75d-110">\<nameClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f75d-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f75d-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f75d-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8f75d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8f75d-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8f75d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f75d-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8f75d-114">Attributes</span></span>  
  
|<span data-ttu-id="8f75d-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8f75d-115">Attribute</span></span>|<span data-ttu-id="8f75d-116">Описание</span><span class="sxs-lookup"><span data-stu-id="8f75d-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8f75d-117">value</span><span class="sxs-lookup"><span data-stu-id="8f75d-117">value</span></span>|<span data-ttu-id="8f75d-118">Строка, указывающая URI, который представляет тип утверждения для утверждения, используемого для <xref:System.Security.Principal.IIdentity.Name%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="8f75d-118">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="8f75d-119">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="8f75d-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8f75d-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8f75d-120">Child Elements</span></span>  
 <span data-ttu-id="8f75d-121">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="8f75d-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8f75d-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8f75d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8f75d-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="8f75d-123">Element</span></span>|<span data-ttu-id="8f75d-124">Описание</span><span class="sxs-lookup"><span data-stu-id="8f75d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f75d-125">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="8f75d-125">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="8f75d-126">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , класса или производного класса любого из этих классов.</span><span class="sxs-lookup"><span data-stu-id="8f75d-126">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f75d-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="8f75d-127">Remarks</span></span>  
 <span data-ttu-id="8f75d-128">Элемент задает свойство при<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> инициализации объекта из конфигурации. <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> `<nameClaimType>`</span><span class="sxs-lookup"><span data-stu-id="8f75d-128">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f75d-129">Пример</span><span class="sxs-lookup"><span data-stu-id="8f75d-129">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f75d-130">См. также</span><span class="sxs-lookup"><span data-stu-id="8f75d-130">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
