---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: a46e9129bd27319abb4d7519444568af622170fc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252068"
---
# <a name="claimtype"></a><span data-ttu-id="c8cba-101">\<> с</span><span class="sxs-lookup"><span data-stu-id="c8cba-101">\<claimType></span></span>
<span data-ttu-id="c8cba-102">Указывает одно необязательное или обязательное утверждение для входящих токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="c8cba-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
<span data-ttu-id="c8cba-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c8cba-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c8cba-104">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="c8cba-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="c8cba-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="c8cba-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="c8cba-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Клаимтиперекуиред >** ](claimtyperequired.md)</span><span class="sxs-lookup"><span data-stu-id="c8cba-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequired>**](claimtyperequired.md)</span></span>\  
<span data-ttu-id="c8cba-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> с**</span><span class="sxs-lookup"><span data-stu-id="c8cba-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8cba-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8cba-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8cba-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c8cba-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c8cba-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c8cba-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8cba-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c8cba-111">Attributes</span></span>  
  
|<span data-ttu-id="c8cba-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c8cba-112">Attribute</span></span>|<span data-ttu-id="c8cba-113">Описание</span><span class="sxs-lookup"><span data-stu-id="c8cba-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c8cba-114">type</span><span class="sxs-lookup"><span data-stu-id="c8cba-114">type</span></span>|<span data-ttu-id="c8cba-115">Тип утверждения.</span><span class="sxs-lookup"><span data-stu-id="c8cba-115">The claim type.</span></span> <span data-ttu-id="c8cba-116">Обычно это URI.</span><span class="sxs-lookup"><span data-stu-id="c8cba-116">Typically a URI.</span></span> <span data-ttu-id="c8cba-117">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="c8cba-117">Required.</span></span>|  
|<span data-ttu-id="c8cba-118">необязательные</span><span class="sxs-lookup"><span data-stu-id="c8cba-118">optional</span></span>|<span data-ttu-id="c8cba-119">Логическое значение, указывающее, является ли тип утверждения необязательным.</span><span class="sxs-lookup"><span data-stu-id="c8cba-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="c8cba-120">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="c8cba-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8cba-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c8cba-121">Child Elements</span></span>  
 <span data-ttu-id="c8cba-122">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="c8cba-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c8cba-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c8cba-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c8cba-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="c8cba-124">Element</span></span>|<span data-ttu-id="c8cba-125">Описание</span><span class="sxs-lookup"><span data-stu-id="c8cba-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8cba-126">\<Клаимтиперекуиред ></span><span class="sxs-lookup"><span data-stu-id="c8cba-126">\<claimTypeRequired></span></span>](claimtyperequired.md)|<span data-ttu-id="c8cba-127">Указывает набор обязательных утверждений для входящих маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="c8cba-127">Specifies the set of required claims for incoming security tokens.</span></span>|
