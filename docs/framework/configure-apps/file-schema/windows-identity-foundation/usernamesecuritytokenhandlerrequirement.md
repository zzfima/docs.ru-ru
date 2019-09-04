---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: 5863c01e97e7f5fb6fe07c43174c0d6cb7a0a25d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251739"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="18353-101">\<Усернамесекурититокенхандлеррекуиремент ></span><span class="sxs-lookup"><span data-stu-id="18353-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="18353-102">Предоставляет конфигурацию для <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> класса или производных классов.</span><span class="sxs-lookup"><span data-stu-id="18353-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="18353-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="18353-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="18353-104">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="18353-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="18353-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="18353-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="18353-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="18353-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="18353-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Добавить >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="18353-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="18353-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Усернамесекурититокенхандлеррекуиремент >**</span><span class="sxs-lookup"><span data-stu-id="18353-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameSecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18353-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18353-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
        <userNameSecurityTokenHandlerRequirement membershipProviderName=xs:string >  
        </userNameSecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18353-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="18353-110">Attributes and Elements</span></span>  
 <span data-ttu-id="18353-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="18353-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18353-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="18353-112">Attributes</span></span>  
  
|<span data-ttu-id="18353-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="18353-113">Attribute</span></span>|<span data-ttu-id="18353-114">Описание</span><span class="sxs-lookup"><span data-stu-id="18353-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="18353-115">мембершиппровидернаме</span><span class="sxs-lookup"><span data-stu-id="18353-115">membershipProviderName</span></span>|<span data-ttu-id="18353-116"><xref:System.Web.Security.MembershipProvider> Указывает, который должен использоваться обработчиком маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="18353-116">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18353-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="18353-117">Child Elements</span></span>  
 <span data-ttu-id="18353-118">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="18353-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="18353-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="18353-119">Parent Elements</span></span>  
  
|<span data-ttu-id="18353-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="18353-120">Element</span></span>|<span data-ttu-id="18353-121">Описание</span><span class="sxs-lookup"><span data-stu-id="18353-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18353-122">\<add></span><span class="sxs-lookup"><span data-stu-id="18353-122">\<add></span></span>](add.md)|<span data-ttu-id="18353-123">Добавляет указанный обработчик маркеров безопасности в коллекцию обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="18353-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18353-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="18353-124">Remarks</span></span>  
 <span data-ttu-id="18353-125">Элемент задает свойство при<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> инициализации объекта из конфигурации. <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> `<userNameSecurityTokenHandlerRequirement>`</span><span class="sxs-lookup"><span data-stu-id="18353-125">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18353-126">Пример</span><span class="sxs-lookup"><span data-stu-id="18353-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
