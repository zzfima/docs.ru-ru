---
title: Перечисление CorManifestResourceFlags
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 204f04b1ed1ea293639e0b9826f7e0ce6f384763
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198547"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="9fe23-102">Перечисление CorManifestResourceFlags</span><span class="sxs-lookup"><span data-stu-id="9fe23-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="9fe23-103">Указывает видимость ресурсов, зашифрованных в манифесте сборки.</span><span class="sxs-lookup"><span data-stu-id="9fe23-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fe23-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9fe23-104">Syntax</span></span>  
  
```  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="9fe23-105">Участники</span><span class="sxs-lookup"><span data-stu-id="9fe23-105">Members</span></span>  
  
|<span data-ttu-id="9fe23-106">Член</span><span class="sxs-lookup"><span data-stu-id="9fe23-106">Member</span></span>|<span data-ttu-id="9fe23-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9fe23-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="9fe23-108">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="9fe23-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="9fe23-109">Ресурсы являются открытыми.</span><span class="sxs-lookup"><span data-stu-id="9fe23-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="9fe23-110">Ресурсы являются закрытыми.</span><span class="sxs-lookup"><span data-stu-id="9fe23-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9fe23-111">Требования</span><span class="sxs-lookup"><span data-stu-id="9fe23-111">Requirements</span></span>  
 <span data-ttu-id="9fe23-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fe23-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fe23-113">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="9fe23-113">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="9fe23-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9fe23-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9fe23-115">См. также</span><span class="sxs-lookup"><span data-stu-id="9fe23-115">See also</span></span>

- [<span data-ttu-id="9fe23-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="9fe23-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
