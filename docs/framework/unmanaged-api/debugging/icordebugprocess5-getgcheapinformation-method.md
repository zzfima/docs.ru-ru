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
ms.openlocfilehash: 50b682a7b3a4aadf7559120745265ef266cf2870
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948750"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="69688-102">Метод ICorDebugProcess5::GetGCHeapInformation</span><span class="sxs-lookup"><span data-stu-id="69688-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="69688-103">Содержит общие сведения о куче для сборки мусора, включая является ли он в настоящее время enumerable.</span><span class="sxs-lookup"><span data-stu-id="69688-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69688-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69688-104">Syntax</span></span>  
  
```  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69688-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="69688-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="69688-106">[out] Указатель на [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) значение, которое предоставляет общие сведения о куче для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="69688-106">[out] A pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69688-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="69688-107">Remarks</span></span>  
 <span data-ttu-id="69688-108">`ICorDebugProcess5::GetGCHeapInformation` Метод должен вызываться перед перечисление кучи или отдельных кучи регионах, чтобы убедиться, что при сборке мусора структуры в процессе не подходит.</span><span class="sxs-lookup"><span data-stu-id="69688-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="69688-109">Куче сбора мусора не может выполнить обход коллекции во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="69688-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="69688-110">В противном случае перечисление может собрать структурами для сборки мусора, которые являются недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="69688-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69688-111">Требования</span><span class="sxs-lookup"><span data-stu-id="69688-111">Requirements</span></span>  
 <span data-ttu-id="69688-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69688-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69688-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69688-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69688-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69688-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69688-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69688-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69688-116">См. также</span><span class="sxs-lookup"><span data-stu-id="69688-116">See also</span></span>

- [<span data-ttu-id="69688-117">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="69688-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="69688-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="69688-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
