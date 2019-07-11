---
title: Метод ICorDebugManagedCallback::DebuggerError
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.DebuggerError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6abc4893ac99c5ce93a409a8120f090250be57c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759660"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="9f343-102">Метод ICorDebugManagedCallback::DebuggerError</span><span class="sxs-lookup"><span data-stu-id="9f343-102">ICorDebugManagedCallback::DebuggerError Method</span></span>
<span data-ttu-id="9f343-103">Уведомляет отладчик о том, что произошла ошибка при попытке обработать события из общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="9f343-103">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f343-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f343-104">Syntax</span></span>  
  
```cpp  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f343-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9f343-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="9f343-106">[in] Указатель на объект «ICorDebugProcess», представляющий процесс, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="9f343-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="9f343-107">[in] Значение HRESULT, который был возвращен из обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="9f343-107">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="9f343-108">[in] Целое число, задающее ошибку среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9f343-108">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f343-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="9f343-109">Remarks</span></span>  
 <span data-ttu-id="9f343-110">Процесс может размещаться в сквозном режиме, в зависимости от типа ошибки.</span><span class="sxs-lookup"><span data-stu-id="9f343-110">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="9f343-111">`DebugError` Обратный вызов указывает, что службы отладки были отключены из-за ошибки, поэтому отладчики должны предоставить сообщение об ошибке доступны пользователю.</span><span class="sxs-lookup"><span data-stu-id="9f343-111">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="9f343-112">[ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) безопасные для вызова, но все другие методы, включая [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), не следует вызывать.</span><span class="sxs-lookup"><span data-stu-id="9f343-112">[ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="9f343-113">Отладчик должен воспользоваться возможностями системы для завершения процессов.</span><span class="sxs-lookup"><span data-stu-id="9f343-113">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f343-114">Требования</span><span class="sxs-lookup"><span data-stu-id="9f343-114">Requirements</span></span>  
 <span data-ttu-id="9f343-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f343-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f343-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f343-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f343-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f343-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f343-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f343-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f343-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9f343-119">See also</span></span>

- [<span data-ttu-id="9f343-120">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="9f343-120">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
