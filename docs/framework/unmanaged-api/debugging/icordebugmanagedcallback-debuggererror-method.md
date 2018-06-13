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
ms.openlocfilehash: 436be84ad91bb20bfd88a51f2d6c2b760c4a4c3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420141"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="b272b-102">Метод ICorDebugManagedCallback::DebuggerError</span><span class="sxs-lookup"><span data-stu-id="b272b-102">ICorDebugManagedCallback::DebuggerError Method</span></span>
<span data-ttu-id="b272b-103">Уведомляет отладчик о том, что произошла ошибка при попытке обработать событие из общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="b272b-103">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b272b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b272b-104">Syntax</span></span>  
  
```  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b272b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b272b-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="b272b-106">[in] Указатель на объект «ICorDebugProcess», который представляет собой процесс, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="b272b-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="b272b-107">[in] Значение HRESULT, возвращенный из обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="b272b-107">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="b272b-108">[in] Целое число, задающее ошибку среды CLR.</span><span class="sxs-lookup"><span data-stu-id="b272b-108">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b272b-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="b272b-109">Remarks</span></span>  
 <span data-ttu-id="b272b-110">Процесс может быть переведен в сквозной режим, в зависимости от характера ошибки.</span><span class="sxs-lookup"><span data-stu-id="b272b-110">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="b272b-111">`DebugError` Обратного вызова указывает, что службы отладки были отключены из-за ошибки, поэтому отладчики должны предоставить сообщение об ошибке доступны пользователю.</span><span class="sxs-lookup"><span data-stu-id="b272b-111">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="b272b-112">[ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) безопасные вызова, а также всех других методов, включая [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), не должен вызываться.</span><span class="sxs-lookup"><span data-stu-id="b272b-112">[ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="b272b-113">Для завершения процессов отладчик должен воспользоваться возможностями системы.</span><span class="sxs-lookup"><span data-stu-id="b272b-113">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b272b-114">Требования</span><span class="sxs-lookup"><span data-stu-id="b272b-114">Requirements</span></span>  
 <span data-ttu-id="b272b-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b272b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b272b-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b272b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b272b-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b272b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b272b-118">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b272b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b272b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="b272b-119">See Also</span></span>  
 [<span data-ttu-id="b272b-120">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="b272b-120">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
