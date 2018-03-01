---
title: "Перечисление COR_PRF_FINALIZER_FLAGS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ae0941e962b2fc1b08f0defb692038bd5fcf885a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corprffinalizerflags-enumeration"></a><span data-ttu-id="15c11-102">Перечисление COR_PRF_FINALIZER_FLAGS</span><span class="sxs-lookup"><span data-stu-id="15c11-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="15c11-103">Описывает метод завершения для объекта.</span><span class="sxs-lookup"><span data-stu-id="15c11-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15c11-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15c11-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="15c11-105">Участники</span><span class="sxs-lookup"><span data-stu-id="15c11-105">Members</span></span>  
  
|<span data-ttu-id="15c11-106">Член</span><span class="sxs-lookup"><span data-stu-id="15c11-106">Member</span></span>|<span data-ttu-id="15c11-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="15c11-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="15c11-108">Метод завершения очень важен.</span><span class="sxs-lookup"><span data-stu-id="15c11-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15c11-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="15c11-109">Remarks</span></span>  
 <span data-ttu-id="15c11-110">`COR_PRF_FINALIZER_FLAGS` Перечисление используется методом [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) метод для описания завершения для объекта.</span><span class="sxs-lookup"><span data-stu-id="15c11-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15c11-111">Требования</span><span class="sxs-lookup"><span data-stu-id="15c11-111">Requirements</span></span>  
 <span data-ttu-id="15c11-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15c11-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15c11-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="15c11-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="15c11-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15c11-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15c11-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15c11-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15c11-116">См. также</span><span class="sxs-lookup"><span data-stu-id="15c11-116">See Also</span></span>  
 [<span data-ttu-id="15c11-117">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="15c11-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
