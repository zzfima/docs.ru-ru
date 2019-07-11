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
ms.openlocfilehash: fd707685dfff31644565db18e72dc153d25781f4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761075"
---
# <a name="icordebugmanagedcallback2exception-method"></a><span data-ttu-id="c4e71-102">Метод ICorDebugManagedCallback2::Exception</span><span class="sxs-lookup"><span data-stu-id="c4e71-102">ICorDebugManagedCallback2::Exception Method</span></span>
<span data-ttu-id="c4e71-103">Уведомляет отладчик о начале поиска обработчика исключений.</span><span class="sxs-lookup"><span data-stu-id="c4e71-103">Notifies the debugger that a search for an exception handler has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4e71-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4e71-104">Syntax</span></span>  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4e71-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c4e71-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="c4e71-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, содержащий поток, на котором возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="c4e71-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="c4e71-107">[in] Указатель на объект ICorDebugThread, представляющий поток, на котором возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="c4e71-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="c4e71-108">[in] Указатель на интерфейс ICorDebugFrame объект, представляющий кадр, что определяется `dwEventType` параметра.</span><span class="sxs-lookup"><span data-stu-id="c4e71-108">[in] A pointer to an ICorDebugFrame object that represents a frame, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="c4e71-109">Дополнительные сведения см. в таблице в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="c4e71-109">For more information, see the table in the Remarks section.</span></span>  
  
 `nOffset`  
 <span data-ttu-id="c4e71-110">[in] Целое число, указывающее смещение, определяемое `dwEventType` параметра.</span><span class="sxs-lookup"><span data-stu-id="c4e71-110">[in] An integer that specifies an offset, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="c4e71-111">Дополнительные сведения см. в таблице в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="c4e71-111">For more information, see the table in the Remarks section.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="c4e71-112">[in] Значение перечисления CorDebugExceptionCallbackType, которое указывает тип этого обратного вызова исключения.</span><span class="sxs-lookup"><span data-stu-id="c4e71-112">[in] A value of the CorDebugExceptionCallbackType enumeration that specifies the type of this exception callback.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c4e71-113">[in] Значение [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) перечисление, содержащее дополнительные сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="c4e71-113">[in] A value of the [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4e71-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="c4e71-114">Remarks</span></span>  
 <span data-ttu-id="c4e71-115">`Exception` Обратный вызов выполняется в различных точках этапа поиска процесса обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="c4e71-115">The `Exception` callback is called at various points during the search phase of the exception-handling process.</span></span> <span data-ttu-id="c4e71-116">То есть он может быть вызван больше, чем один раз во время очистки исключения.</span><span class="sxs-lookup"><span data-stu-id="c4e71-116">That is, it can be called more than once while unwinding an exception.</span></span>  
  
 <span data-ttu-id="c4e71-117">Исключение обрабатывается можно получить из объекта ICorDebugThread ссылается `pThread` параметра.</span><span class="sxs-lookup"><span data-stu-id="c4e71-117">The exception being processed can be retrieved from the ICorDebugThread object referenced by the `pThread` parameter.</span></span>  
  
 <span data-ttu-id="c4e71-118">Определенный кадр и смещение определяется `dwEventType` параметр следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c4e71-118">The particular frame and offset are determined by the `dwEventType` parameter as follows:</span></span>  
  
|<span data-ttu-id="c4e71-119">Значение `dwEventType`</span><span class="sxs-lookup"><span data-stu-id="c4e71-119">Value of `dwEventType`</span></span>|<span data-ttu-id="c4e71-120">Значение `pFrame`</span><span class="sxs-lookup"><span data-stu-id="c4e71-120">Value of `pFrame`</span></span>|<span data-ttu-id="c4e71-121">Значение `nOffset`</span><span class="sxs-lookup"><span data-stu-id="c4e71-121">Value of `nOffset`</span></span>|  
|----------------------------|-----------------------|------------------------|  
|<span data-ttu-id="c4e71-122">DEBUG_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="c4e71-122">DEBUG_EXCEPTION_FIRST_CHANCE</span></span>|<span data-ttu-id="c4e71-123">Фрейма, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="c4e71-123">The frame that threw the exception.</span></span>|<span data-ttu-id="c4e71-124">Указатель инструкций в кадре.</span><span class="sxs-lookup"><span data-stu-id="c4e71-124">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="c4e71-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="c4e71-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span></span>|<span data-ttu-id="c4e71-126">Фрейма пользовательского кода, ближайшего к точке вызванного исключения.</span><span class="sxs-lookup"><span data-stu-id="c4e71-126">The user-code frame closest to the point of the thrown exception.</span></span>|<span data-ttu-id="c4e71-127">Указатель инструкций в кадре.</span><span class="sxs-lookup"><span data-stu-id="c4e71-127">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="c4e71-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="c4e71-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span></span>|<span data-ttu-id="c4e71-129">Кадр, содержащего обработчик catch.</span><span class="sxs-lookup"><span data-stu-id="c4e71-129">The frame that contains the catch handler.</span></span>|<span data-ttu-id="c4e71-130">Смещение промежуточного языка MSIL Microsoft начале обработчика catch.</span><span class="sxs-lookup"><span data-stu-id="c4e71-130">The Microsoft intermediate language (MSIL) offset of the beginning of the catch handler.</span></span>|  
|<span data-ttu-id="c4e71-131">DEBUG_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="c4e71-131">DEBUG_EXCEPTION_UNHANDLED</span></span>|<span data-ttu-id="c4e71-132">NULL</span><span class="sxs-lookup"><span data-stu-id="c4e71-132">NULL</span></span>|<span data-ttu-id="c4e71-133">Не определено.</span><span class="sxs-lookup"><span data-stu-id="c4e71-133">Undefined.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c4e71-134">Требования</span><span class="sxs-lookup"><span data-stu-id="c4e71-134">Requirements</span></span>  
 <span data-ttu-id="c4e71-135">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4e71-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4e71-136">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4e71-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4e71-137">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4e71-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4e71-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4e71-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4e71-139">См. также</span><span class="sxs-lookup"><span data-stu-id="c4e71-139">See also</span></span>

- [<span data-ttu-id="c4e71-140">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="c4e71-140">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="c4e71-141">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="c4e71-141">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
