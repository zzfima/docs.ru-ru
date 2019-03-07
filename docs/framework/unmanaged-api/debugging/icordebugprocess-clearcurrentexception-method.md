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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f014f9213a4b9a2d5119af9a6dceebb9a9d54b52
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473477"
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="62341-102">Метод ICorDebugProcess::ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="62341-102">ICorDebugProcess::ClearCurrentException Method</span></span>
<span data-ttu-id="62341-103">Очищает текущее неуправляемое исключение в данном потоке.</span><span class="sxs-lookup"><span data-stu-id="62341-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62341-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62341-104">Syntax</span></span>  
  
```  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62341-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="62341-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="62341-106">[in] Идентификатор потока, на котором будет очищен текущее неуправляемое исключение.</span><span class="sxs-lookup"><span data-stu-id="62341-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62341-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="62341-107">Remarks</span></span>  
 <span data-ttu-id="62341-108">Вызовите этот метод перед вызовом [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) когда поток сообщил неуправляемые исключения, которое следует игнорировать при отладке.</span><span class="sxs-lookup"><span data-stu-id="62341-108">Call this method before calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="62341-109">Это приведет к устранению диапазона (IB) и события (OOB)-каналу в данном потоке.</span><span class="sxs-lookup"><span data-stu-id="62341-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="62341-110">Все точки останова OOB и одношаговые исключения автоматически очищается.</span><span class="sxs-lookup"><span data-stu-id="62341-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="62341-111">Используйте [ICorDebugThread2::InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) для перехвата текущего управляемые исключения в потоке.</span><span class="sxs-lookup"><span data-stu-id="62341-111">Use [ICorDebugThread2::InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62341-112">Требования</span><span class="sxs-lookup"><span data-stu-id="62341-112">Requirements</span></span>  
 <span data-ttu-id="62341-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62341-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62341-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62341-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62341-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62341-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62341-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62341-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
