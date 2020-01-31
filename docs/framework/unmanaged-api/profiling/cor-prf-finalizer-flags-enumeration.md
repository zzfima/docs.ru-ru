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
ms.openlocfilehash: daca2849908a7798b588ff06f6e117d412db1b33
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867273"
---
# <a name="cor_prf_finalizer_flags-enumeration"></a><span data-ttu-id="bec78-102">Перечисление COR_PRF_FINALIZER_FLAGS</span><span class="sxs-lookup"><span data-stu-id="bec78-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="bec78-103">Описывает метод завершения для объекта.</span><span class="sxs-lookup"><span data-stu-id="bec78-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bec78-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bec78-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="bec78-105">Участники</span><span class="sxs-lookup"><span data-stu-id="bec78-105">Members</span></span>  
  
|<span data-ttu-id="bec78-106">Член</span><span class="sxs-lookup"><span data-stu-id="bec78-106">Member</span></span>|<span data-ttu-id="bec78-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bec78-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="bec78-108">Метод завершения является критическим.</span><span class="sxs-lookup"><span data-stu-id="bec78-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bec78-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="bec78-109">Remarks</span></span>  
 <span data-ttu-id="bec78-110">Перечисление `COR_PRF_FINALIZER_FLAGS` используется методом [ICorProfilerCallback2:: финализеаблеобжекткуеуед](icorprofilercallback2-finalizeableobjectqueued-method.md) для описания метода завершения для объекта.</span><span class="sxs-lookup"><span data-stu-id="bec78-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bec78-111">Требования</span><span class="sxs-lookup"><span data-stu-id="bec78-111">Requirements</span></span>  
 <span data-ttu-id="bec78-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bec78-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bec78-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bec78-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bec78-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bec78-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bec78-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bec78-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bec78-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="bec78-116">See also</span></span>

- [<span data-ttu-id="bec78-117">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="bec78-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
