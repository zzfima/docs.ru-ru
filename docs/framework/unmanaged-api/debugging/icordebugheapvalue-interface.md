---
title: "ICorDebugHeapValue интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapValue
helpviewer_keywords: ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d2ab132b73369526204f8fd811e1567b07b4a9b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugheapvalue-interface1"></a><span data-ttu-id="67c46-102">ICorDebugHeapValue интерфейс1</span><span class="sxs-lookup"><span data-stu-id="67c46-102">ICorDebugHeapValue Interface1</span></span>
<span data-ttu-id="67c46-103">Подкласс «ICorDebugValue», который представляет объект, собранных сборщиком мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="67c46-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="67c46-104">Методы</span><span class="sxs-lookup"><span data-stu-id="67c46-104">Methods</span></span>  
  
|<span data-ttu-id="67c46-105">Метод</span><span class="sxs-lookup"><span data-stu-id="67c46-105">Method</span></span>|<span data-ttu-id="67c46-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="67c46-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="67c46-107">Метод CreateRelocBreakpoint</span><span class="sxs-lookup"><span data-stu-id="67c46-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="67c46-108">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="67c46-108">Not implemented.</span></span>|  
|[<span data-ttu-id="67c46-109">Метод IsValid</span><span class="sxs-lookup"><span data-stu-id="67c46-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="67c46-110">Возвращает значение, указывающее, является ли объект, представленный это `ICorDebugHeapValue` является допустимым или удален сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="67c46-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="67c46-111">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="67c46-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67c46-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="67c46-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67c46-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="67c46-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67c46-114">Требования</span><span class="sxs-lookup"><span data-stu-id="67c46-114">Requirements</span></span>  
 <span data-ttu-id="67c46-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67c46-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67c46-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67c46-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67c46-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67c46-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67c46-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67c46-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67c46-119">См. также</span><span class="sxs-lookup"><span data-stu-id="67c46-119">See Also</span></span>  
    
    
    
 [<span data-ttu-id="67c46-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="67c46-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
