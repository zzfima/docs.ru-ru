---
title: "Метод ICorDebugProcess5::GetGCHeapInformation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.GetGCHeapInformation
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: da423914d8af20c0f942d53ed6ac9f34ace01ca9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="f9de2-102">Метод ICorDebugProcess5::GetGCHeapInformation</span><span class="sxs-lookup"><span data-stu-id="f9de2-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="f9de2-103">Содержит общие сведения о куче для сборки мусора, является ли он в настоящее время перечислимой.</span><span class="sxs-lookup"><span data-stu-id="f9de2-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9de2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9de2-104">Syntax</span></span>  
  
```  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f9de2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f9de2-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="f9de2-106">[out] Указатель на [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) значение, которое предоставляет общие сведения о куче сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="f9de2-106">[out] A pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9de2-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f9de2-107">Remarks</span></span>  
 <span data-ttu-id="f9de2-108">`ICorDebugProcess5::GetGCHeapInformation` Метод должен вызываться перед перечислением кучи или отдельных кучи области, чтобы убедиться в том, что сборка мусора структуры в процессе — действителен в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="f9de2-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="f9de2-109">Невозможно рассмотреть куче сборщика мусора, коллекцию во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f9de2-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="f9de2-110">В противном случае — перечисление может собрать структурами для сборки мусора, являются недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="f9de2-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9de2-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f9de2-111">Requirements</span></span>  
 <span data-ttu-id="f9de2-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9de2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9de2-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f9de2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9de2-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9de2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9de2-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9de2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9de2-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f9de2-116">See Also</span></span>  
 [<span data-ttu-id="f9de2-117">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="f9de2-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="f9de2-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f9de2-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
