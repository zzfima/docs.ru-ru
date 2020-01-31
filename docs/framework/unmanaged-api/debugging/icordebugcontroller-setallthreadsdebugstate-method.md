---
title: Метод ICorDebugController::SetAllThreadsDebugState
ms.date: 03/30/2017
api_name:
- ICorDebugController.SetAllThreadsDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type:
- apiref
ms.openlocfilehash: be7fce700756d7120e0853446b7b307ec77c2080
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783762"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="c7bb9-102">Метод ICorDebugController::SetAllThreadsDebugState</span><span class="sxs-lookup"><span data-stu-id="c7bb9-102">ICorDebugController::SetAllThreadsDebugState Method</span></span>
<span data-ttu-id="c7bb9-103">Задает состояние отладки всех управляемых потоков в процессе.</span><span class="sxs-lookup"><span data-stu-id="c7bb9-103">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7bb9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7bb9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7bb9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7bb9-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="c7bb9-106">окне Значение перечисления "Кордебугсреадстате", указывающее состояние потока для отладки.</span><span class="sxs-lookup"><span data-stu-id="c7bb9-106">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="c7bb9-107">окне Указатель на объект "ICorDebugThread", представляющий поток, исключаемый из параметра состояния отладки.</span><span class="sxs-lookup"><span data-stu-id="c7bb9-107">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="c7bb9-108">Если это значение равно null, ни один поток не исключен.</span><span class="sxs-lookup"><span data-stu-id="c7bb9-108">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7bb9-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="c7bb9-109">Remarks</span></span>  
 <span data-ttu-id="c7bb9-110">Метод `SetAllThreadsDebugState` может повлиять на потоки, которые не видны через [метод енумератесреадс](icordebugcontroller-enumeratethreads-method.md), поэтому потоки, которые были приостановлены с помощью метода `SetAllThreadsDebugState`, необходимо возобновить с помощью метода `SetAllThreadsDebugState`.</span><span class="sxs-lookup"><span data-stu-id="c7bb9-110">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7bb9-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c7bb9-111">Requirements</span></span>  
 <span data-ttu-id="c7bb9-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7bb9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7bb9-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7bb9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7bb9-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7bb9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7bb9-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7bb9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7bb9-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="c7bb9-116">See also</span></span>
