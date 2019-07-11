---
title: Метод ICorDebugThread::GetDebugState
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetDebugState
helpviewer_keywords:
- GetDebugState method [.NET Framework debugging]
- ICorDebugThread::GetDebugState method [.NET Framework debugging]
ms.assetid: 9be27b0c-1d99-4722-b0d4-40cf6753ce5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0baabbb736365b138d1754e68070207b4310bf57
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762460"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="78013-102">Метод ICorDebugThread::GetDebugState</span><span class="sxs-lookup"><span data-stu-id="78013-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="78013-103">Возвращает текущее состояние отладки объекта ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="78013-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78013-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78013-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78013-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="78013-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="78013-106">[out] Указатель на побитовое сочетание значений перечисления CorDebugThreadState, описывающее текущее состояние отладки для данного потока.</span><span class="sxs-lookup"><span data-stu-id="78013-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78013-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="78013-107">Remarks</span></span>  
 <span data-ttu-id="78013-108">Если в настоящее время остановки процесса, `pState` представляет состояние отладки, который будет существовать для данного потока, будто процесс будет продолжен, а не фактическое текущее состояние данного потока.</span><span class="sxs-lookup"><span data-stu-id="78013-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78013-109">Требования</span><span class="sxs-lookup"><span data-stu-id="78013-109">Requirements</span></span>  
 <span data-ttu-id="78013-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78013-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78013-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="78013-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78013-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78013-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78013-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78013-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
