---
title: Перечисление COR_PRF_FINALIZER_FLAGS
ms.date: 03/30/2017
api_name:
- COR_PRF_FINALIZER_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FINALIZER_FLAGS
helpviewer_keywords:
- COR_PRF_FINALIZER_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 297d7721-3911-4f36-9e34-d9da0c33e22a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a66b2b94765c3d59327e500f1e208dc93cd8e231
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781935"
---
# <a name="corprffinalizerflags-enumeration"></a><span data-ttu-id="aa55e-102">Перечисление COR_PRF_FINALIZER_FLAGS</span><span class="sxs-lookup"><span data-stu-id="aa55e-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="aa55e-103">Описывает метод завершения для объекта.</span><span class="sxs-lookup"><span data-stu-id="aa55e-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa55e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa55e-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="aa55e-105">Участники</span><span class="sxs-lookup"><span data-stu-id="aa55e-105">Members</span></span>  
  
|<span data-ttu-id="aa55e-106">Член</span><span class="sxs-lookup"><span data-stu-id="aa55e-106">Member</span></span>|<span data-ttu-id="aa55e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="aa55e-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="aa55e-108">Метод завершения крайне важен.</span><span class="sxs-lookup"><span data-stu-id="aa55e-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa55e-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="aa55e-109">Remarks</span></span>  
 <span data-ttu-id="aa55e-110">`COR_PRF_FINALIZER_FLAGS` Перечисление, используемое [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) метода для описания завершения для объекта.</span><span class="sxs-lookup"><span data-stu-id="aa55e-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa55e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="aa55e-111">Requirements</span></span>  
 <span data-ttu-id="aa55e-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa55e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa55e-113">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aa55e-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aa55e-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa55e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa55e-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa55e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa55e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="aa55e-116">See also</span></span>

- [<span data-ttu-id="aa55e-117">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="aa55e-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
