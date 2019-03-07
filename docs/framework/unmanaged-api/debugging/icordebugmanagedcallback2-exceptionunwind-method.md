---
title: Метод ICorDebugManagedCallback2::ExceptionUnwind
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ExceptionUnwind
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind
helpviewer_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind method [.NET Framework debugging]
- ExceptionUnwind method [.NET Framework debugging]
ms.assetid: aaf5938d-179c-4eaa-8d35-8523a4fadded
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 802d4987b3be86b5a6302b78f75e4f0c02d49f3e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492040"
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a><span data-ttu-id="48087-102">Метод ICorDebugManagedCallback2::ExceptionUnwind</span><span class="sxs-lookup"><span data-stu-id="48087-102">ICorDebugManagedCallback2::ExceptionUnwind Method</span></span>
<span data-ttu-id="48087-103">Предоставляет уведомление о состоянии во время процесса очистки исключения.</span><span class="sxs-lookup"><span data-stu-id="48087-103">Provides a status notification during the exception unwinding process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48087-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48087-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48087-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="48087-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="48087-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, содержащий поток, на котором возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="48087-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="48087-107">[in] Указатель на объект ICorDebugThread, представляющий поток, на котором возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="48087-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="48087-108">[in] Значение перечисления CorDebugExceptionUnwindCallbackType, указывающий событие, о котором функцией обратного вызова, во время фазы перемотки.</span><span class="sxs-lookup"><span data-stu-id="48087-108">[in] A value of the CorDebugExceptionUnwindCallbackType enumeration that specifies the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="48087-109">[in] Значение [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) перечисление, содержащее дополнительные сведения об исключении.</span><span class="sxs-lookup"><span data-stu-id="48087-109">[in] A value of the [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48087-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="48087-110">Remarks</span></span>  
 <span data-ttu-id="48087-111">`ExceptionUnwind` вызывается в различных точках во время фазы перемотки процесса обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="48087-111">`ExceptionUnwind` is called at various points during the unwind phase of the exception-handling process.</span></span> <span data-ttu-id="48087-112">`ExceptionUnwind` может быть вызван несколько раз во время одного исключения.</span><span class="sxs-lookup"><span data-stu-id="48087-112">`ExceptionUnwind` can be called more than once while unwinding a single exception.</span></span>  
  
 <span data-ttu-id="48087-113">Если `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, указатель инструкции появится во фрейме конечного потока в точке последовательности (это может быть несколько перед) инструкцией, вызвавшей исключение.</span><span class="sxs-lookup"><span data-stu-id="48087-113">If `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, the instruction pointer will be in the leaf frame of the thread, at the sequence point before (this may be several instructions before) the instruction that led to the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48087-114">Требования</span><span class="sxs-lookup"><span data-stu-id="48087-114">Requirements</span></span>  
 <span data-ttu-id="48087-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48087-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48087-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48087-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48087-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48087-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48087-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48087-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48087-119">См. также</span><span class="sxs-lookup"><span data-stu-id="48087-119">See also</span></span>
- [<span data-ttu-id="48087-120">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="48087-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="48087-121">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="48087-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
