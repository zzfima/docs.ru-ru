---
title: Метод ICorDebug::Terminate
ms.date: 03/30/2017
api_name:
- ICorDebug.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de37bb34aee9b6536ff892ac30855761bcc69445
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963131"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="8aeee-102">Метод ICorDebug::Terminate</span><span class="sxs-lookup"><span data-stu-id="8aeee-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="8aeee-103">`ICorDebug` Завершает объект.</span><span class="sxs-lookup"><span data-stu-id="8aeee-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8aeee-104">`Terminate`не следует вызывать, пока не получен обратный вызов [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) для всех отлаживаемых процессов.</span><span class="sxs-lookup"><span data-stu-id="8aeee-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aeee-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8aeee-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="8aeee-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="8aeee-106">Remarks</span></span>  
 <span data-ttu-id="8aeee-107">`Terminate`должен вызываться, `ICorDebug` когда объект больше не нужен.</span><span class="sxs-lookup"><span data-stu-id="8aeee-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8aeee-108">Требования</span><span class="sxs-lookup"><span data-stu-id="8aeee-108">Requirements</span></span>  
 <span data-ttu-id="8aeee-109">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8aeee-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8aeee-110">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="8aeee-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8aeee-111">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="8aeee-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8aeee-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8aeee-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aeee-113">См. также</span><span class="sxs-lookup"><span data-stu-id="8aeee-113">See also</span></span>

- [<span data-ttu-id="8aeee-114">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="8aeee-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
