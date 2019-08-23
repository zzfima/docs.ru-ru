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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb130f11975eb95db7807126d6f163425439b0c4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914901"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="a0df8-102">Интерфейс ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="a0df8-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="a0df8-103">Подкласс "ICorDebugValue", представляющий объект, собранный сборщиком мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="a0df8-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a0df8-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a0df8-104">Methods</span></span>  
  
|<span data-ttu-id="a0df8-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a0df8-105">Method</span></span>|<span data-ttu-id="a0df8-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a0df8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a0df8-107">Метод CreateRelocBreakpoint</span><span class="sxs-lookup"><span data-stu-id="a0df8-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="a0df8-108">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="a0df8-108">Not implemented.</span></span>|  
|[<span data-ttu-id="a0df8-109">Метод IsValid</span><span class="sxs-lookup"><span data-stu-id="a0df8-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="a0df8-110">Возвращает значение, указывающее, является ли объект, представленный `ICorDebugHeapValue` этим объектом, допустимым или освобожденным сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="a0df8-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="a0df8-111">Этот метод не рекомендуется к использованию в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="a0df8-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0df8-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0df8-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a0df8-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="a0df8-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0df8-114">Требования</span><span class="sxs-lookup"><span data-stu-id="a0df8-114">Requirements</span></span>  
 <span data-ttu-id="a0df8-115">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0df8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0df8-116">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="a0df8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0df8-117">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="a0df8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0df8-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0df8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0df8-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a0df8-119">See also</span></span>

- [<span data-ttu-id="a0df8-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a0df8-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
