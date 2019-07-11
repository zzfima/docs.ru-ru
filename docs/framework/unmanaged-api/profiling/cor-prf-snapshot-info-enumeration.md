---
title: Перечисление COR_PRF_SNAPSHOT_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_SNAPSHOT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SNAPSHOT_INFO
helpviewer_keywords:
- COR_PRF_SNAPSHOT_INFO enumeration [.NET Framework profiling]
ms.assetid: a5906b2a-ad4a-4cc6-a421-2d7d8adf7468
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9a7d55b5a4867dcdc4e816bd3eac2cf29c68564
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751980"
---
# <a name="corprfsnapshotinfo-enumeration"></a><span data-ttu-id="21e44-102">Перечисление COR_PRF_SNAPSHOT_INFO</span><span class="sxs-lookup"><span data-stu-id="21e44-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>
<span data-ttu-id="21e44-103">Указывает, какой объем данных для обратной передачи со снимком стека в каждом вызове профилировщика [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="21e44-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21e44-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21e44-104">Syntax</span></span>  
  
```cpp  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="21e44-105">Участники</span><span class="sxs-lookup"><span data-stu-id="21e44-105">Members</span></span>  
  
|<span data-ttu-id="21e44-106">Участники</span><span class="sxs-lookup"><span data-stu-id="21e44-106">Members</span></span>|<span data-ttu-id="21e44-107">Описание</span><span class="sxs-lookup"><span data-stu-id="21e44-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="21e44-108">Указывает, что значения должны передаваться для всех `StackSnapshotCallback` параметры, за исключением `context` параметра.</span><span class="sxs-lookup"><span data-stu-id="21e44-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="21e44-109">Указывает, что значения должны передаваться для всех `StackSnapshotCallback` параметров, включая `context` параметра.</span><span class="sxs-lookup"><span data-stu-id="21e44-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="21e44-110">Указывает, что будет использоваться простой и альтернативный алгоритм анализа стека.</span><span class="sxs-lookup"><span data-stu-id="21e44-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21e44-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="21e44-111">Remarks</span></span>  
 <span data-ttu-id="21e44-112">Значения, предоставленные `COR_PRF_SNAPSHOT_INFO` перечисления передаются как параметры для [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="21e44-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21e44-113">Требования</span><span class="sxs-lookup"><span data-stu-id="21e44-113">Requirements</span></span>  
 <span data-ttu-id="21e44-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21e44-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21e44-115">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="21e44-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="21e44-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21e44-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21e44-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21e44-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21e44-118">См. также</span><span class="sxs-lookup"><span data-stu-id="21e44-118">See also</span></span>

- [<span data-ttu-id="21e44-119">Метод DoStackSnapshot</span><span class="sxs-lookup"><span data-stu-id="21e44-119">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="21e44-120">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="21e44-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
