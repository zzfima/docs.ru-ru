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
ms.openlocfilehash: c03be2405e1ab0287a2921b6e2e293862c67a193
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137375"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="f8efe-102">Метод ICorDebugManagedCallback::DebuggerError</span><span class="sxs-lookup"><span data-stu-id="f8efe-102">ICorDebugManagedCallback::DebuggerError Method</span></span>
<span data-ttu-id="f8efe-103">Уведомляет отладчик о том, что произошла ошибка при попытке выполнить обработку события из среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f8efe-103">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8efe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8efe-104">Syntax</span></span>  
  
```cpp  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8efe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f8efe-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="f8efe-106">окне Указатель на объект "ICorDebugProcess", представляющий процесс, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="f8efe-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="f8efe-107">окне Значение HRESULT, возвращенное обработчиком событий.</span><span class="sxs-lookup"><span data-stu-id="f8efe-107">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="f8efe-108">окне Целое число, указывающее ошибку CLR.</span><span class="sxs-lookup"><span data-stu-id="f8efe-108">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8efe-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="f8efe-109">Remarks</span></span>  
 <span data-ttu-id="f8efe-110">Процесс может быть помещен в сквозной режим в зависимости от характера ошибки.</span><span class="sxs-lookup"><span data-stu-id="f8efe-110">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="f8efe-111">Обратный вызов `DebugError` указывает, что службы отладки были отключены из-за ошибки, поэтому Отладчики должны сделать сообщение об ошибке доступным для пользователя.</span><span class="sxs-lookup"><span data-stu-id="f8efe-111">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="f8efe-112">[ICorDebugProcess:: GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) будет использоваться в качестве безопасного вызова, но все остальные методы, включая [ICorDebug:: Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), не должны вызываться.</span><span class="sxs-lookup"><span data-stu-id="f8efe-112">[ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="f8efe-113">Отладчик должен использовать средства операционной системы для завершения процессов.</span><span class="sxs-lookup"><span data-stu-id="f8efe-113">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8efe-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f8efe-114">Requirements</span></span>  
 <span data-ttu-id="f8efe-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8efe-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8efe-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8efe-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8efe-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8efe-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8efe-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8efe-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8efe-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f8efe-119">See also</span></span>

- [<span data-ttu-id="f8efe-120">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="f8efe-120">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
