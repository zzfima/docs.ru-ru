---
title: '&lt;sessionTokenRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 4d5d2348f04ace7596a3a513c5106ea612dc17b7
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48037185"
---
# <a name="ltsessiontokenrequirementgt"></a><span data-ttu-id="22d3b-102">&lt;sessionTokenRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="22d3b-102">&lt;sessionTokenRequirement&gt;</span></span>
<span data-ttu-id="22d3b-103">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> классом или производными классами.</span><span class="sxs-lookup"><span data-stu-id="22d3b-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="22d3b-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="22d3b-104">\<system.identityModel></span></span>  
<span data-ttu-id="22d3b-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="22d3b-105">\<identityConfiguration></span></span>  
<span data-ttu-id="22d3b-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="22d3b-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="22d3b-107">\<add></span><span class="sxs-lookup"><span data-stu-id="22d3b-107">\<add></span></span>  
<span data-ttu-id="22d3b-108">\<sessionTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="22d3b-108">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22d3b-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22d3b-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22d3b-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="22d3b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="22d3b-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="22d3b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22d3b-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="22d3b-112">Attributes</span></span>  
  
|<span data-ttu-id="22d3b-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="22d3b-113">Attribute</span></span>|<span data-ttu-id="22d3b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="22d3b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="22d3b-115">время существования</span><span class="sxs-lookup"><span data-stu-id="22d3b-115">lifetime</span></span>|<span data-ttu-id="22d3b-116">Задает время существования токенов сеансов.</span><span class="sxs-lookup"><span data-stu-id="22d3b-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22d3b-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="22d3b-117">Child Elements</span></span>  
 <span data-ttu-id="22d3b-118">Нет</span><span class="sxs-lookup"><span data-stu-id="22d3b-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22d3b-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="22d3b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="22d3b-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="22d3b-120">Element</span></span>|<span data-ttu-id="22d3b-121">Описание</span><span class="sxs-lookup"><span data-stu-id="22d3b-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22d3b-122">\<add></span><span class="sxs-lookup"><span data-stu-id="22d3b-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="22d3b-123">Добавляет обработчик токенов безопасности в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="22d3b-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="22d3b-124">Пример</span><span class="sxs-lookup"><span data-stu-id="22d3b-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
