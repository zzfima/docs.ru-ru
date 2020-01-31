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
ms.openlocfilehash: 0c3059697014cea33081f6cb81b9d93c7d028c2e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777465"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="10075-102">Метод ICorDebugManagedCallback::CreateProcess</span><span class="sxs-lookup"><span data-stu-id="10075-102">ICorDebugManagedCallback::CreateProcess Method</span></span>
<span data-ttu-id="10075-103">Уведомляет отладчик о том, что процесс был присоединен или запущен в первый раз.</span><span class="sxs-lookup"><span data-stu-id="10075-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10075-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10075-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10075-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="10075-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="10075-106">окне Указатель на объект ICorDebugProcess, представляющий процесс, который был присоединен или запущен.</span><span class="sxs-lookup"><span data-stu-id="10075-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10075-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="10075-107">Remarks</span></span>  
 <span data-ttu-id="10075-108">Этот метод не вызывается до тех пор, пока не будет инициализирована среда CLR.</span><span class="sxs-lookup"><span data-stu-id="10075-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="10075-109">Большая часть методов [ICorDebug](icordebug-interface.md) будет возвращать CORDBG_E_NOTREADY перед обратным вызовом `CreateProcess`.</span><span class="sxs-lookup"><span data-stu-id="10075-109">Most of the [ICorDebug](icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10075-110">Требования</span><span class="sxs-lookup"><span data-stu-id="10075-110">Requirements</span></span>  
 <span data-ttu-id="10075-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10075-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10075-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10075-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10075-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10075-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10075-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10075-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10075-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="10075-115">See also</span></span>

- [<span data-ttu-id="10075-116">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="10075-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
