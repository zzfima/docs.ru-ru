---
title: Перечисление COR_PRF_GC_ROOT_KIND
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_KIND
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_KIND
helpviewer_keywords:
- COR_PRF_GC_ROOT_KIND enumeration [.NET Framework profiling]
ms.assetid: b9fb1c03-417f-41d4-aed4-02cb4ade8def
topic_type:
- apiref
ms.openlocfilehash: 2fe4735b7f218e89577702cde04d8d4f4de2a971
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447353"
---
# <a name="cor_prf_gc_root_kind-enumeration"></a><span data-ttu-id="82bda-102">Перечисление COR_PRF_GC_ROOT_KIND</span><span class="sxs-lookup"><span data-stu-id="82bda-102">COR_PRF_GC_ROOT_KIND Enumeration</span></span>
<span data-ttu-id="82bda-103">Указывает тип корневого элемента сборки мусора, предоставляемый обратным вызовом [ICorProfilerCallback2:: RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="82bda-103">Indicates the kind of garbage collection root that is exposed by the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82bda-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82bda-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_STACK = 1,  
    COR_PRF_GC_ROOT_FINALIZER = 2,  
    COR_PRF_GC_ROOT_HANDLE = 3,  
    COR_PRF_GC_ROOT_OTHER = 0  
} COR_PRF_GC_ROOT_KIND;  
```  
  
## <a name="members"></a><span data-ttu-id="82bda-105">Члены</span><span class="sxs-lookup"><span data-stu-id="82bda-105">Members</span></span>  
  
|<span data-ttu-id="82bda-106">Член</span><span class="sxs-lookup"><span data-stu-id="82bda-106">Member</span></span>|<span data-ttu-id="82bda-107">Описание</span><span class="sxs-lookup"><span data-stu-id="82bda-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_STACK`|<span data-ttu-id="82bda-108">Корень — это переменная в стеке.</span><span class="sxs-lookup"><span data-stu-id="82bda-108">The root is a variable on the stack.</span></span>|  
|`COR_PRF_GC_ROOT_FINALIZER`|<span data-ttu-id="82bda-109">Корень — это запись в очереди метода завершения.</span><span class="sxs-lookup"><span data-stu-id="82bda-109">The root is an entry in the finalizer queue.</span></span>|  
|`COR_PRF_GC_ROOT_HANDLE`|<span data-ttu-id="82bda-110">Корень является обработчиком сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="82bda-110">The root is a garbage collection handle.</span></span>|  
|`COR_PRF_GC_ROOT_OTHER`|<span data-ttu-id="82bda-111">Тип корня не указан.</span><span class="sxs-lookup"><span data-stu-id="82bda-111">The kind of root is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="82bda-112">Требования</span><span class="sxs-lookup"><span data-stu-id="82bda-112">Requirements</span></span>  
 <span data-ttu-id="82bda-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82bda-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82bda-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="82bda-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="82bda-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82bda-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82bda-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82bda-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82bda-117">См. также</span><span class="sxs-lookup"><span data-stu-id="82bda-117">See also</span></span>

- [<span data-ttu-id="82bda-118">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="82bda-118">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
