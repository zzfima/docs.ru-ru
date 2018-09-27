---
title: '&lt;claimTypeRequired&gt;'
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: df4494de6b76943849db2bedef8f43ad894b6bd1
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2018
ms.locfileid: "47399415"
---
# <a name="ltclaimtyperequiredgt"></a><span data-ttu-id="0d53d-102">&lt;claimTypeRequired&gt;</span><span class="sxs-lookup"><span data-stu-id="0d53d-102">&lt;claimTypeRequired&gt;</span></span>
<span data-ttu-id="0d53d-103">Указывает набор утверждений, необходимых для входящих маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="0d53d-103">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="0d53d-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="0d53d-104">\<system.identityModel></span></span>  
<span data-ttu-id="0d53d-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="0d53d-105">\<identityConfiguration></span></span>  
<span data-ttu-id="0d53d-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="0d53d-106">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d53d-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d53d-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d53d-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0d53d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0d53d-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0d53d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d53d-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0d53d-110">Attributes</span></span>  
 <span data-ttu-id="0d53d-111">Нет</span><span class="sxs-lookup"><span data-stu-id="0d53d-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0d53d-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0d53d-112">Child Elements</span></span>  
  
|<span data-ttu-id="0d53d-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="0d53d-113">Element</span></span>|<span data-ttu-id="0d53d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="0d53d-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d53d-115">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="0d53d-115">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="0d53d-116">Указывает одно утверждение обязательными или необязательными для входящих маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="0d53d-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0d53d-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0d53d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0d53d-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="0d53d-118">Element</span></span>|<span data-ttu-id="0d53d-119">Описание</span><span class="sxs-lookup"><span data-stu-id="0d53d-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d53d-120">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="0d53d-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="0d53d-121">Указывает параметры уровня службы идентификации.</span><span class="sxs-lookup"><span data-stu-id="0d53d-121">Specifies service-level identity settings.</span></span>|
