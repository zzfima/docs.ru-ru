---
title: '&lt;userNameSecurityTokenHandlerRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: dfcaad8b150321fda2a86e601bf57204cbdc1a0e
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47216020"
---
# <a name="ltusernamesecuritytokenhandlerrequirementgt"></a><span data-ttu-id="74396-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="74396-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="74396-103">Предоставляет конфигурацию для <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> классом или производными классами.</span><span class="sxs-lookup"><span data-stu-id="74396-103">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="74396-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="74396-104">\<system.identityModel></span></span>  
<span data-ttu-id="74396-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="74396-105">\<identityConfiguration></span></span>  
<span data-ttu-id="74396-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="74396-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="74396-107">\<add></span><span class="sxs-lookup"><span data-stu-id="74396-107">\<add></span></span>  
<span data-ttu-id="74396-108">\<userNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="74396-108">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74396-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74396-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74396-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="74396-110">Attributes and Elements</span></span>  
 <span data-ttu-id="74396-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="74396-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74396-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="74396-112">Attributes</span></span>  
  
|<span data-ttu-id="74396-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="74396-113">Attribute</span></span>|<span data-ttu-id="74396-114">Описание</span><span class="sxs-lookup"><span data-stu-id="74396-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="74396-115">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="74396-115">membershipProviderName</span></span>|<span data-ttu-id="74396-116">Указывает <xref:System.Web.Security.MembershipProvider> , рекомендуется использовать обработчик токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="74396-116">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74396-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="74396-117">Child Elements</span></span>  
 <span data-ttu-id="74396-118">Нет</span><span class="sxs-lookup"><span data-stu-id="74396-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74396-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="74396-119">Parent Elements</span></span>  
  
|<span data-ttu-id="74396-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="74396-120">Element</span></span>|<span data-ttu-id="74396-121">Описание</span><span class="sxs-lookup"><span data-stu-id="74396-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74396-122">\<add></span><span class="sxs-lookup"><span data-stu-id="74396-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="74396-123">Добавляет обработчик токенов безопасности в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="74396-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74396-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="74396-124">Remarks</span></span>  
 <span data-ttu-id="74396-125">`<userNameSecurityTokenHandlerRequirement>` Наборов элементов <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> свойство при <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> объект инициализирован из конфигурации.</span><span class="sxs-lookup"><span data-stu-id="74396-125">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74396-126">Пример</span><span class="sxs-lookup"><span data-stu-id="74396-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
