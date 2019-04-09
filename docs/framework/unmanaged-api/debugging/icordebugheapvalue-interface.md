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
ms.openlocfilehash: d5fcd8c17c4006714fa9d11aece5cccc57c97087
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075500"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="8ce3b-102">Интерфейс ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="8ce3b-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="8ce3b-103">Подкласс «ICorDebugValue», который представляет объект, собранных сборщиком мусора среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="8ce3b-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8ce3b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="8ce3b-104">Methods</span></span>  
  
|<span data-ttu-id="8ce3b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="8ce3b-105">Method</span></span>|<span data-ttu-id="8ce3b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="8ce3b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8ce3b-107">Метод CreateRelocBreakpoint</span><span class="sxs-lookup"><span data-stu-id="8ce3b-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="8ce3b-108">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="8ce3b-108">Not implemented.</span></span>|  
|[<span data-ttu-id="8ce3b-109">Метод IsValid</span><span class="sxs-lookup"><span data-stu-id="8ce3b-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="8ce3b-110">Получает значение, указывающее, является ли объект, представленный это `ICorDebugHeapValue` является допустимым, или он был удален сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="8ce3b-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="8ce3b-111">Этот метод был объявлен устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="8ce3b-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ce3b-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="8ce3b-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ce3b-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="8ce3b-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ce3b-114">Требования</span><span class="sxs-lookup"><span data-stu-id="8ce3b-114">Requirements</span></span>  
 <span data-ttu-id="8ce3b-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ce3b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ce3b-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ce3b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ce3b-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ce3b-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8ce3b-118">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8ce3b-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8ce3b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="8ce3b-119">See also</span></span>

- [<span data-ttu-id="8ce3b-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8ce3b-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
