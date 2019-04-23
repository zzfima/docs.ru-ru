---
title: Интерфейс ICorDebugExceptionObjectCallStackEnum
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 39dffa18-c71b-48c4-b11d-e814631ab1e9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7ed6c04a46a767ed122e54df0695429cf923b8a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59126208"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="0d699-102">Интерфейс ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="0d699-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>
<span data-ttu-id="0d699-103">Предоставляет перечислитель для сведений стека вызовов, встроенных в объект исключения.</span><span class="sxs-lookup"><span data-stu-id="0d699-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="0d699-104">Этот интерфейс является подклассом ICorDebugEnum-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="0d699-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0d699-105">Методы</span><span class="sxs-lookup"><span data-stu-id="0d699-105">Methods</span></span>  
  
|<span data-ttu-id="0d699-106">Метод</span><span class="sxs-lookup"><span data-stu-id="0d699-106">Method</span></span>|<span data-ttu-id="0d699-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0d699-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d699-108">ICorDebugExceptionObjectCallStackEnum::Next</span><span class="sxs-lookup"><span data-stu-id="0d699-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="0d699-109">Возвращает заданное число [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) объектов, содержащих сведения о стеке вызовов объект исключения.</span><span class="sxs-lookup"><span data-stu-id="0d699-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d699-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="0d699-110">Remarks</span></span>  
 <span data-ttu-id="0d699-111">`ICorDebugExceptionObjectCallStackEnum` Интерфейс реализует интерфейс ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="0d699-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="0d699-112">`ICorDebugExceptionObjectCallStackEnum` Экземпляр заполняется [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) объектов путем вызова [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="0d699-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="0d699-113">Элементы стека вызова в коллекции можно перечислить, вызвав [ICorDebugExceptionObjectCallStackEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md) метод</span><span class="sxs-lookup"><span data-stu-id="0d699-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d699-114">Требования</span><span class="sxs-lookup"><span data-stu-id="0d699-114">Requirements</span></span>  
 <span data-ttu-id="0d699-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d699-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d699-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d699-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d699-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d699-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d699-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d699-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d699-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0d699-119">See also</span></span>

- [<span data-ttu-id="0d699-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0d699-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="0d699-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="0d699-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
