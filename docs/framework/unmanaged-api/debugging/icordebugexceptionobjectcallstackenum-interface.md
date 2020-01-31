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
ms.openlocfilehash: 9d98bccdfb83cec547b185693c28f25017d3225f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782799"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="9785c-102">Интерфейс ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="9785c-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>
<span data-ttu-id="9785c-103">Предоставляет перечислитель для сведений стека вызовов, встроенных в объект исключения.</span><span class="sxs-lookup"><span data-stu-id="9785c-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="9785c-104">Этот интерфейс является подклассом интерфейса ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="9785c-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9785c-105">Методы</span><span class="sxs-lookup"><span data-stu-id="9785c-105">Methods</span></span>  
  
|<span data-ttu-id="9785c-106">Метод</span><span class="sxs-lookup"><span data-stu-id="9785c-106">Method</span></span>|<span data-ttu-id="9785c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9785c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9785c-108">ICorDebugExceptionObjectCallStackEnum:: Next</span><span class="sxs-lookup"><span data-stu-id="9785c-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="9785c-109">Возвращает указанное число объектов [кордебужексцептионобжектстаккфраме](cordebugexceptionobjectstackframe-structure.md) , содержащих сведения о стеке вызовов объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="9785c-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9785c-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="9785c-110">Remarks</span></span>  
 <span data-ttu-id="9785c-111">Интерфейс `ICorDebugExceptionObjectCallStackEnum` реализует интерфейс ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="9785c-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="9785c-112">Экземпляр `ICorDebugExceptionObjectCallStackEnum` заполняется объектами [кордебужексцептионобжектстаккфраме](cordebugexceptionobjectstackframe-structure.md) путем вызова метода [ICorDebugExceptionObjectValue:: EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9785c-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="9785c-113">Элементы стека вызовов в коллекции можно перечислить, вызвав метод [ICorDebugExceptionObjectCallStackEnum:: Next.](icordebugexceptionobjectcallstackenum-next-method.md)</span><span class="sxs-lookup"><span data-stu-id="9785c-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9785c-114">Требования</span><span class="sxs-lookup"><span data-stu-id="9785c-114">Requirements</span></span>  
 <span data-ttu-id="9785c-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9785c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9785c-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9785c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9785c-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9785c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9785c-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9785c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9785c-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="9785c-119">See also</span></span>

- [<span data-ttu-id="9785c-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9785c-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9785c-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="9785c-121">Debugging</span></span>](index.md)
