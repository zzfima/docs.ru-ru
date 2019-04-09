---
title: Интерфейс ICorDebugThread3
ms.date: 03/30/2017
api_name:
- ICorDebugThread3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3
helpviewer_keywords:
- ICorDebugThread3 interface [.NET Framework debugging]
ms.assetid: eb2860ef-06cb-4968-a6c3-6d048ecda2a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d34a3395605505ca0ebda072e33d8083d51123a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59185878"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="bb7ec-102">Интерфейс ICorDebugThread3</span><span class="sxs-lookup"><span data-stu-id="bb7ec-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="bb7ec-103">Предоставляет точку входа для [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) и соответствующие интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="bb7ec-103">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bb7ec-104">Методы</span><span class="sxs-lookup"><span data-stu-id="bb7ec-104">Methods</span></span>  
  
|<span data-ttu-id="bb7ec-105">Метод</span><span class="sxs-lookup"><span data-stu-id="bb7ec-105">Method</span></span>|<span data-ttu-id="bb7ec-106">Описание</span><span class="sxs-lookup"><span data-stu-id="bb7ec-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bb7ec-107">Метод CreateStackWalk</span><span class="sxs-lookup"><span data-stu-id="bb7ec-107">CreateStackWalk Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="bb7ec-108">Создает [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) объект потока, стек которого вы хотите развернуть.</span><span class="sxs-lookup"><span data-stu-id="bb7ec-108">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="bb7ec-109">Метод GetActiveInternalFrames</span><span class="sxs-lookup"><span data-stu-id="bb7ec-109">GetActiveInternalFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="bb7ec-110">Возвращает массив из внутренних кадрах ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) объектов) в стеке.</span><span class="sxs-lookup"><span data-stu-id="bb7ec-110">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb7ec-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="bb7ec-111">Remarks</span></span>  
 `ICorDebugThread3` <span data-ttu-id="bb7ec-112">является логическим расширением интерфейса ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="bb7ec-112">is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb7ec-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="bb7ec-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb7ec-114">Требования</span><span class="sxs-lookup"><span data-stu-id="bb7ec-114">Requirements</span></span>  
 <span data-ttu-id="bb7ec-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb7ec-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb7ec-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb7ec-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb7ec-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb7ec-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="bb7ec-118">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bb7ec-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bb7ec-119">См. также</span><span class="sxs-lookup"><span data-stu-id="bb7ec-119">See also</span></span>

- [<span data-ttu-id="bb7ec-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="bb7ec-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="bb7ec-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="bb7ec-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
