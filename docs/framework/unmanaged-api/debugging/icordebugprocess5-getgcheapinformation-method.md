---
title: Метод ICorDebugProcess5::GetGCHeapInformation
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetGCHeapInformation
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f8824ce004cac8bc2ad675c83dc6b5f167f183e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421051"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="548a8-102">Метод ICorDebugProcess5::GetGCHeapInformation</span><span class="sxs-lookup"><span data-stu-id="548a8-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="548a8-103">Содержит общие сведения о куче для сборки мусора, является ли он в настоящее время перечислимой.</span><span class="sxs-lookup"><span data-stu-id="548a8-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="548a8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="548a8-104">Syntax</span></span>  
  
```  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="548a8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="548a8-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="548a8-106">[out] Указатель на [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) значение, которое предоставляет общие сведения о куче сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="548a8-106">[out] A pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="548a8-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="548a8-107">Remarks</span></span>  
 <span data-ttu-id="548a8-108">`ICorDebugProcess5::GetGCHeapInformation` Метод должен вызываться перед перечислением кучи или отдельных кучи области, чтобы убедиться в том, что сборка мусора структуры в процессе — действителен в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="548a8-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="548a8-109">Невозможно рассмотреть куче сборщика мусора, коллекцию во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="548a8-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="548a8-110">В противном случае — перечисление может собрать структурами для сборки мусора, являются недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="548a8-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="548a8-111">Требования</span><span class="sxs-lookup"><span data-stu-id="548a8-111">Requirements</span></span>  
 <span data-ttu-id="548a8-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="548a8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="548a8-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="548a8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="548a8-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="548a8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="548a8-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="548a8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="548a8-116">См. также</span><span class="sxs-lookup"><span data-stu-id="548a8-116">See Also</span></span>  
 [<span data-ttu-id="548a8-117">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="548a8-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="548a8-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="548a8-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
