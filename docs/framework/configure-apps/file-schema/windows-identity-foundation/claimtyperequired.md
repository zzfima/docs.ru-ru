---
title: '&lt;claimTypeRequired&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 491277e39b29d7c3e0a0d69ec8745b2c6718a91e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltclaimtyperequiredgt"></a><span data-ttu-id="769a4-102">&lt;claimTypeRequired&gt;</span><span class="sxs-lookup"><span data-stu-id="769a4-102">&lt;claimTypeRequired&gt;</span></span>
<span data-ttu-id="769a4-103">Указывает набор утверждений, необходимых для входящих токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="769a4-103">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="769a4-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="769a4-104">\<system.identityModel></span></span>  
<span data-ttu-id="769a4-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="769a4-105">\<identityConfiguration></span></span>  
<span data-ttu-id="769a4-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="769a4-106">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="769a4-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="769a4-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="769a4-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="769a4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="769a4-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="769a4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="769a4-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="769a4-110">Attributes</span></span>  
 <span data-ttu-id="769a4-111">Нет</span><span class="sxs-lookup"><span data-stu-id="769a4-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="769a4-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="769a4-112">Child Elements</span></span>  
  
|<span data-ttu-id="769a4-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="769a4-113">Element</span></span>|<span data-ttu-id="769a4-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="769a4-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="769a4-115">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="769a4-115">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="769a4-116">Указывает один обязательный или необязательный утверждений входящие маркеры безопасности.</span><span class="sxs-lookup"><span data-stu-id="769a4-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="769a4-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="769a4-117">Parent Elements</span></span>  
  
|<span data-ttu-id="769a4-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="769a4-118">Element</span></span>|<span data-ttu-id="769a4-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="769a4-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="769a4-120">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="769a4-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="769a4-121">Указывает параметры уровня службы удостоверений.</span><span class="sxs-lookup"><span data-stu-id="769a4-121">Specifies service-level identity settings.</span></span>|
