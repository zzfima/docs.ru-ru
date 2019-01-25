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
ms.openlocfilehash: 33c233f2699c89e5acfb0fda13f74589f1c5dd4b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741604"
---
# <a name="corprfsnapshotinfo-enumeration"></a><span data-ttu-id="5602a-102">Перечисление COR_PRF_SNAPSHOT_INFO</span><span class="sxs-lookup"><span data-stu-id="5602a-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>
<span data-ttu-id="5602a-103">Указывает, какой объем данных для обратной передачи со снимком стека в каждом вызове профилировщика [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="5602a-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5602a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5602a-104">Syntax</span></span>  
  
```  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="5602a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="5602a-105">Members</span></span>  
  
|<span data-ttu-id="5602a-106">Участники</span><span class="sxs-lookup"><span data-stu-id="5602a-106">Members</span></span>|<span data-ttu-id="5602a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5602a-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="5602a-108">Указывает, что значения должны передаваться для всех `StackSnapshotCallback` параметры, за исключением `context` параметра.</span><span class="sxs-lookup"><span data-stu-id="5602a-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="5602a-109">Указывает, что значения должны передаваться для всех `StackSnapshotCallback` параметров, включая `context` параметра.</span><span class="sxs-lookup"><span data-stu-id="5602a-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="5602a-110">Указывает, что будет использоваться простой и альтернативный алгоритм анализа стека.</span><span class="sxs-lookup"><span data-stu-id="5602a-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5602a-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="5602a-111">Remarks</span></span>  
 <span data-ttu-id="5602a-112">Значения, предоставленные `COR_PRF_SNAPSHOT_INFO` перечисления передаются как параметры для [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="5602a-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5602a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="5602a-113">Requirements</span></span>  
 <span data-ttu-id="5602a-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5602a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5602a-115">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5602a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5602a-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5602a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5602a-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5602a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5602a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5602a-118">See also</span></span>
- [<span data-ttu-id="5602a-119">Метод DoStackSnapshot</span><span class="sxs-lookup"><span data-stu-id="5602a-119">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="5602a-120">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="5602a-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
