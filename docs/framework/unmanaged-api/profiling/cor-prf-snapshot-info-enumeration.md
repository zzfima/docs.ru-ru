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
ms.openlocfilehash: 97bf3e69a8ea155d53479ba6f61988e56e3bd396
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867028"
---
# <a name="cor_prf_snapshot_info-enumeration"></a><span data-ttu-id="b4c97-102">Перечисление COR_PRF_SNAPSHOT_INFO</span><span class="sxs-lookup"><span data-stu-id="b4c97-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>
<span data-ttu-id="b4c97-103">Указывает объем данных, которые необходимо передать обратно с помощью моментального снимка стека при каждом вызове функции [стаккснапшоткаллбакк](stacksnapshotcallback-function.md) профилировщика.</span><span class="sxs-lookup"><span data-stu-id="b4c97-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4c97-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4c97-104">Syntax</span></span>  
  
```cpp  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="b4c97-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b4c97-105">Members</span></span>  
  
|<span data-ttu-id="b4c97-106">Участники</span><span class="sxs-lookup"><span data-stu-id="b4c97-106">Members</span></span>|<span data-ttu-id="b4c97-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b4c97-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="b4c97-108">Указывает, что значения должны передаваться для всех `StackSnapshotCallback` параметров, кроме параметра `context`.</span><span class="sxs-lookup"><span data-stu-id="b4c97-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="b4c97-109">Указывает, что значения должны передаваться для всех параметров `StackSnapshotCallback`, включая параметр `context`.</span><span class="sxs-lookup"><span data-stu-id="b4c97-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="b4c97-110">Указывает, что будет использоваться более простой и альтернативный алгоритм анализа стека.</span><span class="sxs-lookup"><span data-stu-id="b4c97-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4c97-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="b4c97-111">Remarks</span></span>  
 <span data-ttu-id="b4c97-112">Значения, предоставляемые перечислением `COR_PRF_SNAPSHOT_INFO`, передаются в качестве параметров в метод [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b4c97-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4c97-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b4c97-113">Requirements</span></span>  
 <span data-ttu-id="b4c97-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4c97-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4c97-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b4c97-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b4c97-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4c97-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4c97-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4c97-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4c97-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="b4c97-118">See also</span></span>

- [<span data-ttu-id="b4c97-119">Метод DoStackSnapshot</span><span class="sxs-lookup"><span data-stu-id="b4c97-119">DoStackSnapshot Method</span></span>](icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="b4c97-120">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="b4c97-120">Profiling Enumerations</span></span>](profiling-enumerations.md)
