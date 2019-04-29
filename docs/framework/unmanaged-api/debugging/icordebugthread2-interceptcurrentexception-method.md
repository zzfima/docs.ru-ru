---
title: Метод ICorDebugThread2::InterceptCurrentException
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.InterceptCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::InterceptCurrentException
helpviewer_keywords:
- InterceptCurrentException method [.NET Framework debugging]
- ICorDebugThread2::InterceptCurrentException method [.NET Framework debugging]
ms.assetid: 536d2357-1b97-49e0-a10c-c860aed74e6e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01b883a5c6dd0cff119ff09747d32c607ac7ec60
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61968302"
---
# <a name="icordebugthread2interceptcurrentexception-method"></a><span data-ttu-id="eee80-102">Метод ICorDebugThread2::InterceptCurrentException</span><span class="sxs-lookup"><span data-stu-id="eee80-102">ICorDebugThread2::InterceptCurrentException Method</span></span>
<span data-ttu-id="eee80-103">Позволяет отладчику перехватить текущее исключение в данном потоке.</span><span class="sxs-lookup"><span data-stu-id="eee80-103">Allows a debugger to intercept the current exception on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eee80-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eee80-104">Syntax</span></span>  
  
```  
HRESULT InterceptCurrentException (  
    [in] ICorDebugFrame  *pFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eee80-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eee80-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="eee80-106">[in] Указатель на интерфейс ICorDebugFrame, представляющий активный кадр стека.</span><span class="sxs-lookup"><span data-stu-id="eee80-106">[in] A pointer to an ICorDebugFrame that represents the active stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eee80-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="eee80-107">Remarks</span></span>  
 <span data-ttu-id="eee80-108">`InterceptCurrentException` Метод может вызываться между обратного вызова исключения ([ICorDebugManagedCallback::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md) или [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)) и связанные вызов [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md).</span><span class="sxs-lookup"><span data-stu-id="eee80-108">The `InterceptCurrentException` method can be called between an exception callback ([ICorDebugManagedCallback::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md) or [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)) and the associated call to [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eee80-109">Требования</span><span class="sxs-lookup"><span data-stu-id="eee80-109">Requirements</span></span>  
 <span data-ttu-id="eee80-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eee80-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eee80-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eee80-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eee80-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eee80-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eee80-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eee80-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
