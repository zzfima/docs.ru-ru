---
title: '&lt;sessionTokenRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6c40948633eaf892db06e9bba756158dfc3c4a2e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754994"
---
# <a name="ltsessiontokenrequirementgt"></a><span data-ttu-id="deaf8-102">&lt;sessionTokenRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="deaf8-102">&lt;sessionTokenRequirement&gt;</span></span>
<span data-ttu-id="deaf8-103">Обеспечивает настройку для <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> класса или производных классов.</span><span class="sxs-lookup"><span data-stu-id="deaf8-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="deaf8-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="deaf8-104">\<system.identityModel></span></span>  
<span data-ttu-id="deaf8-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="deaf8-105">\<identityConfiguration></span></span>  
<span data-ttu-id="deaf8-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="deaf8-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="deaf8-107">\<add></span><span class="sxs-lookup"><span data-stu-id="deaf8-107">\<add></span></span>  
<span data-ttu-id="deaf8-108">\<sessionTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="deaf8-108">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="deaf8-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="deaf8-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">  
        <sessionTokenRequirement lifetime=TimeSpan >  
        </sessionTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="deaf8-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="deaf8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="deaf8-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="deaf8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="deaf8-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="deaf8-112">Attributes</span></span>  
  
|<span data-ttu-id="deaf8-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="deaf8-113">Attribute</span></span>|<span data-ttu-id="deaf8-114">Описание</span><span class="sxs-lookup"><span data-stu-id="deaf8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="deaf8-115">время существования</span><span class="sxs-lookup"><span data-stu-id="deaf8-115">lifetime</span></span>|<span data-ttu-id="deaf8-116">Задает время существования маркеров сеанса.</span><span class="sxs-lookup"><span data-stu-id="deaf8-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="deaf8-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="deaf8-117">Child Elements</span></span>  
 <span data-ttu-id="deaf8-118">Нет</span><span class="sxs-lookup"><span data-stu-id="deaf8-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="deaf8-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="deaf8-119">Parent Elements</span></span>  
  
|<span data-ttu-id="deaf8-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="deaf8-120">Element</span></span>|<span data-ttu-id="deaf8-121">Описание</span><span class="sxs-lookup"><span data-stu-id="deaf8-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="deaf8-122">\<add></span><span class="sxs-lookup"><span data-stu-id="deaf8-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="deaf8-123">Добавляет обработчик маркеров безопасности в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="deaf8-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="deaf8-124">Пример</span><span class="sxs-lookup"><span data-stu-id="deaf8-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
