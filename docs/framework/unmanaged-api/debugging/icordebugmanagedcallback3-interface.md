---
title: Интерфейс ICorDebugManagedCallback3
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3
helpviewer_keywords:
- ICorDebugManagedCallback3 interface [.NET Framework debugging]
ms.assetid: a95389d3-cf2e-47a4-9805-61426acc6b65
topic_type:
- apiref
ms.openlocfilehash: 8da04b0c620404e0dad8227c7a627f75507389a7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128029"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="50a2e-102">Интерфейс ICorDebugManagedCallback3</span><span class="sxs-lookup"><span data-stu-id="50a2e-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="50a2e-103">Предоставляет метод обратного вызова, указывающий, что создано включенное пользовательское уведомление отладчика.</span><span class="sxs-lookup"><span data-stu-id="50a2e-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50a2e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="50a2e-104">Methods</span></span>  
  
|<span data-ttu-id="50a2e-105">Метод</span><span class="sxs-lookup"><span data-stu-id="50a2e-105">Method</span></span>|<span data-ttu-id="50a2e-106">Описание</span><span class="sxs-lookup"><span data-stu-id="50a2e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50a2e-107">Метод CustomNotification</span><span class="sxs-lookup"><span data-stu-id="50a2e-107">CustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="50a2e-108">Указывает, что создано включенное пользовательское уведомление отладчика.</span><span class="sxs-lookup"><span data-stu-id="50a2e-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50a2e-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="50a2e-109">Remarks</span></span>  
 <span data-ttu-id="50a2e-110">Этот интерфейс является логическим расширением интерфейсов [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) и [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="50a2e-110">This interface is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="50a2e-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="50a2e-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50a2e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="50a2e-112">Requirements</span></span>  
 <span data-ttu-id="50a2e-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50a2e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50a2e-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50a2e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50a2e-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50a2e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50a2e-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50a2e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50a2e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="50a2e-117">See also</span></span>

- [<span data-ttu-id="50a2e-118">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="50a2e-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
- [<span data-ttu-id="50a2e-119">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="50a2e-119">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="50a2e-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="50a2e-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="50a2e-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="50a2e-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
