---
title: Метод ICorDebugProcess::ClearCurrentException
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ClearCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ClearCurrentException
helpviewer_keywords:
- ClearCurrentException method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::ClearCurrentException method [.NET Framework debugging]
ms.assetid: 9e02ee1a-e495-4578-bfb5-b946274bede7
topic_type:
- apiref
ms.openlocfilehash: 4cfacb7f3303947ec8b11362fde82649687889d8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792665"
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="385b2-102">Метод ICorDebugProcess::ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="385b2-102">ICorDebugProcess::ClearCurrentException Method</span></span>
<span data-ttu-id="385b2-103">Очищает текущее неуправляемое исключение для данного потока.</span><span class="sxs-lookup"><span data-stu-id="385b2-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="385b2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="385b2-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="385b2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="385b2-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="385b2-106">окне Идентификатор потока, в котором будет очищаться текущее неуправляемое исключение.</span><span class="sxs-lookup"><span data-stu-id="385b2-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="385b2-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="385b2-107">Remarks</span></span>  
 <span data-ttu-id="385b2-108">Вызывайте этот метод перед вызовом [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) , когда поток сообщил о неуправляемом исключении, которое должно игнорироваться отлаживаемым объектом.</span><span class="sxs-lookup"><span data-stu-id="385b2-108">Call this method before calling [ICorDebugController::Continue](icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="385b2-109">Это приведет к удалению необработанных внутренних () и нестандартных событий (OOB) для данного потока.</span><span class="sxs-lookup"><span data-stu-id="385b2-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="385b2-110">Все точки останова OOB и одношаговые исключения автоматически очищаются.</span><span class="sxs-lookup"><span data-stu-id="385b2-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="385b2-111">Используйте [ICorDebugThread2:: интерцепткуррентексцептион](icordebugthread2-interceptcurrentexception-method.md) для перехвата текущего управляемого исключения в потоке.</span><span class="sxs-lookup"><span data-stu-id="385b2-111">Use [ICorDebugThread2::InterceptCurrentException](icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="385b2-112">Требования</span><span class="sxs-lookup"><span data-stu-id="385b2-112">Requirements</span></span>  
 <span data-ttu-id="385b2-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="385b2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="385b2-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="385b2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="385b2-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="385b2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="385b2-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="385b2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
