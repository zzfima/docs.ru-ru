---
title: '&lt;userNameSecurityTokenHandlerRequirement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 31e0c2cf10b8bc93ade0d417763075c4419ac19f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltusernamesecuritytokenhandlerrequirementgt"></a><span data-ttu-id="1f003-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="1f003-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="1f003-103">Обеспечивает настройку для <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> класса или производных классов.</span><span class="sxs-lookup"><span data-stu-id="1f003-103">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="1f003-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="1f003-104">\<system.identityModel></span></span>  
<span data-ttu-id="1f003-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="1f003-105">\<identityConfiguration></span></span>  
<span data-ttu-id="1f003-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="1f003-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="1f003-107">\<add></span><span class="sxs-lookup"><span data-stu-id="1f003-107">\<add></span></span>  
<span data-ttu-id="1f003-108">\<userNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="1f003-108">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f003-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f003-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f003-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1f003-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1f003-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1f003-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f003-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1f003-112">Attributes</span></span>  
  
|<span data-ttu-id="1f003-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1f003-113">Attribute</span></span>|<span data-ttu-id="1f003-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="1f003-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1f003-115">Используйте</span><span class="sxs-lookup"><span data-stu-id="1f003-115">membershipProviderName</span></span>|<span data-ttu-id="1f003-116">Указывает <xref:System.Web.Security.MembershipProvider> , следует использовать обработчик маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="1f003-116">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1f003-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1f003-117">Child Elements</span></span>  
 <span data-ttu-id="1f003-118">Нет</span><span class="sxs-lookup"><span data-stu-id="1f003-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1f003-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1f003-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1f003-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="1f003-120">Element</span></span>|<span data-ttu-id="1f003-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="1f003-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1f003-122">\<add></span><span class="sxs-lookup"><span data-stu-id="1f003-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="1f003-123">Добавляет обработчик маркеров безопасности в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="1f003-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f003-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="1f003-124">Remarks</span></span>  
 <span data-ttu-id="1f003-125">`<userNameSecurityTokenHandlerRequirement>` Наборы элементов <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> свойство при <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> инициализации объекта из конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1f003-125">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f003-126">Пример</span><span class="sxs-lookup"><span data-stu-id="1f003-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
