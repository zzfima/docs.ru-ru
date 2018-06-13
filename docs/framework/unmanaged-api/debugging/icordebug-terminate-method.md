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
ms.openlocfilehash: 2c2b590e7402bf29ffeb5bd14fc383edae41a04e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404005"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="db343-102">Метод ICorDebug::Terminate</span><span class="sxs-lookup"><span data-stu-id="db343-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="db343-103">Завершает `ICorDebug` объекта.</span><span class="sxs-lookup"><span data-stu-id="db343-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db343-104">`Terminate` не следует вызывать до [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) получил обратного вызова для всех отлаживаемых процессов.</span><span class="sxs-lookup"><span data-stu-id="db343-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db343-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db343-105">Syntax</span></span>  
  
```  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="db343-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="db343-106">Remarks</span></span>  
 <span data-ttu-id="db343-107">`Terminate` должно вызываться при `ICorDebug` объект больше не нужен.</span><span class="sxs-lookup"><span data-stu-id="db343-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db343-108">Требования</span><span class="sxs-lookup"><span data-stu-id="db343-108">Requirements</span></span>  
 <span data-ttu-id="db343-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db343-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db343-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db343-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db343-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db343-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db343-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db343-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db343-113">См. также</span><span class="sxs-lookup"><span data-stu-id="db343-113">See Also</span></span>  
 [<span data-ttu-id="db343-114">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="db343-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
