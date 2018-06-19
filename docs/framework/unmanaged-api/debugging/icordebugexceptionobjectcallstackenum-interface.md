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
ms.openlocfilehash: e6df9c7e24e2303571b7cb3b80ff4bf07dc59ccc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415669"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="f80fd-102">Интерфейс ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="f80fd-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>
<span data-ttu-id="f80fd-103">Предоставляет перечислитель для сведений стека вызовов, встроенных в объект исключения.</span><span class="sxs-lookup"><span data-stu-id="f80fd-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="f80fd-104">Этот интерфейс является подклассом ICorDebugEnum-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f80fd-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f80fd-105">Методы</span><span class="sxs-lookup"><span data-stu-id="f80fd-105">Methods</span></span>  
  
|<span data-ttu-id="f80fd-106">Метод</span><span class="sxs-lookup"><span data-stu-id="f80fd-106">Method</span></span>|<span data-ttu-id="f80fd-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f80fd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f80fd-108">ICorDebugExceptionObjectCallStackEnum::Next</span><span class="sxs-lookup"><span data-stu-id="f80fd-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="f80fd-109">Возвращает заданное число [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) объекты, содержащие сведения о стеке вызовов объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="f80fd-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f80fd-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="f80fd-110">Remarks</span></span>  
 <span data-ttu-id="f80fd-111">`ICorDebugExceptionObjectCallStackEnum` ICorDebugEnum-интерфейс реализует интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f80fd-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="f80fd-112">`ICorDebugExceptionObjectCallStackEnum` Заполненный экземпляр [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) объектов путем вызова [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="f80fd-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="f80fd-113">Элементы стека вызова в коллекции могут быть перечислены путем вызова [ICorDebugExceptionObjectCallStackEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md) метод</span><span class="sxs-lookup"><span data-stu-id="f80fd-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f80fd-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f80fd-114">Requirements</span></span>  
 <span data-ttu-id="f80fd-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f80fd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f80fd-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f80fd-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f80fd-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f80fd-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f80fd-118">**Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f80fd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f80fd-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f80fd-119">See Also</span></span>  
 [<span data-ttu-id="f80fd-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f80fd-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="f80fd-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="f80fd-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
