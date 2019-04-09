---
title: Метод ICorDebugModule3::CreateReaderForInMemorySymbols
ms.date: 03/30/2017
api_name:
- ICorDebugModule3.CreateReaderForInMemorySymbols
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3::CreateReaderForInMemorySymbols
helpviewer_keywords:
- CreateReaderForInMemorySymbols method, ICorDebugModule3 interface [.NET Framework debugging]
- ICorDebugModule3::CreateReaderForInMemorySymbols method [.NET Framework debugging]
ms.assetid: af317171-d66d-4114-89eb-063554c74940
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ccfe83707b6354c42a4c3c81e911918b2ea79ec4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108918"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="92a0c-102">Метод ICorDebugModule3::CreateReaderForInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="92a0c-102">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>
<span data-ttu-id="92a0c-103">Создает средство чтения символов отладки для динамического модуля.</span><span class="sxs-lookup"><span data-stu-id="92a0c-103">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92a0c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92a0c-104">Syntax</span></span>  
  
```  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
## <a name="parameters"></a><span data-ttu-id="92a0c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="92a0c-105">Parameters</span></span>  
 <span data-ttu-id="92a0c-106">riid</span><span class="sxs-lookup"><span data-stu-id="92a0c-106">riid</span></span>  
 <span data-ttu-id="92a0c-107">[in] Идентификатор IID интерфейса COM для возврата.</span><span class="sxs-lookup"><span data-stu-id="92a0c-107">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="92a0c-108">Как правило, это [интерфейс ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span><span class="sxs-lookup"><span data-stu-id="92a0c-108">Typically, this is an [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="92a0c-109">ppObj</span><span class="sxs-lookup"><span data-stu-id="92a0c-109">ppObj</span></span>  
 <span data-ttu-id="92a0c-110">[out] Указатель на указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="92a0c-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92a0c-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="92a0c-111">Return Value</span></span>  
 <span data-ttu-id="92a0c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="92a0c-112">S_OK</span></span>  
 <span data-ttu-id="92a0c-113">Успешно создано средство чтения.</span><span class="sxs-lookup"><span data-stu-id="92a0c-113">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="92a0c-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="92a0c-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="92a0c-115">Модуль не является модулем в памяти или динамическим.</span><span class="sxs-lookup"><span data-stu-id="92a0c-115">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="92a0c-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="92a0c-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="92a0c-117">Символы не были предоставлены приложением или еще не доступны.</span><span class="sxs-lookup"><span data-stu-id="92a0c-117">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="92a0c-118">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="92a0c-118">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="92a0c-119">Не удалось создать средство чтения.</span><span class="sxs-lookup"><span data-stu-id="92a0c-119">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92a0c-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="92a0c-120">Remarks</span></span>  
 <span data-ttu-id="92a0c-121">Этот метод может также быть используется, чтобы создать объект средства чтения символов для модулей в памяти (нединамичного), но только после символы будут доступны (обозначается [метод UpdateModuleSymbols](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) обратного вызова).</span><span class="sxs-lookup"><span data-stu-id="92a0c-121">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="92a0c-122">Этот метод возвращает новый экземпляр средства чтения, каждый раз при его вызове (как [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span><span class="sxs-lookup"><span data-stu-id="92a0c-122">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span></span> <span data-ttu-id="92a0c-123">Таким образом, отладчик должен кэш-памяти результат и запрашивать новый экземпляр только при изменении базовых данных (то есть, в том случае, когда [метод LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) обратного вызова).</span><span class="sxs-lookup"><span data-stu-id="92a0c-123">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="92a0c-124">Динамические модули не могут содержать любые символы, которые, только после загрузки первый тип (как указано в [метод LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) обратного вызова).</span><span class="sxs-lookup"><span data-stu-id="92a0c-124">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92a0c-125">Требования</span><span class="sxs-lookup"><span data-stu-id="92a0c-125">Requirements</span></span>  
 <span data-ttu-id="92a0c-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92a0c-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92a0c-127">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92a0c-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92a0c-128">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92a0c-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92a0c-129">**Версии платформы .NET framework:** 4.5, 4, 3.5 С ПАКЕТОМ ОБНОВЛЕНИЯ 1</span><span class="sxs-lookup"><span data-stu-id="92a0c-129">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92a0c-130">См. также</span><span class="sxs-lookup"><span data-stu-id="92a0c-130">See also</span></span>

- [<span data-ttu-id="92a0c-131">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="92a0c-131">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="92a0c-132">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="92a0c-132">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="92a0c-133">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="92a0c-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
