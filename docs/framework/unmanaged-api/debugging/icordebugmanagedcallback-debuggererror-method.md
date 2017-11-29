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
ms.openlocfilehash: c4eb16762d2a0db01c3cc921712a89995e0c87c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="1cf9a-102">Метод ICorDebugManagedCallback::DebuggerError</span><span class="sxs-lookup"><span data-stu-id="1cf9a-102">ICorDebugManagedCallback::DebuggerError Method</span></span>
<span data-ttu-id="1cf9a-103">Уведомляет отладчик о том, что произошла ошибка при попытке обработать событие из общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="1cf9a-103">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cf9a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1cf9a-104">Syntax</span></span>  
  
```  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1cf9a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1cf9a-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="1cf9a-106">[in] Указатель на объект «ICorDebugProcess», который представляет собой процесс, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="1cf9a-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="1cf9a-107">[in] Значение HRESULT, возвращенный из обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="1cf9a-107">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="1cf9a-108">[in] Целое число, задающее ошибку среды CLR.</span><span class="sxs-lookup"><span data-stu-id="1cf9a-108">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1cf9a-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="1cf9a-109">Remarks</span></span>  
 <span data-ttu-id="1cf9a-110">Процесс может быть переведен в сквозной режим, в зависимости от характера ошибки.</span><span class="sxs-lookup"><span data-stu-id="1cf9a-110">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="1cf9a-111">`DebugError` Обратного вызова указывает, что службы отладки были отключены из-за ошибки, поэтому отладчики должны предоставить сообщение об ошибке доступны пользователю.</span><span class="sxs-lookup"><span data-stu-id="1cf9a-111">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="1cf9a-112">[ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) безопасные вызова, а также всех других методов, включая [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), не должен вызываться.</span><span class="sxs-lookup"><span data-stu-id="1cf9a-112">[ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="1cf9a-113">Для завершения процессов отладчик должен воспользоваться возможностями системы.</span><span class="sxs-lookup"><span data-stu-id="1cf9a-113">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cf9a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1cf9a-114">Requirements</span></span>  
 <span data-ttu-id="1cf9a-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cf9a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cf9a-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1cf9a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1cf9a-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1cf9a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1cf9a-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cf9a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cf9a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="1cf9a-119">See Also</span></span>  
 [<span data-ttu-id="1cf9a-120">ICorDebugManagedCallback-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1cf9a-120">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
