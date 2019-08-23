---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: fed8964e03b80e365fdc5eafd45b4fc372a6e352
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944257"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="58252-101">\<Усернамесекурититокенхандлеррекуиремент ></span><span class="sxs-lookup"><span data-stu-id="58252-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="58252-102">Предоставляет конфигурацию для <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> класса или производных классов.</span><span class="sxs-lookup"><span data-stu-id="58252-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="58252-103">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="58252-103">\<system.identityModel></span></span>  
<span data-ttu-id="58252-104">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="58252-104">\<identityConfiguration></span></span>  
<span data-ttu-id="58252-105">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="58252-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="58252-106">\<add></span><span class="sxs-lookup"><span data-stu-id="58252-106">\<add></span></span>  
<span data-ttu-id="58252-107">\<Усернамесекурититокенхандлеррекуиремент ></span><span class="sxs-lookup"><span data-stu-id="58252-107">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58252-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="58252-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58252-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="58252-109">Attributes and Elements</span></span>  
 <span data-ttu-id="58252-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="58252-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58252-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="58252-111">Attributes</span></span>  
  
|<span data-ttu-id="58252-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="58252-112">Attribute</span></span>|<span data-ttu-id="58252-113">Описание</span><span class="sxs-lookup"><span data-stu-id="58252-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="58252-114">мембершиппровидернаме</span><span class="sxs-lookup"><span data-stu-id="58252-114">membershipProviderName</span></span>|<span data-ttu-id="58252-115"><xref:System.Web.Security.MembershipProvider> Указывает, который должен использоваться обработчиком маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="58252-115">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58252-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="58252-116">Child Elements</span></span>  
 <span data-ttu-id="58252-117">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="58252-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="58252-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="58252-118">Parent Elements</span></span>  
  
|<span data-ttu-id="58252-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="58252-119">Element</span></span>|<span data-ttu-id="58252-120">Описание</span><span class="sxs-lookup"><span data-stu-id="58252-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58252-121">\<add></span><span class="sxs-lookup"><span data-stu-id="58252-121">\<add></span></span>](add.md)|<span data-ttu-id="58252-122">Добавляет указанный обработчик маркеров безопасности в коллекцию обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="58252-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58252-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="58252-123">Remarks</span></span>  
 <span data-ttu-id="58252-124">Элемент задает свойство при<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> инициализации объекта из конфигурации. <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> `<userNameSecurityTokenHandlerRequirement>`</span><span class="sxs-lookup"><span data-stu-id="58252-124">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58252-125">Пример</span><span class="sxs-lookup"><span data-stu-id="58252-125">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
