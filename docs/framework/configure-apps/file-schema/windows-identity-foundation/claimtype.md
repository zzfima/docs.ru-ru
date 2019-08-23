---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 4253aec961b812b6893ee201861d2ab38048032a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942879"
---
# <a name="claimtype"></a><span data-ttu-id="ad411-101">\<> с</span><span class="sxs-lookup"><span data-stu-id="ad411-101">\<claimType></span></span>
<span data-ttu-id="ad411-102">Указывает одно необязательное или обязательное утверждение для входящих токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="ad411-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="ad411-103">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="ad411-103">\<system.identityModel></span></span>  
<span data-ttu-id="ad411-104">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="ad411-104">\<identityConfiguration></span></span>  
<span data-ttu-id="ad411-105">\<Клаимтиперекуиред ></span><span class="sxs-lookup"><span data-stu-id="ad411-105">\<claimTypeRequired></span></span>  
<span data-ttu-id="ad411-106">\<> с</span><span class="sxs-lookup"><span data-stu-id="ad411-106">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad411-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad411-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad411-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ad411-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ad411-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ad411-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad411-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ad411-110">Attributes</span></span>  
  
|<span data-ttu-id="ad411-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ad411-111">Attribute</span></span>|<span data-ttu-id="ad411-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ad411-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ad411-113">type</span><span class="sxs-lookup"><span data-stu-id="ad411-113">type</span></span>|<span data-ttu-id="ad411-114">Тип утверждения.</span><span class="sxs-lookup"><span data-stu-id="ad411-114">The claim type.</span></span> <span data-ttu-id="ad411-115">Обычно это URI.</span><span class="sxs-lookup"><span data-stu-id="ad411-115">Typically a URI.</span></span> <span data-ttu-id="ad411-116">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="ad411-116">Required.</span></span>|  
|<span data-ttu-id="ad411-117">необязательные</span><span class="sxs-lookup"><span data-stu-id="ad411-117">optional</span></span>|<span data-ttu-id="ad411-118">Логическое значение, указывающее, является ли тип утверждения необязательным.</span><span class="sxs-lookup"><span data-stu-id="ad411-118">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="ad411-119">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="ad411-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ad411-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ad411-120">Child Elements</span></span>  
 <span data-ttu-id="ad411-121">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="ad411-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ad411-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ad411-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ad411-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="ad411-123">Element</span></span>|<span data-ttu-id="ad411-124">Описание</span><span class="sxs-lookup"><span data-stu-id="ad411-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad411-125">\<Клаимтиперекуиред ></span><span class="sxs-lookup"><span data-stu-id="ad411-125">\<claimTypeRequired></span></span>](claimtyperequired.md)|<span data-ttu-id="ad411-126">Указывает набор обязательных утверждений для входящих маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="ad411-126">Specifies the set of required claims for incoming security tokens.</span></span>|
