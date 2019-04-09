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
ms.openlocfilehash: 321298ce942b35d11a861c87cdf6b8714179ea97
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080843"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="e81d1-102">Метод ICorDebug::Terminate</span><span class="sxs-lookup"><span data-stu-id="e81d1-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="e81d1-103">Завершает `ICorDebug` объекта.</span><span class="sxs-lookup"><span data-stu-id="e81d1-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
>  `Terminate` <span data-ttu-id="e81d1-104">не следует вызывать до [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) получено обратного вызова для всех отлаживаемых процессов.</span><span class="sxs-lookup"><span data-stu-id="e81d1-104">should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e81d1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e81d1-105">Syntax</span></span>  
  
```  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e81d1-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="e81d1-106">Remarks</span></span>  
 `Terminate` <span data-ttu-id="e81d1-107">должен вызываться при `ICorDebug` объект больше не нужен.</span><span class="sxs-lookup"><span data-stu-id="e81d1-107">must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e81d1-108">Требования</span><span class="sxs-lookup"><span data-stu-id="e81d1-108">Requirements</span></span>  
 <span data-ttu-id="e81d1-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e81d1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e81d1-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e81d1-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e81d1-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e81d1-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e81d1-112">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e81d1-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e81d1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e81d1-113">See also</span></span>

- [<span data-ttu-id="e81d1-114">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="e81d1-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
