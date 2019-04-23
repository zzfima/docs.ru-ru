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
ms.openlocfilehash: d5037f335e8d66c341d70d91d955a1ac7571b823
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59123764"
---
# <a name="corprffinalizerflags-enumeration"></a><span data-ttu-id="8883f-102">Перечисление COR_PRF_FINALIZER_FLAGS</span><span class="sxs-lookup"><span data-stu-id="8883f-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="8883f-103">Описывает метод завершения для объекта.</span><span class="sxs-lookup"><span data-stu-id="8883f-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8883f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8883f-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="8883f-105">Участники</span><span class="sxs-lookup"><span data-stu-id="8883f-105">Members</span></span>  
  
|<span data-ttu-id="8883f-106">Член</span><span class="sxs-lookup"><span data-stu-id="8883f-106">Member</span></span>|<span data-ttu-id="8883f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8883f-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="8883f-108">Метод завершения крайне важен.</span><span class="sxs-lookup"><span data-stu-id="8883f-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8883f-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="8883f-109">Remarks</span></span>  
 <span data-ttu-id="8883f-110">`COR_PRF_FINALIZER_FLAGS` Перечисление, используемое [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) метода для описания завершения для объекта.</span><span class="sxs-lookup"><span data-stu-id="8883f-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8883f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="8883f-111">Requirements</span></span>  
 <span data-ttu-id="8883f-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8883f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8883f-113">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8883f-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8883f-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8883f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8883f-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8883f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8883f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8883f-116">See also</span></span>

- [<span data-ttu-id="8883f-117">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="8883f-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
