---
title: '&lt;sessionTokenRequirement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
caps.latest.revision: "3"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 5a141dd83cb7ef1271906871097eb68da174d22f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltsessiontokenrequirementgt"></a><span data-ttu-id="3eaa2-102">&lt;sessionTokenRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="3eaa2-102">&lt;sessionTokenRequirement&gt;</span></span>
<span data-ttu-id="3eaa2-103">Обеспечивает настройку для <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> класса или производных классов.</span><span class="sxs-lookup"><span data-stu-id="3eaa2-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="3eaa2-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="3eaa2-104">\<system.identityModel></span></span>  
<span data-ttu-id="3eaa2-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3eaa2-105">\<identityConfiguration></span></span>  
<span data-ttu-id="3eaa2-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="3eaa2-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="3eaa2-107">\<add></span><span class="sxs-lookup"><span data-stu-id="3eaa2-107">\<add></span></span>  
<span data-ttu-id="3eaa2-108">\<sessionTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="3eaa2-108">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eaa2-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3eaa2-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3eaa2-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3eaa2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3eaa2-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3eaa2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3eaa2-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3eaa2-112">Attributes</span></span>  
  
|<span data-ttu-id="3eaa2-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3eaa2-113">Attribute</span></span>|<span data-ttu-id="3eaa2-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="3eaa2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3eaa2-115">время существования</span><span class="sxs-lookup"><span data-stu-id="3eaa2-115">lifetime</span></span>|<span data-ttu-id="3eaa2-116">Задает время существования маркеров сеанса.</span><span class="sxs-lookup"><span data-stu-id="3eaa2-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3eaa2-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3eaa2-117">Child Elements</span></span>  
 <span data-ttu-id="3eaa2-118">Нет</span><span class="sxs-lookup"><span data-stu-id="3eaa2-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3eaa2-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3eaa2-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3eaa2-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="3eaa2-120">Element</span></span>|<span data-ttu-id="3eaa2-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="3eaa2-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3eaa2-122">\<add></span><span class="sxs-lookup"><span data-stu-id="3eaa2-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="3eaa2-123">Добавляет обработчик маркеров безопасности в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="3eaa2-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3eaa2-124">Пример</span><span class="sxs-lookup"><span data-stu-id="3eaa2-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
