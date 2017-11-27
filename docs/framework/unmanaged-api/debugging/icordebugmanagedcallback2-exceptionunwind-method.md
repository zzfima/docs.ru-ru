---
title: "Метод ICorDebugManagedCallback2::ExceptionUnwind"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.ExceptionUnwind
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::ExceptionUnwind
helpviewer_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind method [.NET Framework debugging]
- ExceptionUnwind method [.NET Framework debugging]
ms.assetid: aaf5938d-179c-4eaa-8d35-8523a4fadded
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 45b9f5838e4bc98e3f269a2cebd575abfe998a2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a><span data-ttu-id="24ea8-102">Метод ICorDebugManagedCallback2::ExceptionUnwind</span><span class="sxs-lookup"><span data-stu-id="24ea8-102">ICorDebugManagedCallback2::ExceptionUnwind Method</span></span>
<span data-ttu-id="24ea8-103">Предоставляет уведомление о состоянии во время процесса очистки исключения.</span><span class="sxs-lookup"><span data-stu-id="24ea8-103">Provides a status notification during the exception unwinding process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24ea8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24ea8-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="24ea8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="24ea8-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="24ea8-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, содержащий поток, в котором возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="24ea8-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="24ea8-107">[in] Указатель на объект ICorDebugThread, представляющий поток, в котором возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="24ea8-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="24ea8-108">[in] Значение перечисления CorDebugExceptionUnwindCallbackType, который указывает событие, о котором обратный вызов во время фазы перемотки.</span><span class="sxs-lookup"><span data-stu-id="24ea8-108">[in] A value of the CorDebugExceptionUnwindCallbackType enumeration that specifies the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="24ea8-109">[in] Значение [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) перечисления, в котором указываются дополнительные сведения об исключении.</span><span class="sxs-lookup"><span data-stu-id="24ea8-109">[in] A value of the [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24ea8-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="24ea8-110">Remarks</span></span>  
 <span data-ttu-id="24ea8-111">`ExceptionUnwind`вызывается в различных точках во время фазы перемотки процесс обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="24ea8-111">`ExceptionUnwind` is called at various points during the unwind phase of the exception-handling process.</span></span> <span data-ttu-id="24ea8-112">`ExceptionUnwind`можно вызывать несколько раз во время одного исключения.</span><span class="sxs-lookup"><span data-stu-id="24ea8-112">`ExceptionUnwind` can be called more than once while unwinding a single exception.</span></span>  
  
 <span data-ttu-id="24ea8-113">Если `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, указатель инструкций будет в конечном кадре потока в точке последовательности (это может быть несколько инструкций до) инструкцией, вызвавшей исключение.</span><span class="sxs-lookup"><span data-stu-id="24ea8-113">If `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, the instruction pointer will be in the leaf frame of the thread, at the sequence point before (this may be several instructions before) the instruction that led to the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24ea8-114">Требования</span><span class="sxs-lookup"><span data-stu-id="24ea8-114">Requirements</span></span>  
 <span data-ttu-id="24ea8-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24ea8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24ea8-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24ea8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24ea8-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24ea8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24ea8-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24ea8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24ea8-119">См. также</span><span class="sxs-lookup"><span data-stu-id="24ea8-119">See Also</span></span>  
 [<span data-ttu-id="24ea8-120">ICorDebugManagedCallback2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="24ea8-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="24ea8-121">ICorDebugManagedCallback-интерфейс</span><span class="sxs-lookup"><span data-stu-id="24ea8-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
