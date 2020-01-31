---
title: Интерфейс ICorDebugComObjectValue
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
ms.openlocfilehash: ed5b39ed4b2a14c071bf23fb04efbad6834e8a9d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783974"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="317f2-102">Интерфейс ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="317f2-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="317f2-103">Предоставляет методы для получения сведений, связанных с вызываемой оболочкой времени выполнения (RCW).</span><span class="sxs-lookup"><span data-stu-id="317f2-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="317f2-104">Методы</span><span class="sxs-lookup"><span data-stu-id="317f2-104">Methods</span></span>  
  
|<span data-ttu-id="317f2-105">Метод</span><span class="sxs-lookup"><span data-stu-id="317f2-105">Method</span></span>|<span data-ttu-id="317f2-106">Описание</span><span class="sxs-lookup"><span data-stu-id="317f2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="317f2-107">Метод GetCachedInterfacePointers</span><span class="sxs-lookup"><span data-stu-id="317f2-107">GetCachedInterfacePointers Method</span></span>](icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="317f2-108">Возвращает необработанные указатели интерфейса, кэшированные в текущей RCW.</span><span class="sxs-lookup"><span data-stu-id="317f2-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="317f2-109">Метод GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="317f2-109">GetCachedInterfaceTypes Method</span></span>](icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="317f2-110">Предоставляет перечислитель для типов интерфейса, к которым был применен регистр текущего объекта или использован в качестве.</span><span class="sxs-lookup"><span data-stu-id="317f2-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="317f2-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="317f2-111">Remarks</span></span>  
 <span data-ttu-id="317f2-112">Чтобы проверить, представляет ли экземпляр интерфейса "ICorDebugValue" RCW, отладчик вызывает `QueryInterface` "ICorDebugValue" с `IID_ICorDebugComObjectValue`.</span><span class="sxs-lookup"><span data-stu-id="317f2-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="317f2-113">Требования</span><span class="sxs-lookup"><span data-stu-id="317f2-113">Requirements</span></span>  
 <span data-ttu-id="317f2-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="317f2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="317f2-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="317f2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="317f2-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="317f2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="317f2-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="317f2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="317f2-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="317f2-118">See also</span></span>

- [<span data-ttu-id="317f2-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="317f2-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="317f2-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="317f2-120">Debugging</span></span>](index.md)
