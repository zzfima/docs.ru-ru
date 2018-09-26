---
title: '&lt;userNameSecurityTokenHandlerRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: dfcaad8b150321fda2a86e601bf57204cbdc1a0e
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075040"
---
# <a name="ltusernamesecuritytokenhandlerrequirementgt"></a><span data-ttu-id="7a08e-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="7a08e-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="7a08e-103">Предоставляет конфигурацию для <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> классом или производными классами.</span><span class="sxs-lookup"><span data-stu-id="7a08e-103">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="7a08e-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="7a08e-104">\<system.identityModel></span></span>  
<span data-ttu-id="7a08e-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="7a08e-105">\<identityConfiguration></span></span>  
<span data-ttu-id="7a08e-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="7a08e-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="7a08e-107">\<add></span><span class="sxs-lookup"><span data-stu-id="7a08e-107">\<add></span></span>  
<span data-ttu-id="7a08e-108">\<userNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="7a08e-108">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a08e-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a08e-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a08e-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7a08e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7a08e-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7a08e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a08e-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7a08e-112">Attributes</span></span>  
  
|<span data-ttu-id="7a08e-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7a08e-113">Attribute</span></span>|<span data-ttu-id="7a08e-114">Описание</span><span class="sxs-lookup"><span data-stu-id="7a08e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7a08e-115">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="7a08e-115">membershipProviderName</span></span>|<span data-ttu-id="7a08e-116">Указывает <xref:System.Web.Security.MembershipProvider> , рекомендуется использовать обработчик токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="7a08e-116">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7a08e-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7a08e-117">Child Elements</span></span>  
 <span data-ttu-id="7a08e-118">Нет</span><span class="sxs-lookup"><span data-stu-id="7a08e-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7a08e-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7a08e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="7a08e-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="7a08e-120">Element</span></span>|<span data-ttu-id="7a08e-121">Описание</span><span class="sxs-lookup"><span data-stu-id="7a08e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7a08e-122">\<add></span><span class="sxs-lookup"><span data-stu-id="7a08e-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="7a08e-123">Добавляет обработчик токенов безопасности в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="7a08e-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a08e-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="7a08e-124">Remarks</span></span>  
 <span data-ttu-id="7a08e-125">`<userNameSecurityTokenHandlerRequirement>` Наборов элементов <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> свойство при <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> объект инициализирован из конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7a08e-125">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a08e-126">Пример</span><span class="sxs-lookup"><span data-stu-id="7a08e-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
