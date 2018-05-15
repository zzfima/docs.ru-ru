---
title: Метод ICorDebugManagedCallback2::Exception
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::Exception
helpviewer_keywords:
- ICorDebugManagedCallback2::Exception method [.NET Framework debugging]
- Exception method, ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: 78b0f14f-2fae-4e63-8412-4df119ee8468
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: faefff879142d66c4c596f1b30a25e349a4014b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallback2exception-method"></a><span data-ttu-id="b5821-102">Метод ICorDebugManagedCallback2::Exception</span><span class="sxs-lookup"><span data-stu-id="b5821-102">ICorDebugManagedCallback2::Exception Method</span></span>
<span data-ttu-id="b5821-103">Уведомляет отладчик о начале поиска для обработчика исключений.</span><span class="sxs-lookup"><span data-stu-id="b5821-103">Notifies the debugger that a search for an exception handler has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5821-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5821-104">Syntax</span></span>  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5821-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b5821-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="b5821-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, содержащий поток, в котором возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="b5821-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="b5821-107">[in] Указатель на объект ICorDebugThread, представляющий поток, в котором возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="b5821-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="b5821-108">[in] Указатель на объект ICorDebugFrame, который представляет кадр, что определяется `dwEventType` параметра.</span><span class="sxs-lookup"><span data-stu-id="b5821-108">[in] A pointer to an ICorDebugFrame object that represents a frame, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="b5821-109">Дополнительные сведения см. в таблице в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="b5821-109">For more information, see the table in the Remarks section.</span></span>  
  
 `nOffset`  
 <span data-ttu-id="b5821-110">[in] Целое число, определяющее смещение определяется `dwEventType` параметра.</span><span class="sxs-lookup"><span data-stu-id="b5821-110">[in] An integer that specifies an offset, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="b5821-111">Дополнительные сведения см. в таблице в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="b5821-111">For more information, see the table in the Remarks section.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="b5821-112">[in] Значение перечисления CorDebugExceptionCallbackType, которое указывает тип обратного вызова, это исключение.</span><span class="sxs-lookup"><span data-stu-id="b5821-112">[in] A value of the CorDebugExceptionCallbackType enumeration that specifies the type of this exception callback.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b5821-113">[in] Значение [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) перечисления, в котором указываются дополнительные сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="b5821-113">[in] A value of the [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5821-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="b5821-114">Remarks</span></span>  
 <span data-ttu-id="b5821-115">`Exception` Обратного вызова вызывается в различных точках этапа поиска процесса обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="b5821-115">The `Exception` callback is called at various points during the search phase of the exception-handling process.</span></span> <span data-ttu-id="b5821-116">То есть он может быть вызван больше, чем один раз во время очистки исключения.</span><span class="sxs-lookup"><span data-stu-id="b5821-116">That is, it can be called more than once while unwinding an exception.</span></span>  
  
 <span data-ttu-id="b5821-117">Исключение обрабатывается могут быть получены из ICorDebugThread объект, упоминаемый в `pThread` параметра.</span><span class="sxs-lookup"><span data-stu-id="b5821-117">The exception being processed can be retrieved from the ICorDebugThread object referenced by the `pThread` parameter.</span></span>  
  
 <span data-ttu-id="b5821-118">Определенный кадр и смещение определяются `dwEventType` параметр следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b5821-118">The particular frame and offset are determined by the `dwEventType` parameter as follows:</span></span>  
  
|<span data-ttu-id="b5821-119">Значение `dwEventType`</span><span class="sxs-lookup"><span data-stu-id="b5821-119">Value of `dwEventType`</span></span>|<span data-ttu-id="b5821-120">Значение `pFrame`</span><span class="sxs-lookup"><span data-stu-id="b5821-120">Value of `pFrame`</span></span>|<span data-ttu-id="b5821-121">Значение `nOffset`</span><span class="sxs-lookup"><span data-stu-id="b5821-121">Value of `nOffset`</span></span>|  
|----------------------------|-----------------------|------------------------|  
|<span data-ttu-id="b5821-122">DEBUG_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="b5821-122">DEBUG_EXCEPTION_FIRST_CHANCE</span></span>|<span data-ttu-id="b5821-123">Кадр, который вызвал исключение.</span><span class="sxs-lookup"><span data-stu-id="b5821-123">The frame that threw the exception.</span></span>|<span data-ttu-id="b5821-124">Указатель инструкций в кадре.</span><span class="sxs-lookup"><span data-stu-id="b5821-124">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="b5821-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="b5821-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span></span>|<span data-ttu-id="b5821-126">Фрейма пользовательского кода, ближайшего к точке вызванного исключения.</span><span class="sxs-lookup"><span data-stu-id="b5821-126">The user-code frame closest to the point of the thrown exception.</span></span>|<span data-ttu-id="b5821-127">Указатель инструкций в кадре.</span><span class="sxs-lookup"><span data-stu-id="b5821-127">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="b5821-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="b5821-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span></span>|<span data-ttu-id="b5821-129">Кадр, содержащего обработчик catch.</span><span class="sxs-lookup"><span data-stu-id="b5821-129">The frame that contains the catch handler.</span></span>|<span data-ttu-id="b5821-130">Смещение промежуточного языка MSIL Корпорация Майкрософт начала обработчика блока catch.</span><span class="sxs-lookup"><span data-stu-id="b5821-130">The Microsoft intermediate language (MSIL) offset of the beginning of the catch handler.</span></span>|  
|<span data-ttu-id="b5821-131">DEBUG_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="b5821-131">DEBUG_EXCEPTION_UNHANDLED</span></span>|<span data-ttu-id="b5821-132">NULL</span><span class="sxs-lookup"><span data-stu-id="b5821-132">NULL</span></span>|<span data-ttu-id="b5821-133">Не определено.</span><span class="sxs-lookup"><span data-stu-id="b5821-133">Undefined.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b5821-134">Требования</span><span class="sxs-lookup"><span data-stu-id="b5821-134">Requirements</span></span>  
 <span data-ttu-id="b5821-135">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5821-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5821-136">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5821-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5821-137">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5821-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5821-138">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5821-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5821-139">См. также</span><span class="sxs-lookup"><span data-stu-id="b5821-139">See Also</span></span>  
 [<span data-ttu-id="b5821-140">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="b5821-140">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="b5821-141">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="b5821-141">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
