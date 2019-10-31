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
ms.openlocfilehash: fa317e1217ac0a9ca46bfeb312446534b1fca63a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131563"
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a><span data-ttu-id="5c664-102">Метод ICorDebugManagedCallback2::ExceptionUnwind</span><span class="sxs-lookup"><span data-stu-id="5c664-102">ICorDebugManagedCallback2::ExceptionUnwind Method</span></span>
<span data-ttu-id="5c664-103">Предоставляет уведомление о состоянии во время процесса очистки исключения.</span><span class="sxs-lookup"><span data-stu-id="5c664-103">Provides a status notification during the exception unwinding process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c664-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c664-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c664-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5c664-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5c664-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий поток, в котором было создано исключение.</span><span class="sxs-lookup"><span data-stu-id="5c664-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="5c664-107">окне Указатель на объект ICorDebugThread, представляющий поток, в котором было создано исключение.</span><span class="sxs-lookup"><span data-stu-id="5c664-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="5c664-108">окне Значение перечисления Кордебужексцептионунвиндкаллбакктипе, указывающее событие, сигнальное функцией обратного вызова на этапе очистки.</span><span class="sxs-lookup"><span data-stu-id="5c664-108">[in] A value of the CorDebugExceptionUnwindCallbackType enumeration that specifies the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="5c664-109">окне Значение перечисления [кордебужексцептионфлагс](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) , которое указывает дополнительные сведения об исключении.</span><span class="sxs-lookup"><span data-stu-id="5c664-109">[in] A value of the [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c664-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="5c664-110">Remarks</span></span>  
 <span data-ttu-id="5c664-111">`ExceptionUnwind` вызывается в различных точках на этапе очистки процесса обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="5c664-111">`ExceptionUnwind` is called at various points during the unwind phase of the exception-handling process.</span></span> <span data-ttu-id="5c664-112">`ExceptionUnwind` можно вызывать более одного раза при очистке одного исключения.</span><span class="sxs-lookup"><span data-stu-id="5c664-112">`ExceptionUnwind` can be called more than once while unwinding a single exception.</span></span>  
  
 <span data-ttu-id="5c664-113">Если `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, указатель инструкции будет находиться в конечном кадре потока в точке следования до (это может быть несколько инструкций до) инструкции, которая привела к исключению.</span><span class="sxs-lookup"><span data-stu-id="5c664-113">If `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, the instruction pointer will be in the leaf frame of the thread, at the sequence point before (this may be several instructions before) the instruction that led to the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c664-114">Требования</span><span class="sxs-lookup"><span data-stu-id="5c664-114">Requirements</span></span>  
 <span data-ttu-id="5c664-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c664-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c664-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c664-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c664-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c664-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c664-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c664-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c664-119">См. также</span><span class="sxs-lookup"><span data-stu-id="5c664-119">See also</span></span>

- [<span data-ttu-id="5c664-120">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="5c664-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="5c664-121">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="5c664-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
