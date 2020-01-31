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
ms.openlocfilehash: 0210aca5698cd9c86979c13afd1e622b50d194df
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867192"
---
# <a name="cor_prf_gc_root_flags-enumeration"></a><span data-ttu-id="f29eb-102">Перечисление COR_PRF_GC_ROOT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="f29eb-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="f29eb-103">Указывает свойство корня сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f29eb-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f29eb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f29eb-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="f29eb-105">Участники</span><span class="sxs-lookup"><span data-stu-id="f29eb-105">Members</span></span>  
  
|<span data-ttu-id="f29eb-106">Член</span><span class="sxs-lookup"><span data-stu-id="f29eb-106">Member</span></span>|<span data-ttu-id="f29eb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f29eb-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="f29eb-108">Корень предотвращает перемещение объекта в сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="f29eb-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="f29eb-109">Корень не препятствует сбору мусора.</span><span class="sxs-lookup"><span data-stu-id="f29eb-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="f29eb-110">Корень ссылается на поле объекта, а не на сам объект.</span><span class="sxs-lookup"><span data-stu-id="f29eb-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="f29eb-111">Корень предотвращает сборку мусора, если значение счетчика ссылок объекта является определенным значением.</span><span class="sxs-lookup"><span data-stu-id="f29eb-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f29eb-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="f29eb-112">Remarks</span></span>  
 <span data-ttu-id="f29eb-113">`COR_PRF_GC_ROOT_FLAGS` представляет собой битовую маску, которая предоставляет дополнительные сведения о специальных корневых элементах.</span><span class="sxs-lookup"><span data-stu-id="f29eb-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="f29eb-114">Однако не все корни являются специальными.</span><span class="sxs-lookup"><span data-stu-id="f29eb-114">However, not all roots are special.</span></span> <span data-ttu-id="f29eb-115">Например, некоторые корни не являются слабыми ссылками, внутренними указателями, закрепленными или подсчитаны ссылки.</span><span class="sxs-lookup"><span data-stu-id="f29eb-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="f29eb-116">Для таких корней нет флагов для передачи.</span><span class="sxs-lookup"><span data-stu-id="f29eb-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="f29eb-117">Таким образом, методы, использующие это перечисление, например метод [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) , отправляют 0 для битовой маски флагов, что означает, что все флаги отключены.</span><span class="sxs-lookup"><span data-stu-id="f29eb-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f29eb-118">Требования</span><span class="sxs-lookup"><span data-stu-id="f29eb-118">Requirements</span></span>  
 <span data-ttu-id="f29eb-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f29eb-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f29eb-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f29eb-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f29eb-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f29eb-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f29eb-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f29eb-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f29eb-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="f29eb-123">See also</span></span>

- [<span data-ttu-id="f29eb-124">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="f29eb-124">Profiling Enumerations</span></span>](profiling-enumerations.md)
