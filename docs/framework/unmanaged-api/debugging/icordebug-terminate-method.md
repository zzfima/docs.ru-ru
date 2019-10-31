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
ms.openlocfilehash: 78838e9002cb3f5263395af9de255c54de47b6ae
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134019"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="14644-102">Метод ICorDebug::Terminate</span><span class="sxs-lookup"><span data-stu-id="14644-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="14644-103">Завершает объект `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="14644-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="14644-104">`Terminate` не следует вызывать, пока не получен обратный вызов [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) для всех отлаживаемых процессов.</span><span class="sxs-lookup"><span data-stu-id="14644-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14644-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14644-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="14644-106">Заметки</span><span class="sxs-lookup"><span data-stu-id="14644-106">Remarks</span></span>  
 <span data-ttu-id="14644-107">`Terminate` должны вызываться, когда объект `ICorDebug` больше не нужен.</span><span class="sxs-lookup"><span data-stu-id="14644-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14644-108">Требования</span><span class="sxs-lookup"><span data-stu-id="14644-108">Requirements</span></span>  
 <span data-ttu-id="14644-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14644-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14644-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14644-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14644-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14644-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14644-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14644-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14644-113">См. также</span><span class="sxs-lookup"><span data-stu-id="14644-113">See also</span></span>

- [<span data-ttu-id="14644-114">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="14644-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
