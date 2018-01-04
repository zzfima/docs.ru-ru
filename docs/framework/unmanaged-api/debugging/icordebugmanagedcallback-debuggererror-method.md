---
title: "Метод ICorDebugManagedCallback::DebuggerError"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.DebuggerError
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cc92bc6a1718d9d3505443e5b13786d1a359481f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="49e6c-102">Метод ICorDebugManagedCallback::DebuggerError</span><span class="sxs-lookup"><span data-stu-id="49e6c-102">ICorDebugManagedCallback::DebuggerError Method</span></span>
<span data-ttu-id="49e6c-103">Уведомляет отладчик о том, что произошла ошибка при попытке обработать событие из общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="49e6c-103">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49e6c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49e6c-104">Syntax</span></span>  
  
```  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49e6c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="49e6c-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="49e6c-106">[in] Указатель на объект «ICorDebugProcess», который представляет собой процесс, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="49e6c-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="49e6c-107">[in] Значение HRESULT, возвращенный из обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="49e6c-107">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="49e6c-108">[in] Целое число, задающее ошибку среды CLR.</span><span class="sxs-lookup"><span data-stu-id="49e6c-108">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49e6c-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="49e6c-109">Remarks</span></span>  
 <span data-ttu-id="49e6c-110">Процесс может быть переведен в сквозной режим, в зависимости от характера ошибки.</span><span class="sxs-lookup"><span data-stu-id="49e6c-110">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="49e6c-111">`DebugError` Обратного вызова указывает, что службы отладки были отключены из-за ошибки, поэтому отладчики должны предоставить сообщение об ошибке доступны пользователю.</span><span class="sxs-lookup"><span data-stu-id="49e6c-111">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="49e6c-112">[ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) безопасные вызова, а также всех других методов, включая [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), не должен вызываться.</span><span class="sxs-lookup"><span data-stu-id="49e6c-112">[ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="49e6c-113">Для завершения процессов отладчик должен воспользоваться возможностями системы.</span><span class="sxs-lookup"><span data-stu-id="49e6c-113">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49e6c-114">Требования</span><span class="sxs-lookup"><span data-stu-id="49e6c-114">Requirements</span></span>  
 <span data-ttu-id="49e6c-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49e6c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49e6c-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49e6c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49e6c-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49e6c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49e6c-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49e6c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49e6c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="49e6c-119">See Also</span></span>  
 [<span data-ttu-id="49e6c-120">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="49e6c-120">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
