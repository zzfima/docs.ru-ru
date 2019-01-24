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
ms.openlocfilehash: 7800567f51196154f49c93dbbbe819f77cefdfe8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499042"
---
# <a name="corprffinalizerflags-enumeration"></a><span data-ttu-id="48175-102">Перечисление COR_PRF_FINALIZER_FLAGS</span><span class="sxs-lookup"><span data-stu-id="48175-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="48175-103">Описывает метод завершения для объекта.</span><span class="sxs-lookup"><span data-stu-id="48175-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48175-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48175-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="48175-105">Участники</span><span class="sxs-lookup"><span data-stu-id="48175-105">Members</span></span>  
  
|<span data-ttu-id="48175-106">Член</span><span class="sxs-lookup"><span data-stu-id="48175-106">Member</span></span>|<span data-ttu-id="48175-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="48175-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="48175-108">Метод завершения крайне важен.</span><span class="sxs-lookup"><span data-stu-id="48175-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48175-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="48175-109">Remarks</span></span>  
 <span data-ttu-id="48175-110">`COR_PRF_FINALIZER_FLAGS` Перечисление, используемое [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) метода для описания завершения для объекта.</span><span class="sxs-lookup"><span data-stu-id="48175-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48175-111">Требования</span><span class="sxs-lookup"><span data-stu-id="48175-111">Requirements</span></span>  
 <span data-ttu-id="48175-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48175-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48175-113">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="48175-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="48175-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48175-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48175-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48175-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48175-116">См. также</span><span class="sxs-lookup"><span data-stu-id="48175-116">See also</span></span>
- [<span data-ttu-id="48175-117">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="48175-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
