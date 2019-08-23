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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 138ac80a9abb64d4c004e83e53ed1eea2b124ff2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69909897"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="d4ebd-102">Интерфейс ICorDebugManagedCallback3</span><span class="sxs-lookup"><span data-stu-id="d4ebd-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="d4ebd-103">Предоставляет метод обратного вызова, указывающий, что создано включенное пользовательское уведомление отладчика.</span><span class="sxs-lookup"><span data-stu-id="d4ebd-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d4ebd-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d4ebd-104">Methods</span></span>  
  
|<span data-ttu-id="d4ebd-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d4ebd-105">Method</span></span>|<span data-ttu-id="d4ebd-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d4ebd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d4ebd-107">Метод CustomNotification</span><span class="sxs-lookup"><span data-stu-id="d4ebd-107">CustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="d4ebd-108">Указывает, что создано включенное пользовательское уведомление отладчика.</span><span class="sxs-lookup"><span data-stu-id="d4ebd-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4ebd-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="d4ebd-109">Remarks</span></span>  
 <span data-ttu-id="d4ebd-110">Этот интерфейс является логическим расширением интерфейсов [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) и [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d4ebd-110">This interface is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d4ebd-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="d4ebd-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4ebd-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d4ebd-112">Requirements</span></span>  
 <span data-ttu-id="d4ebd-113">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4ebd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4ebd-114">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="d4ebd-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4ebd-115">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="d4ebd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4ebd-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4ebd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4ebd-117">См. также</span><span class="sxs-lookup"><span data-stu-id="d4ebd-117">See also</span></span>

- [<span data-ttu-id="d4ebd-118">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="d4ebd-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
- [<span data-ttu-id="d4ebd-119">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="d4ebd-119">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="d4ebd-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d4ebd-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d4ebd-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="d4ebd-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
