---
title: '&lt;claimType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: ae572ff3a8a2335a4259bdce2af5f6922fb0596f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltclaimtypegt"></a><span data-ttu-id="505d5-102">&lt;claimType&gt;</span><span class="sxs-lookup"><span data-stu-id="505d5-102">&lt;claimType&gt;</span></span>
<span data-ttu-id="505d5-103">Указывает один обязательный или необязательный утверждений входящие маркеры безопасности.</span><span class="sxs-lookup"><span data-stu-id="505d5-103">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="505d5-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="505d5-104">\<system.identityModel></span></span>  
<span data-ttu-id="505d5-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="505d5-105">\<identityConfiguration></span></span>  
<span data-ttu-id="505d5-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="505d5-106">\<claimTypeRequired></span></span>  
<span data-ttu-id="505d5-107">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="505d5-107">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="505d5-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="505d5-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="505d5-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="505d5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="505d5-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="505d5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="505d5-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="505d5-111">Attributes</span></span>  
  
|<span data-ttu-id="505d5-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="505d5-112">Attribute</span></span>|<span data-ttu-id="505d5-113">Описание</span><span class="sxs-lookup"><span data-stu-id="505d5-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="505d5-114">type</span><span class="sxs-lookup"><span data-stu-id="505d5-114">type</span></span>|<span data-ttu-id="505d5-115">Тип утверждения.</span><span class="sxs-lookup"><span data-stu-id="505d5-115">The claim type.</span></span> <span data-ttu-id="505d5-116">Обычно URI.</span><span class="sxs-lookup"><span data-stu-id="505d5-116">Typically a URI.</span></span> <span data-ttu-id="505d5-117">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="505d5-117">Required.</span></span>|  
|<span data-ttu-id="505d5-118">необязательные</span><span class="sxs-lookup"><span data-stu-id="505d5-118">optional</span></span>|<span data-ttu-id="505d5-119">Логическое значение, указывающее, является ли тип утверждения является необязательным.</span><span class="sxs-lookup"><span data-stu-id="505d5-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="505d5-120">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="505d5-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="505d5-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="505d5-121">Child Elements</span></span>  
 <span data-ttu-id="505d5-122">Нет</span><span class="sxs-lookup"><span data-stu-id="505d5-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="505d5-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="505d5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="505d5-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="505d5-124">Element</span></span>|<span data-ttu-id="505d5-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="505d5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="505d5-126">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="505d5-126">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="505d5-127">Указывает набор утверждений, необходимых для входящих токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="505d5-127">Specifies the set of required claims for incoming security tokens.</span></span>|
