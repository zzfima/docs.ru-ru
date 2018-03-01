---
title: "Интерфейс ICorDebugILFrame3"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugILFrame3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 15212cb5-93d4-4025-bec9-d4b9919eb1fe
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1096942775dd579fa530415873694b3e6e67a74a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe3-interface"></a><span data-ttu-id="d27a5-102">Интерфейс ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="d27a5-102">ICorDebugILFrame3 Interface</span></span>
<span data-ttu-id="d27a5-103">Предоставляет метод, инкапсулирующий возвращаемое значение функции.</span><span class="sxs-lookup"><span data-stu-id="d27a5-103">Provides a method that encapsulates the return value of a function.</span></span> <span data-ttu-id="d27a5-104">`ICorDebugILFrame3`является логическим расширением ICorDebugILFrame и ICorDebugILFrame2 интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="d27a5-104">`ICorDebugILFrame3` is a logical extension of the ICorDebugILFrame and ICorDebugILFrame2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d27a5-105">Методы</span><span class="sxs-lookup"><span data-stu-id="d27a5-105">Methods</span></span>  
  
|<span data-ttu-id="d27a5-106">Метод</span><span class="sxs-lookup"><span data-stu-id="d27a5-106">Method</span></span>|<span data-ttu-id="d27a5-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="d27a5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d27a5-108">Метод GetReturnValueForILOffset</span><span class="sxs-lookup"><span data-stu-id="d27a5-108">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)|<span data-ttu-id="d27a5-109">Возвращает объект ICorDebugValue, инкапсулирующий возвращаемое значение функции.</span><span class="sxs-lookup"><span data-stu-id="d27a5-109">Gets an ICorDebugValue object that encapsulates the return value of a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d27a5-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="d27a5-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d27a5-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="d27a5-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d27a5-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d27a5-112">Requirements</span></span>  
 <span data-ttu-id="d27a5-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d27a5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d27a5-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d27a5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d27a5-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d27a5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d27a5-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d27a5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d27a5-117">См. также</span><span class="sxs-lookup"><span data-stu-id="d27a5-117">See Also</span></span>  
 [<span data-ttu-id="d27a5-118">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="d27a5-118">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [<span data-ttu-id="d27a5-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d27a5-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
