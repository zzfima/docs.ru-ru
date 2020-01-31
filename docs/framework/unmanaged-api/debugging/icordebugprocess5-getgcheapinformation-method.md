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
ms.openlocfilehash: 703f159c5bc6b73dcd0e770bdeb61f676aae034c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792380"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="e6618-102">Метод ICorDebugProcess5::GetGCHeapInformation</span><span class="sxs-lookup"><span data-stu-id="e6618-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="e6618-103">Содержит общие сведения о куче сборки мусора, включая возможность перечисления в данный момент.</span><span class="sxs-lookup"><span data-stu-id="e6618-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6618-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6618-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6618-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e6618-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="e6618-106">заполняет Указатель на [COR_HEAPINFO](cor-heapinfo-structure.md) значение, предоставляющее общие сведения о куче сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="e6618-106">[out] A pointer to a [COR_HEAPINFO](cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6618-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="e6618-107">Remarks</span></span>  
 <span data-ttu-id="e6618-108">Перед перечислением областей кучи или отдельных куч необходимо вызвать метод `ICorDebugProcess5::GetGCHeapInformation`, чтобы убедиться в том, что структуры сборки мусора в этом процессе являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="e6618-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="e6618-109">Невозможно выполнить обход кучи сборки мусора, пока выполняется сбор.</span><span class="sxs-lookup"><span data-stu-id="e6618-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="e6618-110">В противном случае перечисление может собирать недопустимые структуры сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="e6618-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6618-111">Требования</span><span class="sxs-lookup"><span data-stu-id="e6618-111">Requirements</span></span>  
 <span data-ttu-id="e6618-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6618-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6618-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6618-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6618-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6618-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6618-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6618-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6618-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="e6618-116">See also</span></span>

- [<span data-ttu-id="e6618-117">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="e6618-117">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="e6618-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e6618-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
