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
ms.openlocfilehash: 4ff5c0d470e6eb84eb8b526f5e8f74e5e1a8118a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125490"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="1bb9c-102">Интерфейс ICorDebugComObjectValue Interface</span><span class="sxs-lookup"><span data-stu-id="1bb9c-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="1bb9c-103">Предоставляет методы для получения сведений, связанных с вызываемой оболочкой времени выполнения (RCW).</span><span class="sxs-lookup"><span data-stu-id="1bb9c-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1bb9c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="1bb9c-104">Methods</span></span>  
  
|<span data-ttu-id="1bb9c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="1bb9c-105">Method</span></span>|<span data-ttu-id="1bb9c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="1bb9c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1bb9c-107">Метод GetCachedInterfacePointers</span><span class="sxs-lookup"><span data-stu-id="1bb9c-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="1bb9c-108">Возвращает необработанные указатели интерфейса, кэшированные в текущей RCW.</span><span class="sxs-lookup"><span data-stu-id="1bb9c-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="1bb9c-109">Метод GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="1bb9c-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="1bb9c-110">Предоставляет перечислитель для типов интерфейса, к которым был применен регистр текущего объекта или использован в качестве.</span><span class="sxs-lookup"><span data-stu-id="1bb9c-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bb9c-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="1bb9c-111">Remarks</span></span>  
 <span data-ttu-id="1bb9c-112">Чтобы проверить, представляет ли экземпляр интерфейса "ICorDebugValue" RCW, отладчик вызывает `QueryInterface` "ICorDebugValue" с `IID_ICorDebugComObjectValue`.</span><span class="sxs-lookup"><span data-stu-id="1bb9c-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bb9c-113">Требования</span><span class="sxs-lookup"><span data-stu-id="1bb9c-113">Requirements</span></span>  
 <span data-ttu-id="1bb9c-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bb9c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bb9c-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1bb9c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1bb9c-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bb9c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1bb9c-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bb9c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bb9c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="1bb9c-118">See also</span></span>

- [<span data-ttu-id="1bb9c-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1bb9c-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="1bb9c-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="1bb9c-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
