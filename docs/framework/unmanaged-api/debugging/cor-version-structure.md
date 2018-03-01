---
title: "Структура COR_VERSION"
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
- COR_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_VERSION
helpviewer_keywords:
- COR_VERSION structure [.NET Framework debugging]
ms.assetid: 5efaee1c-a001-4c73-9525-4160f4c71567
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b527cb9175315af98a9ad4e9be06d459ad6e188e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corversion-structure"></a><span data-ttu-id="41b0c-102">Структура COR_VERSION</span><span class="sxs-lookup"><span data-stu-id="41b0c-102">COR_VERSION Structure</span></span>
<span data-ttu-id="41b0c-103">Содержит стандартный номер версии среды CLR, состоящий из четырех частей.</span><span class="sxs-lookup"><span data-stu-id="41b0c-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41b0c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41b0c-104">Syntax</span></span>  
  
```  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="41b0c-105">Участники</span><span class="sxs-lookup"><span data-stu-id="41b0c-105">Members</span></span>  
  
|<span data-ttu-id="41b0c-106">Член</span><span class="sxs-lookup"><span data-stu-id="41b0c-106">Member</span></span>|<span data-ttu-id="41b0c-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="41b0c-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="41b0c-108">Основной номер версии.</span><span class="sxs-lookup"><span data-stu-id="41b0c-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="41b0c-109">Дополнительный номер версии.</span><span class="sxs-lookup"><span data-stu-id="41b0c-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="41b0c-110">Номер сборки.</span><span class="sxs-lookup"><span data-stu-id="41b0c-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="41b0c-111">Номер вложенного построения.</span><span class="sxs-lookup"><span data-stu-id="41b0c-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41b0c-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="41b0c-112">Remarks</span></span>  
 <span data-ttu-id="41b0c-113">Если номер версии — 1.0.3705.288, 1 — номер основной версии, 0 — дополнительный номер версии, 3705 — номер сборки, а 288 — дополнительный номер сборки.</span><span class="sxs-lookup"><span data-stu-id="41b0c-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41b0c-114">Требования</span><span class="sxs-lookup"><span data-stu-id="41b0c-114">Requirements</span></span>  
 <span data-ttu-id="41b0c-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41b0c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41b0c-116">**Заголовок:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="41b0c-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="41b0c-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41b0c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41b0c-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41b0c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41b0c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="41b0c-119">See Also</span></span>  
 [<span data-ttu-id="41b0c-120">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="41b0c-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="41b0c-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="41b0c-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
