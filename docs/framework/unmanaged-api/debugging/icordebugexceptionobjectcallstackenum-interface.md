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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126208"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="6ea74-102">Интерфейс ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="6ea74-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>
<span data-ttu-id="6ea74-103">Предоставляет перечислитель для сведений стека вызовов, встроенных в объект исключения.</span><span class="sxs-lookup"><span data-stu-id="6ea74-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="6ea74-104">Этот интерфейс является подклассом ICorDebugEnum-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="6ea74-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6ea74-105">Методы</span><span class="sxs-lookup"><span data-stu-id="6ea74-105">Methods</span></span>  
  
|<span data-ttu-id="6ea74-106">Метод</span><span class="sxs-lookup"><span data-stu-id="6ea74-106">Method</span></span>|<span data-ttu-id="6ea74-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6ea74-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6ea74-108">ICorDebugExceptionObjectCallStackEnum::Next</span><span class="sxs-lookup"><span data-stu-id="6ea74-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="6ea74-109">Возвращает заданное число [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) объектов, содержащих сведения о стеке вызовов объект исключения.</span><span class="sxs-lookup"><span data-stu-id="6ea74-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ea74-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="6ea74-110">Remarks</span></span>  
 <span data-ttu-id="6ea74-111">`ICorDebugExceptionObjectCallStackEnum` Интерфейс реализует интерфейс ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="6ea74-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="6ea74-112">`ICorDebugExceptionObjectCallStackEnum` Экземпляр заполняется [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) объектов путем вызова [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="6ea74-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="6ea74-113">Элементы стека вызова в коллекции можно перечислить, вызвав [ICorDebugExceptionObjectCallStackEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md) метод</span><span class="sxs-lookup"><span data-stu-id="6ea74-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ea74-114">Требования</span><span class="sxs-lookup"><span data-stu-id="6ea74-114">Requirements</span></span>  
 <span data-ttu-id="6ea74-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ea74-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ea74-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ea74-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ea74-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ea74-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6ea74-118">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6ea74-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6ea74-119">См. также</span><span class="sxs-lookup"><span data-stu-id="6ea74-119">See also</span></span>

- [<span data-ttu-id="6ea74-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6ea74-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="6ea74-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="6ea74-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
