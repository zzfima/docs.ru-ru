---
title: "Перечисление CorManifestResourceFlags"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorManifestResourceFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorManifestResourceFlags
helpviewer_keywords:
- CorManifestResourceFlags enumeration [.NET Framework metadata]
ms.assetid: 1b0306b7-622b-4b57-8edc-3c713bb147ae
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7a1ad2aa505ba77f136a28b2cfa9f1fa357c37ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="73192-102">Перечисление CorManifestResourceFlags</span><span class="sxs-lookup"><span data-stu-id="73192-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="73192-103">Задает видимость ресурсов, зашифрованных в манифесте сборки.</span><span class="sxs-lookup"><span data-stu-id="73192-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73192-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73192-104">Syntax</span></span>  
  
```  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="73192-105">Участники</span><span class="sxs-lookup"><span data-stu-id="73192-105">Members</span></span>  
  
|<span data-ttu-id="73192-106">Член</span><span class="sxs-lookup"><span data-stu-id="73192-106">Member</span></span>|<span data-ttu-id="73192-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="73192-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="73192-108">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="73192-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="73192-109">Ресурсы являются открытыми.</span><span class="sxs-lookup"><span data-stu-id="73192-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="73192-110">Ресурсы являются закрытыми.</span><span class="sxs-lookup"><span data-stu-id="73192-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73192-111">Требования</span><span class="sxs-lookup"><span data-stu-id="73192-111">Requirements</span></span>  
 <span data-ttu-id="73192-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73192-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73192-113">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="73192-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="73192-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73192-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73192-115">См. также</span><span class="sxs-lookup"><span data-stu-id="73192-115">See Also</span></span>  
 [<span data-ttu-id="73192-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="73192-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
