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
ms.openlocfilehash: 76f7b53f800bc8c5c23f49a0781287a38bf8c959
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421520"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="9f841-102">Метод ICorDebugModule3::CreateReaderForInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="9f841-102">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>
<span data-ttu-id="9f841-103">Создает средство чтения символов отладки для динамического модуля.</span><span class="sxs-lookup"><span data-stu-id="9f841-103">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f841-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f841-104">Syntax</span></span>  
  
```  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9f841-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9f841-105">Parameters</span></span>  
 <span data-ttu-id="9f841-106">riid</span><span class="sxs-lookup"><span data-stu-id="9f841-106">riid</span></span>  
 <span data-ttu-id="9f841-107">[in] Идентификатор IID интерфейса COM для возврата.</span><span class="sxs-lookup"><span data-stu-id="9f841-107">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="9f841-108">Как правило, это [ISymUnmanagedReader-интерфейс](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9f841-108">Typically, this is an [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="9f841-109">ppObj</span><span class="sxs-lookup"><span data-stu-id="9f841-109">ppObj</span></span>  
 <span data-ttu-id="9f841-110">[out] Указатель на указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="9f841-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f841-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9f841-111">Return Value</span></span>  
 <span data-ttu-id="9f841-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="9f841-112">S_OK</span></span>  
 <span data-ttu-id="9f841-113">Успешно создан средства чтения.</span><span class="sxs-lookup"><span data-stu-id="9f841-113">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="9f841-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="9f841-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="9f841-115">Модуль не является модулем в памяти или динамическим.</span><span class="sxs-lookup"><span data-stu-id="9f841-115">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="9f841-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9f841-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="9f841-117">Символы, не были предоставлены приложением или еще не доступны.</span><span class="sxs-lookup"><span data-stu-id="9f841-117">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="9f841-118">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="9f841-118">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="9f841-119">Не удалось создать средство чтения.</span><span class="sxs-lookup"><span data-stu-id="9f841-119">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f841-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="9f841-120">Remarks</span></span>  
 <span data-ttu-id="9f841-121">Этот метод может также быть используется, чтобы создать объект средства чтения символов для модулей (не являющегося динамическим) в памяти, но только после символов будут доступны (обозначается [метод UpdateModuleSymbols](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) обратного вызова).</span><span class="sxs-lookup"><span data-stu-id="9f841-121">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="9f841-122">Этот метод возвращает новый экземпляр средства чтения при каждом вызове (как [CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6)).</span><span class="sxs-lookup"><span data-stu-id="9f841-122">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6)).</span></span> <span data-ttu-id="9f841-123">Таким образом, отладчик должен кэшировать результат и запросить новый экземпляр только в том случае, если изменились базовые данные (то есть, когда [метод LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) обратного вызова).</span><span class="sxs-lookup"><span data-stu-id="9f841-123">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="9f841-124">Динамические модули не могут содержать любые символы, которые, только после загрузки первый тип (как указано в [метод LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) обратного вызова).</span><span class="sxs-lookup"><span data-stu-id="9f841-124">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f841-125">Требования</span><span class="sxs-lookup"><span data-stu-id="9f841-125">Requirements</span></span>  
 <span data-ttu-id="9f841-126">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f841-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f841-127">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f841-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f841-128">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f841-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f841-129">**Версии платформы .NET framework:** 4.5, 4, 3.5 с пакетом обновления 1</span><span class="sxs-lookup"><span data-stu-id="9f841-129">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f841-130">См. также</span><span class="sxs-lookup"><span data-stu-id="9f841-130">See Also</span></span>  
 [<span data-ttu-id="9f841-131">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="9f841-131">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="9f841-132">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="9f841-132">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="9f841-133">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9f841-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
