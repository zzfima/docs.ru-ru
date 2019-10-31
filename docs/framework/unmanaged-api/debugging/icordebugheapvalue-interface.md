---
title: Интерфейс ICorDebugHeapValue
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue
helpviewer_keywords:
- ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type:
- apiref
ms.openlocfilehash: 4f87065fc4a3d80a8363f3ae2fbb76c29f3d9b96
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138418"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="a3264-102">Интерфейс ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="a3264-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="a3264-103">Подкласс "ICorDebugValue", представляющий объект, собранный сборщиком мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="a3264-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a3264-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a3264-104">Methods</span></span>  
  
|<span data-ttu-id="a3264-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a3264-105">Method</span></span>|<span data-ttu-id="a3264-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a3264-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a3264-107">Метод CreateRelocBreakpoint</span><span class="sxs-lookup"><span data-stu-id="a3264-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="a3264-108">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="a3264-108">Not implemented.</span></span>|  
|[<span data-ttu-id="a3264-109">Метод IsValid</span><span class="sxs-lookup"><span data-stu-id="a3264-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="a3264-110">Возвращает значение, указывающее, является ли допустимым объект, представленный данным `ICorDebugHeapValue`, или освобожден сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="a3264-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="a3264-111">Этот метод не рекомендуется к использованию в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="a3264-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3264-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="a3264-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a3264-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="a3264-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3264-114">Требования</span><span class="sxs-lookup"><span data-stu-id="a3264-114">Requirements</span></span>  
 <span data-ttu-id="a3264-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3264-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3264-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3264-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3264-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3264-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3264-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3264-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3264-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a3264-119">See also</span></span>

- [<span data-ttu-id="a3264-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a3264-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
