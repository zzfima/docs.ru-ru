---
title: "Перечисление COR_PRF_GC_ROOT_FLAGS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_GC_ROOT_FLAGS
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords: COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5e00f695edb94acbd54d6bd009ccd629aeec1b14
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corprfgcrootflags-enumeration"></a><span data-ttu-id="4ee46-102">Перечисление COR_PRF_GC_ROOT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="4ee46-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="4ee46-103">Указывает свойства корня сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4ee46-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ee46-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ee46-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="4ee46-105">Участники</span><span class="sxs-lookup"><span data-stu-id="4ee46-105">Members</span></span>  
  
|<span data-ttu-id="4ee46-106">Член</span><span class="sxs-lookup"><span data-stu-id="4ee46-106">Member</span></span>|<span data-ttu-id="4ee46-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="4ee46-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="4ee46-108">Корень предотвращает мусора переместить объект.</span><span class="sxs-lookup"><span data-stu-id="4ee46-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="4ee46-109">Корень не предотвращает сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="4ee46-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="4ee46-110">Корень ссылается на поле объекта, а не сам объект.</span><span class="sxs-lookup"><span data-stu-id="4ee46-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="4ee46-111">Корневой предотвращает сбора мусора, если количество ссылок на объект определенного значения.</span><span class="sxs-lookup"><span data-stu-id="4ee46-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ee46-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="4ee46-112">Remarks</span></span>  
 <span data-ttu-id="4ee46-113">`COR_PRF_GC_ROOT_FLAGS`представляет собой битовую маску, предоставляющий дополнительные сведения об особых корнях.</span><span class="sxs-lookup"><span data-stu-id="4ee46-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="4ee46-114">Однако не все корни являются особыми.</span><span class="sxs-lookup"><span data-stu-id="4ee46-114">However, not all roots are special.</span></span> <span data-ttu-id="4ee46-115">Например некоторые корни не слабые ссылки внутренних указателей, закрепленных или подсчетом ссылок.</span><span class="sxs-lookup"><span data-stu-id="4ee46-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="4ee46-116">Для таких корней отсутствуют флаги для передачи.</span><span class="sxs-lookup"><span data-stu-id="4ee46-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="4ee46-117">Таким образом, методы, использующие это перечисление, такие как [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) метода send 0 для битовой маски флагов, указывающее, что все флаги выключены.</span><span class="sxs-lookup"><span data-stu-id="4ee46-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ee46-118">Требования</span><span class="sxs-lookup"><span data-stu-id="4ee46-118">Requirements</span></span>  
 <span data-ttu-id="4ee46-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ee46-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ee46-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4ee46-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4ee46-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ee46-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ee46-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ee46-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ee46-123">См. также</span><span class="sxs-lookup"><span data-stu-id="4ee46-123">See Also</span></span>  
 [<span data-ttu-id="4ee46-124">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="4ee46-124">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
