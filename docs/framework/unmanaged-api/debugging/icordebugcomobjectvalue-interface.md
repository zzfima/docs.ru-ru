---
title: "Интерфейс ICorDebugComObjectValue Interface"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugComObjectValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugComObjectValue
helpviewer_keywords: ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8d339d3146a8a9214c3518eac6c31ed5222f9b31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="fed74-102">Интерфейс ICorDebugComObjectValue Interface</span><span class="sxs-lookup"><span data-stu-id="fed74-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="fed74-103">Предоставляет методы для получения сведений, связанных с вызываемой оболочки времени выполнения (RCW).</span><span class="sxs-lookup"><span data-stu-id="fed74-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fed74-104">Методы</span><span class="sxs-lookup"><span data-stu-id="fed74-104">Methods</span></span>  
  
|<span data-ttu-id="fed74-105">Метод</span><span class="sxs-lookup"><span data-stu-id="fed74-105">Method</span></span>|<span data-ttu-id="fed74-106">Описание</span><span class="sxs-lookup"><span data-stu-id="fed74-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fed74-107">Метод GetCachedInterfacePointers</span><span class="sxs-lookup"><span data-stu-id="fed74-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="fed74-108">Возвращает интерфейс необработанные указатели, кэшируются на текущем вызываемая оболочка времени Выполнения.</span><span class="sxs-lookup"><span data-stu-id="fed74-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="fed74-109">Метод GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="fed74-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="fed74-110">Предоставляет перечислитель для типов интерфейсов, что текущий объект был случаем и или использовать в качестве.</span><span class="sxs-lookup"><span data-stu-id="fed74-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fed74-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="fed74-111">Remarks</span></span>  
 <span data-ttu-id="fed74-112">Чтобы проверить, представляет ли экземпляр интерфейса «ICorDebugValue» RCW, отладчик вызывает `QueryInterface` на «ICorDebugValue» с `IID_ICorDebugComObjectValue`.</span><span class="sxs-lookup"><span data-stu-id="fed74-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fed74-113">Требования</span><span class="sxs-lookup"><span data-stu-id="fed74-113">Requirements</span></span>  
 <span data-ttu-id="fed74-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fed74-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fed74-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fed74-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fed74-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fed74-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fed74-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fed74-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed74-118">См. также</span><span class="sxs-lookup"><span data-stu-id="fed74-118">See Also</span></span>  
 [<span data-ttu-id="fed74-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="fed74-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="fed74-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="fed74-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
