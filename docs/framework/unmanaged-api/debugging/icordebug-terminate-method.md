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
ms.openlocfilehash: 3037fc704ffc3aac4d050cef7857261f138f7d35
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738075"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="39132-102">Метод ICorDebug::Terminate</span><span class="sxs-lookup"><span data-stu-id="39132-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="39132-103">Завершает `ICorDebug` объекта.</span><span class="sxs-lookup"><span data-stu-id="39132-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39132-104">`Terminate` не следует вызывать до [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) получено обратного вызова для всех отлаживаемых процессов.</span><span class="sxs-lookup"><span data-stu-id="39132-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39132-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39132-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="39132-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="39132-106">Remarks</span></span>  
 <span data-ttu-id="39132-107">`Terminate` должен вызываться при `ICorDebug` объект больше не нужен.</span><span class="sxs-lookup"><span data-stu-id="39132-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39132-108">Требования</span><span class="sxs-lookup"><span data-stu-id="39132-108">Requirements</span></span>  
 <span data-ttu-id="39132-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39132-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39132-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39132-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39132-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39132-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39132-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39132-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39132-113">См. также</span><span class="sxs-lookup"><span data-stu-id="39132-113">See also</span></span>

- [<span data-ttu-id="39132-114">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="39132-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
