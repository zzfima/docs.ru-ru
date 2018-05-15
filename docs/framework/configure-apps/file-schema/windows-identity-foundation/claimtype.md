---
title: '&lt;ClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 94f8586a9ca63b8c1f1128cdda4a74ccfe0f5416
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimtypegt"></a><span data-ttu-id="e700f-102">&lt;ClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="e700f-102">&lt;claimType&gt;</span></span>
<span data-ttu-id="e700f-103">Указывает один обязательный или необязательный утверждений входящие маркеры безопасности.</span><span class="sxs-lookup"><span data-stu-id="e700f-103">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="e700f-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="e700f-104">\<system.identityModel></span></span>  
<span data-ttu-id="e700f-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="e700f-105">\<identityConfiguration></span></span>  
<span data-ttu-id="e700f-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="e700f-106">\<claimTypeRequired></span></span>  
<span data-ttu-id="e700f-107">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="e700f-107">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e700f-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e700f-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
      <claimType type=URI optional=xs:boolean >  
      </claimType>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e700f-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e700f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e700f-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e700f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e700f-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e700f-111">Attributes</span></span>  
  
|<span data-ttu-id="e700f-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e700f-112">Attribute</span></span>|<span data-ttu-id="e700f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e700f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e700f-114">type</span><span class="sxs-lookup"><span data-stu-id="e700f-114">type</span></span>|<span data-ttu-id="e700f-115">Тип утверждения.</span><span class="sxs-lookup"><span data-stu-id="e700f-115">The claim type.</span></span> <span data-ttu-id="e700f-116">Обычно URI.</span><span class="sxs-lookup"><span data-stu-id="e700f-116">Typically a URI.</span></span> <span data-ttu-id="e700f-117">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="e700f-117">Required.</span></span>|  
|<span data-ttu-id="e700f-118">необязательные</span><span class="sxs-lookup"><span data-stu-id="e700f-118">optional</span></span>|<span data-ttu-id="e700f-119">Логическое значение, указывающее, является ли тип утверждения является необязательным.</span><span class="sxs-lookup"><span data-stu-id="e700f-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="e700f-120">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="e700f-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e700f-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e700f-121">Child Elements</span></span>  
 <span data-ttu-id="e700f-122">Нет</span><span class="sxs-lookup"><span data-stu-id="e700f-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e700f-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e700f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e700f-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="e700f-124">Element</span></span>|<span data-ttu-id="e700f-125">Описание</span><span class="sxs-lookup"><span data-stu-id="e700f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e700f-126">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="e700f-126">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="e700f-127">Указывает набор утверждений, необходимых для входящих токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="e700f-127">Specifies the set of required claims for incoming security tokens.</span></span>|
