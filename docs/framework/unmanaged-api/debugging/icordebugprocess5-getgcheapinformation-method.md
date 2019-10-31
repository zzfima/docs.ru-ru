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
ms.openlocfilehash: 3aa9fe884b16a239f5105dd262edeb8fc3e4abaa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084406"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="b03d7-102">Метод ICorDebugProcess5::GetGCHeapInformation</span><span class="sxs-lookup"><span data-stu-id="b03d7-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="b03d7-103">Содержит общие сведения о куче сборки мусора, включая возможность перечисления в данный момент.</span><span class="sxs-lookup"><span data-stu-id="b03d7-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b03d7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b03d7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b03d7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b03d7-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="b03d7-106">заполняет Указатель на значение [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) , предоставляющее общие сведения о куче сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="b03d7-106">[out] A pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b03d7-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="b03d7-107">Remarks</span></span>  
 <span data-ttu-id="b03d7-108">Перед перечислением областей кучи или отдельных куч необходимо вызвать метод `ICorDebugProcess5::GetGCHeapInformation`, чтобы убедиться в том, что структуры сборки мусора в этом процессе являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="b03d7-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="b03d7-109">Невозможно выполнить обход кучи сборки мусора, пока выполняется сбор.</span><span class="sxs-lookup"><span data-stu-id="b03d7-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="b03d7-110">В противном случае перечисление может собирать недопустимые структуры сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="b03d7-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b03d7-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b03d7-111">Requirements</span></span>  
 <span data-ttu-id="b03d7-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b03d7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b03d7-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b03d7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b03d7-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b03d7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b03d7-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b03d7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b03d7-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b03d7-116">See also</span></span>

- [<span data-ttu-id="b03d7-117">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="b03d7-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="b03d7-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b03d7-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
