---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 4bf8ad2f70499edfc72dd9fcd9a5d8a0aafbbc66
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251941"
---
# <a name="nameclaimtype"></a><span data-ttu-id="f7070-101">\<Намеклаимтипе ></span><span class="sxs-lookup"><span data-stu-id="f7070-101">\<nameClaimType></span></span>
<span data-ttu-id="f7070-102">Задает тип утверждения, указывающий <xref:System.Security.Principal.IIdentity.Name%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="f7070-102">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="f7070-103">Тип утверждения используется для поиска <xref:System.Security.Claims.Claim> в <xref:System.Security.Claims.ClaimsIdentity> коллекции объектов, возвращаемых <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> методом этого обработчика маркеров.</span><span class="sxs-lookup"><span data-stu-id="f7070-103">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="f7070-104">Затем значение соответствующего утверждения задается в качестве имени объекта, <xref:System.Security.Principal.IIdentity> созданного из этого обработчика маркеров.</span><span class="sxs-lookup"><span data-stu-id="f7070-104">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
<span data-ttu-id="f7070-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f7070-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f7070-106">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="f7070-106">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="f7070-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="f7070-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="f7070-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="f7070-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="f7070-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Добавить >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="f7070-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="f7070-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<samlSecurityTokenRequirement >** ](samlsecuritytokenrequirement.md)</span><span class="sxs-lookup"><span data-stu-id="f7070-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)</span></span>\
<span data-ttu-id="f7070-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Намеклаимтипе >**</span><span class="sxs-lookup"><span data-stu-id="f7070-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameClaimType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7070-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7070-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7070-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f7070-113">Attributes and Elements</span></span>  
 <span data-ttu-id="f7070-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f7070-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7070-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f7070-115">Attributes</span></span>  
  
|<span data-ttu-id="f7070-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f7070-116">Attribute</span></span>|<span data-ttu-id="f7070-117">Описание</span><span class="sxs-lookup"><span data-stu-id="f7070-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f7070-118">value</span><span class="sxs-lookup"><span data-stu-id="f7070-118">value</span></span>|<span data-ttu-id="f7070-119">Строка, указывающая URI, который представляет тип утверждения для утверждения, используемого для <xref:System.Security.Principal.IIdentity.Name%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="f7070-119">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="f7070-120">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f7070-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7070-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f7070-121">Child Elements</span></span>  
 <span data-ttu-id="f7070-122">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="f7070-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7070-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f7070-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f7070-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="f7070-124">Element</span></span>|<span data-ttu-id="f7070-125">Описание</span><span class="sxs-lookup"><span data-stu-id="f7070-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7070-126">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="f7070-126">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="f7070-127">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , класса или производного класса любого из этих классов.</span><span class="sxs-lookup"><span data-stu-id="f7070-127">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7070-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="f7070-128">Remarks</span></span>  
 <span data-ttu-id="f7070-129">Элемент задает свойство при<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> инициализации объекта из конфигурации. <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> `<nameClaimType>`</span><span class="sxs-lookup"><span data-stu-id="f7070-129">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7070-130">Пример</span><span class="sxs-lookup"><span data-stu-id="f7070-130">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f7070-131">См. также</span><span class="sxs-lookup"><span data-stu-id="f7070-131">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
