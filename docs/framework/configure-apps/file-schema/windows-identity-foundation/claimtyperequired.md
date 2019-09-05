---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: 1c40c5e4b4a24a3c1bbd6e096f12b7b044331c88
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252050"
---
# <a name="claimtyperequired"></a><span data-ttu-id="02f61-101">\<Клаимтиперекуиред ></span><span class="sxs-lookup"><span data-stu-id="02f61-101">\<claimTypeRequired></span></span>
<span data-ttu-id="02f61-102">Указывает набор обязательных утверждений для входящих маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="02f61-102">Specifies the set of required claims for incoming security tokens.</span></span>  
  
<span data-ttu-id="02f61-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="02f61-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="02f61-104">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="02f61-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="02f61-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="02f61-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="02f61-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Клаимтиперекуиред >**</span><span class="sxs-lookup"><span data-stu-id="02f61-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimTypeRequired>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02f61-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02f61-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02f61-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="02f61-108">Attributes and Elements</span></span>  
 <span data-ttu-id="02f61-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="02f61-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02f61-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="02f61-110">Attributes</span></span>  
 <span data-ttu-id="02f61-111">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="02f61-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="02f61-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="02f61-112">Child Elements</span></span>  
  
|<span data-ttu-id="02f61-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="02f61-113">Element</span></span>|<span data-ttu-id="02f61-114">Описание</span><span class="sxs-lookup"><span data-stu-id="02f61-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02f61-115">\<> с</span><span class="sxs-lookup"><span data-stu-id="02f61-115">\<claimType></span></span>](claimtype.md)|<span data-ttu-id="02f61-116">Указывает одно необязательное или обязательное утверждение для входящих токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="02f61-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="02f61-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="02f61-117">Parent Elements</span></span>  
  
|<span data-ttu-id="02f61-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="02f61-118">Element</span></span>|<span data-ttu-id="02f61-119">Описание</span><span class="sxs-lookup"><span data-stu-id="02f61-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02f61-120">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="02f61-120">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="02f61-121">Задает параметры удостоверений уровня службы.</span><span class="sxs-lookup"><span data-stu-id="02f61-121">Specifies service-level identity settings.</span></span>|
