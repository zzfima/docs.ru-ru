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
ms.openlocfilehash: b97f29b94ed4fad6892697ca1c7ed4a20c99c03e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793271"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="91ecf-102">Интерфейс ICorDebugManagedCallback3</span><span class="sxs-lookup"><span data-stu-id="91ecf-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="91ecf-103">Предоставляет метод обратного вызова, указывающий, что создано включенное пользовательское уведомление отладчика.</span><span class="sxs-lookup"><span data-stu-id="91ecf-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="91ecf-104">Методы</span><span class="sxs-lookup"><span data-stu-id="91ecf-104">Methods</span></span>  
  
|<span data-ttu-id="91ecf-105">Метод</span><span class="sxs-lookup"><span data-stu-id="91ecf-105">Method</span></span>|<span data-ttu-id="91ecf-106">Описание</span><span class="sxs-lookup"><span data-stu-id="91ecf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="91ecf-107">Метод CustomNotification</span><span class="sxs-lookup"><span data-stu-id="91ecf-107">CustomNotification Method</span></span>](icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="91ecf-108">Указывает, что создано включенное пользовательское уведомление отладчика.</span><span class="sxs-lookup"><span data-stu-id="91ecf-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91ecf-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="91ecf-109">Remarks</span></span>  
 <span data-ttu-id="91ecf-110">Этот интерфейс является логическим расширением интерфейсов [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) и [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="91ecf-110">This interface is a logical extension of the [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="91ecf-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="91ecf-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91ecf-112">Требования</span><span class="sxs-lookup"><span data-stu-id="91ecf-112">Requirements</span></span>  
 <span data-ttu-id="91ecf-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91ecf-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91ecf-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91ecf-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91ecf-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91ecf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91ecf-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91ecf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91ecf-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="91ecf-117">See also</span></span>

- [<span data-ttu-id="91ecf-118">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="91ecf-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
- [<span data-ttu-id="91ecf-119">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="91ecf-119">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="91ecf-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="91ecf-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="91ecf-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="91ecf-121">Debugging</span></span>](index.md)
