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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 263c22a07f363c2752afb50779515de043976e93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207712"
---
# <a name="corprfgcrootflags-enumeration"></a><span data-ttu-id="08480-102">Перечисление COR_PRF_GC_ROOT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="08480-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="08480-103">Указывает свойства корня сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="08480-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08480-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08480-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="08480-105">Участники</span><span class="sxs-lookup"><span data-stu-id="08480-105">Members</span></span>  
  
|<span data-ttu-id="08480-106">Член</span><span class="sxs-lookup"><span data-stu-id="08480-106">Member</span></span>|<span data-ttu-id="08480-107">Описание</span><span class="sxs-lookup"><span data-stu-id="08480-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="08480-108">Корневой предотвращает сборку мусора перемещать объект.</span><span class="sxs-lookup"><span data-stu-id="08480-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="08480-109">Корень не предотвращает сбор мусора.</span><span class="sxs-lookup"><span data-stu-id="08480-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="08480-110">Корень ссылается на поле объекта, а не сам объект.</span><span class="sxs-lookup"><span data-stu-id="08480-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="08480-111">Корневой предотвращает сбор мусора, если счетчик ссылок объекта, не определенное значение.</span><span class="sxs-lookup"><span data-stu-id="08480-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08480-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="08480-112">Remarks</span></span>  
 `COR_PRF_GC_ROOT_FLAGS` <span data-ttu-id="08480-113">Это битовая маска, Дополнительные сведения о специальных корней.</span><span class="sxs-lookup"><span data-stu-id="08480-113">is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="08480-114">Однако не все корни являются особыми.</span><span class="sxs-lookup"><span data-stu-id="08480-114">However, not all roots are special.</span></span> <span data-ttu-id="08480-115">Например некоторые корни не являются слабые ссылки, внутренних указателей, закрепленные или подсчетом ссылок.</span><span class="sxs-lookup"><span data-stu-id="08480-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="08480-116">Для таких корней есть флаги для передачи.</span><span class="sxs-lookup"><span data-stu-id="08480-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="08480-117">Таким образом, методы, использующие это перечисление, такие как [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) метода send 0 для битовой маски флагов, указывающее, что все флаги выключены.</span><span class="sxs-lookup"><span data-stu-id="08480-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08480-118">Требования</span><span class="sxs-lookup"><span data-stu-id="08480-118">Requirements</span></span>  
 <span data-ttu-id="08480-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08480-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08480-120">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="08480-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="08480-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08480-121">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="08480-122">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="08480-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="08480-123">См. также</span><span class="sxs-lookup"><span data-stu-id="08480-123">See also</span></span>

- [<span data-ttu-id="08480-124">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="08480-124">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
