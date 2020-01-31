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
ms.openlocfilehash: 9b96c0a2eca543b9e01ccf92b271b1aa7003c5c9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781938"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="7f8ce-102">Метод ICorDebugManagedCallback::DebuggerError</span><span class="sxs-lookup"><span data-stu-id="7f8ce-102">ICorDebugManagedCallback::DebuggerError Method</span></span>
<span data-ttu-id="7f8ce-103">Уведомляет отладчик о том, что произошла ошибка при попытке выполнить обработку события из среды CLR.</span><span class="sxs-lookup"><span data-stu-id="7f8ce-103">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f8ce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f8ce-104">Syntax</span></span>  
  
```cpp  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f8ce-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7f8ce-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="7f8ce-106">окне Указатель на объект "ICorDebugProcess", представляющий процесс, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="7f8ce-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="7f8ce-107">окне Значение HRESULT, возвращенное обработчиком событий.</span><span class="sxs-lookup"><span data-stu-id="7f8ce-107">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="7f8ce-108">окне Целое число, указывающее ошибку CLR.</span><span class="sxs-lookup"><span data-stu-id="7f8ce-108">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f8ce-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="7f8ce-109">Remarks</span></span>  
 <span data-ttu-id="7f8ce-110">Процесс может быть помещен в сквозной режим в зависимости от характера ошибки.</span><span class="sxs-lookup"><span data-stu-id="7f8ce-110">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="7f8ce-111">Обратный вызов `DebugError` указывает, что службы отладки были отключены из-за ошибки, поэтому Отладчики должны сделать сообщение об ошибке доступным для пользователя.</span><span class="sxs-lookup"><span data-stu-id="7f8ce-111">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="7f8ce-112">[ICorDebugProcess:: GetID](icordebugprocess-getid-method.md) будет использоваться в качестве безопасного вызова, но все остальные методы, включая [ICorDebug:: Terminate](icordebug-terminate-method.md), не должны вызываться.</span><span class="sxs-lookup"><span data-stu-id="7f8ce-112">[ICorDebugProcess::GetID](icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="7f8ce-113">Отладчик должен использовать средства операционной системы для завершения процессов.</span><span class="sxs-lookup"><span data-stu-id="7f8ce-113">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f8ce-114">Требования</span><span class="sxs-lookup"><span data-stu-id="7f8ce-114">Requirements</span></span>  
 <span data-ttu-id="7f8ce-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f8ce-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f8ce-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f8ce-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f8ce-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f8ce-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f8ce-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f8ce-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f8ce-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="7f8ce-119">See also</span></span>

- [<span data-ttu-id="7f8ce-120">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="7f8ce-120">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
