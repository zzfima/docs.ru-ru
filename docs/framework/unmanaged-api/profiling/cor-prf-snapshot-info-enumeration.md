---
title: "Перечисление COR_PRF_SNAPSHOT_INFO"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_SNAPSHOT_INFO
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_SNAPSHOT_INFO
helpviewer_keywords: COR_PRF_SNAPSHOT_INFO enumeration [.NET Framework profiling]
ms.assetid: a5906b2a-ad4a-4cc6-a421-2d7d8adf7468
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a9c854360881426f2fc7fc9e401da1dc93b9bd84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="corprfsnapshotinfo-enumeration"></a><span data-ttu-id="1de15-102">Перечисление COR_PRF_SNAPSHOT_INFO</span><span class="sxs-lookup"><span data-stu-id="1de15-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>
<span data-ttu-id="1de15-103">Указывает, какой объем данных для обратной передачи со снимком стека в каждом вызове функции профилировщика [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="1de15-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1de15-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1de15-104">Syntax</span></span>  
  
```  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="1de15-105">Члены</span><span class="sxs-lookup"><span data-stu-id="1de15-105">Members</span></span>  
  
|<span data-ttu-id="1de15-106">Члены</span><span class="sxs-lookup"><span data-stu-id="1de15-106">Members</span></span>|<span data-ttu-id="1de15-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1de15-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="1de15-108">Указывает, что значения должны передаваться для всех `StackSnapshotCallback` параметров, за исключением `context` параметра.</span><span class="sxs-lookup"><span data-stu-id="1de15-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="1de15-109">Указывает, что значения должны передаваться для всех `StackSnapshotCallback` параметров, включая `context` параметра.</span><span class="sxs-lookup"><span data-stu-id="1de15-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="1de15-110">Указывает, что будет использоваться простой и альтернативный алгоритм прохода стека.</span><span class="sxs-lookup"><span data-stu-id="1de15-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1de15-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="1de15-111">Remarks</span></span>  
 <span data-ttu-id="1de15-112">Значения, предоставленные `COR_PRF_SNAPSHOT_INFO` перечисления передаются как параметры для [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="1de15-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1de15-113">Требования</span><span class="sxs-lookup"><span data-stu-id="1de15-113">Requirements</span></span>  
 <span data-ttu-id="1de15-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1de15-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1de15-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1de15-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1de15-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1de15-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1de15-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1de15-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1de15-118">См. также</span><span class="sxs-lookup"><span data-stu-id="1de15-118">See Also</span></span>  
 [<span data-ttu-id="1de15-119">Метод DoStackSnapshot</span><span class="sxs-lookup"><span data-stu-id="1de15-119">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
 [<span data-ttu-id="1de15-120">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="1de15-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
