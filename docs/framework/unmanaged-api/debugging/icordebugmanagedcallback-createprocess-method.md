---
title: Метод ICorDebugManagedCallback::CreateProcess
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateProcess
helpviewer_keywords:
- ICorDebugManagedCallback::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: 8e89d5ee-e4e3-4738-8302-0b7d1cf4846e
topic_type:
- apiref
ms.openlocfilehash: d773368c85fd42fd169109cf1c7e6635705ebb7e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090227"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="e4119-102">Метод ICorDebugManagedCallback::CreateProcess</span><span class="sxs-lookup"><span data-stu-id="e4119-102">ICorDebugManagedCallback::CreateProcess Method</span></span>
<span data-ttu-id="e4119-103">Уведомляет отладчик о том, что процесс был присоединен или запущен в первый раз.</span><span class="sxs-lookup"><span data-stu-id="e4119-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4119-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e4119-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4119-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e4119-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="e4119-106">окне Указатель на объект ICorDebugProcess, представляющий процесс, который был присоединен или запущен.</span><span class="sxs-lookup"><span data-stu-id="e4119-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4119-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="e4119-107">Remarks</span></span>  
 <span data-ttu-id="e4119-108">Этот метод не вызывается до тех пор, пока не будет инициализирована среда CLR.</span><span class="sxs-lookup"><span data-stu-id="e4119-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="e4119-109">Большая часть методов [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) возвратит CORDBG_E_NOTREADY перед обратным вызовом `CreateProcess`.</span><span class="sxs-lookup"><span data-stu-id="e4119-109">Most of the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4119-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e4119-110">Requirements</span></span>  
 <span data-ttu-id="e4119-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4119-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4119-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4119-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4119-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4119-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4119-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4119-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4119-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e4119-115">See also</span></span>

- [<span data-ttu-id="e4119-116">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="e4119-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
