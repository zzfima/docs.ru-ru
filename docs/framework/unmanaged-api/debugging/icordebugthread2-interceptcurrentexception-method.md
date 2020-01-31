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
ms.openlocfilehash: c25a03ef5bbba18da31787c911f83a1348badd4b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791453"
---
# <a name="icordebugthread2interceptcurrentexception-method"></a><span data-ttu-id="707e6-102">Метод ICorDebugThread2::InterceptCurrentException</span><span class="sxs-lookup"><span data-stu-id="707e6-102">ICorDebugThread2::InterceptCurrentException Method</span></span>
<span data-ttu-id="707e6-103">Позволяет отладчику перехватить текущее исключение в этом потоке.</span><span class="sxs-lookup"><span data-stu-id="707e6-103">Allows a debugger to intercept the current exception on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="707e6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="707e6-104">Syntax</span></span>  
  
```cpp  
HRESULT InterceptCurrentException (  
    [in] ICorDebugFrame  *pFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="707e6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="707e6-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="707e6-106">окне Указатель на объект ICorDebugFrame, представляющий активный кадр стека.</span><span class="sxs-lookup"><span data-stu-id="707e6-106">[in] A pointer to an ICorDebugFrame that represents the active stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="707e6-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="707e6-107">Remarks</span></span>  
 <span data-ttu-id="707e6-108">Метод `InterceptCurrentException` может быть вызван между обратным вызовом исключения ([ICorDebugManagedCallback:: Exception](icordebugmanagedcallback-exception-method.md) или [ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md)) и связанным вызовом [ICorDebugController:: Continue](icordebugcontroller-continue-method.md).</span><span class="sxs-lookup"><span data-stu-id="707e6-108">The `InterceptCurrentException` method can be called between an exception callback ([ICorDebugManagedCallback::Exception](icordebugmanagedcallback-exception-method.md) or [ICorDebugManagedCallback2::Exception](icordebugmanagedcallback2-exception-method.md)) and the associated call to [ICorDebugController::Continue](icordebugcontroller-continue-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="707e6-109">Требования</span><span class="sxs-lookup"><span data-stu-id="707e6-109">Requirements</span></span>  
 <span data-ttu-id="707e6-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="707e6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="707e6-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="707e6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="707e6-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="707e6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="707e6-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="707e6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
