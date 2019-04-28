---
title: Интерфейс ICorDebugComObjectValue Interface
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugComObjectValue
helpviewer_keywords:
- ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3387985ebf6027b9cd9dee372190da65939dbae3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749701"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="7f2be-102">Интерфейс ICorDebugComObjectValue Interface</span><span class="sxs-lookup"><span data-stu-id="7f2be-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="7f2be-103">Предоставляет методы для получения сведений, связанных с вызываемой оболочки времени выполнения (RCW).</span><span class="sxs-lookup"><span data-stu-id="7f2be-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7f2be-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7f2be-104">Methods</span></span>  
  
|<span data-ttu-id="7f2be-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7f2be-105">Method</span></span>|<span data-ttu-id="7f2be-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7f2be-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7f2be-107">Метод GetCachedInterfacePointers</span><span class="sxs-lookup"><span data-stu-id="7f2be-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="7f2be-108">Возвращает интерфейс необработанные указатели, кэшируются на текущем вызываемая оболочка времени Выполнения.</span><span class="sxs-lookup"><span data-stu-id="7f2be-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="7f2be-109">Метод GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="7f2be-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="7f2be-110">Предоставляет перечислитель для типов интерфейсов, что текущий объект был преобразование из или использовать в качестве.</span><span class="sxs-lookup"><span data-stu-id="7f2be-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f2be-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="7f2be-111">Remarks</span></span>  
 <span data-ttu-id="7f2be-112">Чтобы проверить, представляет ли экземпляр интерфейс «ICorDebugValue» RCW, отладчик вызывает `QueryInterface` на «ICorDebugValue» с `IID_ICorDebugComObjectValue`.</span><span class="sxs-lookup"><span data-stu-id="7f2be-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f2be-113">Требования</span><span class="sxs-lookup"><span data-stu-id="7f2be-113">Requirements</span></span>  
 <span data-ttu-id="7f2be-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f2be-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f2be-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f2be-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f2be-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f2be-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f2be-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f2be-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f2be-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7f2be-118">See also</span></span>

- [<span data-ttu-id="7f2be-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7f2be-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="7f2be-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="7f2be-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
