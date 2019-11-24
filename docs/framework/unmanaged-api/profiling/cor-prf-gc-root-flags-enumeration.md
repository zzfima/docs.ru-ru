---
title: Перечисление COR_PRF_GC_ROOT_FLAGS
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords:
- COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type:
- apiref
ms.openlocfilehash: 174486a88192bd5ff11074930d5ad3375603f8a5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449467"
---
# <a name="cor_prf_gc_root_flags-enumeration"></a><span data-ttu-id="724a8-102">Перечисление COR_PRF_GC_ROOT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="724a8-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="724a8-103">Indicates a property of a garbage collection root.</span><span class="sxs-lookup"><span data-stu-id="724a8-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="724a8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="724a8-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="724a8-105">Члены</span><span class="sxs-lookup"><span data-stu-id="724a8-105">Members</span></span>  
  
|<span data-ttu-id="724a8-106">Член</span><span class="sxs-lookup"><span data-stu-id="724a8-106">Member</span></span>|<span data-ttu-id="724a8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="724a8-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="724a8-108">The root prevents a garbage collection from moving the object.</span><span class="sxs-lookup"><span data-stu-id="724a8-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="724a8-109">The root does not prevent garbage collection.</span><span class="sxs-lookup"><span data-stu-id="724a8-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="724a8-110">The root refers to a field of the object rather than the object itself.</span><span class="sxs-lookup"><span data-stu-id="724a8-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="724a8-111">The root prevents garbage collection if the reference count of the object is a certain value.</span><span class="sxs-lookup"><span data-stu-id="724a8-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="724a8-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="724a8-112">Remarks</span></span>  
 <span data-ttu-id="724a8-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span><span class="sxs-lookup"><span data-stu-id="724a8-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="724a8-114">However, not all roots are special.</span><span class="sxs-lookup"><span data-stu-id="724a8-114">However, not all roots are special.</span></span> <span data-ttu-id="724a8-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span><span class="sxs-lookup"><span data-stu-id="724a8-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="724a8-116">For such roots, there are no flags to convey.</span><span class="sxs-lookup"><span data-stu-id="724a8-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="724a8-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span><span class="sxs-lookup"><span data-stu-id="724a8-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="724a8-118">Требования</span><span class="sxs-lookup"><span data-stu-id="724a8-118">Requirements</span></span>  
 <span data-ttu-id="724a8-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="724a8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="724a8-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="724a8-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="724a8-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="724a8-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="724a8-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="724a8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="724a8-123">См. также</span><span class="sxs-lookup"><span data-stu-id="724a8-123">See also</span></span>

- [<span data-ttu-id="724a8-124">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="724a8-124">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
