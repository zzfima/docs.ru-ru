---
title: '&lt;claimTypeRequired&gt;'
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6fb600aac46b3ee5cb54fa904d35ac7b7ed90719
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimtyperequiredgt"></a><span data-ttu-id="77339-102">&lt;claimTypeRequired&gt;</span><span class="sxs-lookup"><span data-stu-id="77339-102">&lt;claimTypeRequired&gt;</span></span>
<span data-ttu-id="77339-103">Указывает набор утверждений, необходимых для входящих токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="77339-103">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="77339-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="77339-104">\<system.identityModel></span></span>  
<span data-ttu-id="77339-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="77339-105">\<identityConfiguration></span></span>  
<span data-ttu-id="77339-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="77339-106">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77339-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="77339-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77339-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="77339-108">Attributes and Elements</span></span>  
 <span data-ttu-id="77339-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="77339-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77339-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="77339-110">Attributes</span></span>  
 <span data-ttu-id="77339-111">Нет</span><span class="sxs-lookup"><span data-stu-id="77339-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="77339-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="77339-112">Child Elements</span></span>  
  
|<span data-ttu-id="77339-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="77339-113">Element</span></span>|<span data-ttu-id="77339-114">Описание</span><span class="sxs-lookup"><span data-stu-id="77339-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="77339-115">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="77339-115">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="77339-116">Указывает один обязательный или необязательный утверждений входящие маркеры безопасности.</span><span class="sxs-lookup"><span data-stu-id="77339-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="77339-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="77339-117">Parent Elements</span></span>  
  
|<span data-ttu-id="77339-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="77339-118">Element</span></span>|<span data-ttu-id="77339-119">Описание</span><span class="sxs-lookup"><span data-stu-id="77339-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="77339-120">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="77339-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="77339-121">Указывает параметры уровня службы удостоверений.</span><span class="sxs-lookup"><span data-stu-id="77339-121">Specifies service-level identity settings.</span></span>|
