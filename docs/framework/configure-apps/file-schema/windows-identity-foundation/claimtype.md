---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 6bc185572528d4229ee53f1421eaa5bf27b053e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667227"
---
# <a name="claimtype"></a><span data-ttu-id="06b08-101">\<claimType></span><span class="sxs-lookup"><span data-stu-id="06b08-101">\<claimType></span></span>
<span data-ttu-id="06b08-102">Указывает одно утверждение обязательными или необязательными для входящих маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="06b08-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="06b08-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="06b08-103">\<system.identityModel></span></span>  
<span data-ttu-id="06b08-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="06b08-104">\<identityConfiguration></span></span>  
<span data-ttu-id="06b08-105">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="06b08-105">\<claimTypeRequired></span></span>  
<span data-ttu-id="06b08-106">\<claimType></span><span class="sxs-lookup"><span data-stu-id="06b08-106">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06b08-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06b08-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06b08-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="06b08-108">Attributes and Elements</span></span>  
 <span data-ttu-id="06b08-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="06b08-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06b08-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="06b08-110">Attributes</span></span>  
  
|<span data-ttu-id="06b08-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="06b08-111">Attribute</span></span>|<span data-ttu-id="06b08-112">Описание</span><span class="sxs-lookup"><span data-stu-id="06b08-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="06b08-113">type</span><span class="sxs-lookup"><span data-stu-id="06b08-113">type</span></span>|<span data-ttu-id="06b08-114">Тип утверждения.</span><span class="sxs-lookup"><span data-stu-id="06b08-114">The claim type.</span></span> <span data-ttu-id="06b08-115">Обычно URI.</span><span class="sxs-lookup"><span data-stu-id="06b08-115">Typically a URI.</span></span> <span data-ttu-id="06b08-116">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="06b08-116">Required.</span></span>|  
|<span data-ttu-id="06b08-117">необязательные</span><span class="sxs-lookup"><span data-stu-id="06b08-117">optional</span></span>|<span data-ttu-id="06b08-118">Логическое значение, указывающее, является ли тип утверждения необязательным.</span><span class="sxs-lookup"><span data-stu-id="06b08-118">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="06b08-119">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="06b08-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06b08-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="06b08-120">Child Elements</span></span>  
 <span data-ttu-id="06b08-121">Нет</span><span class="sxs-lookup"><span data-stu-id="06b08-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06b08-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="06b08-122">Parent Elements</span></span>  
  
|<span data-ttu-id="06b08-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="06b08-123">Element</span></span>|<span data-ttu-id="06b08-124">Описание</span><span class="sxs-lookup"><span data-stu-id="06b08-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06b08-125">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="06b08-125">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="06b08-126">Указывает набор утверждений, необходимых для входящих маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="06b08-126">Specifies the set of required claims for incoming security tokens.</span></span>|
