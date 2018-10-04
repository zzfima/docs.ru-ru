---
title: '&lt;sessionTokenRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 4d5d2348f04ace7596a3a513c5106ea612dc17b7
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48792933"
---
# <a name="ltsessiontokenrequirementgt"></a><span data-ttu-id="8ae8d-102">&lt;sessionTokenRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="8ae8d-102">&lt;sessionTokenRequirement&gt;</span></span>
<span data-ttu-id="8ae8d-103">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> классом или производными классами.</span><span class="sxs-lookup"><span data-stu-id="8ae8d-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="8ae8d-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="8ae8d-104">\<system.identityModel></span></span>  
<span data-ttu-id="8ae8d-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="8ae8d-105">\<identityConfiguration></span></span>  
<span data-ttu-id="8ae8d-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="8ae8d-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="8ae8d-107">\<add></span><span class="sxs-lookup"><span data-stu-id="8ae8d-107">\<add></span></span>  
<span data-ttu-id="8ae8d-108">\<sessionTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="8ae8d-108">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ae8d-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ae8d-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ae8d-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8ae8d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8ae8d-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8ae8d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ae8d-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8ae8d-112">Attributes</span></span>  
  
|<span data-ttu-id="8ae8d-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8ae8d-113">Attribute</span></span>|<span data-ttu-id="8ae8d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="8ae8d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8ae8d-115">время существования</span><span class="sxs-lookup"><span data-stu-id="8ae8d-115">lifetime</span></span>|<span data-ttu-id="8ae8d-116">Задает время существования токенов сеансов.</span><span class="sxs-lookup"><span data-stu-id="8ae8d-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ae8d-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8ae8d-117">Child Elements</span></span>  
 <span data-ttu-id="8ae8d-118">Нет</span><span class="sxs-lookup"><span data-stu-id="8ae8d-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ae8d-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8ae8d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8ae8d-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="8ae8d-120">Element</span></span>|<span data-ttu-id="8ae8d-121">Описание</span><span class="sxs-lookup"><span data-stu-id="8ae8d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ae8d-122">\<add></span><span class="sxs-lookup"><span data-stu-id="8ae8d-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="8ae8d-123">Добавляет обработчик токенов безопасности в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="8ae8d-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8ae8d-124">Пример</span><span class="sxs-lookup"><span data-stu-id="8ae8d-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
