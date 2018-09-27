---
title: '&lt;ClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 805377565b6e835fd9ffba915a003bc56529a3b6
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2018
ms.locfileid: "47234967"
---
# <a name="ltclaimtypegt"></a><span data-ttu-id="70d7a-102">&lt;ClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="70d7a-102">&lt;claimType&gt;</span></span>
<span data-ttu-id="70d7a-103">Указывает одно утверждение обязательными или необязательными для входящих маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="70d7a-103">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="70d7a-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="70d7a-104">\<system.identityModel></span></span>  
<span data-ttu-id="70d7a-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="70d7a-105">\<identityConfiguration></span></span>  
<span data-ttu-id="70d7a-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="70d7a-106">\<claimTypeRequired></span></span>  
<span data-ttu-id="70d7a-107">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="70d7a-107">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70d7a-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70d7a-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70d7a-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="70d7a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="70d7a-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="70d7a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70d7a-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="70d7a-111">Attributes</span></span>  
  
|<span data-ttu-id="70d7a-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="70d7a-112">Attribute</span></span>|<span data-ttu-id="70d7a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="70d7a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="70d7a-114">type</span><span class="sxs-lookup"><span data-stu-id="70d7a-114">type</span></span>|<span data-ttu-id="70d7a-115">Тип утверждения.</span><span class="sxs-lookup"><span data-stu-id="70d7a-115">The claim type.</span></span> <span data-ttu-id="70d7a-116">Обычно URI.</span><span class="sxs-lookup"><span data-stu-id="70d7a-116">Typically a URI.</span></span> <span data-ttu-id="70d7a-117">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="70d7a-117">Required.</span></span>|  
|<span data-ttu-id="70d7a-118">необязательные</span><span class="sxs-lookup"><span data-stu-id="70d7a-118">optional</span></span>|<span data-ttu-id="70d7a-119">Логическое значение, указывающее, является ли тип утверждения необязательным.</span><span class="sxs-lookup"><span data-stu-id="70d7a-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="70d7a-120">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="70d7a-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70d7a-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="70d7a-121">Child Elements</span></span>  
 <span data-ttu-id="70d7a-122">Нет</span><span class="sxs-lookup"><span data-stu-id="70d7a-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="70d7a-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="70d7a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="70d7a-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="70d7a-124">Element</span></span>|<span data-ttu-id="70d7a-125">Описание</span><span class="sxs-lookup"><span data-stu-id="70d7a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70d7a-126">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="70d7a-126">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="70d7a-127">Указывает набор утверждений, необходимых для входящих маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="70d7a-127">Specifies the set of required claims for incoming security tokens.</span></span>|
