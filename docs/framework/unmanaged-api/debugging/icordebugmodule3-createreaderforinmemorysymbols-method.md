---
title: "Метод ICorDebugModule3::CreateReaderForInMemorySymbols"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule3.CreateReaderForInMemorySymbols
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugModule3::CreateReaderForInMemorySymbols
helpviewer_keywords:
- CreateReaderForInMemorySymbols method, ICorDebugModule3 interface [.NET Framework debugging]
- ICorDebugModule3::CreateReaderForInMemorySymbols method [.NET Framework debugging]
ms.assetid: af317171-d66d-4114-89eb-063554c74940
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fbab155e783d3b5e40da466fef56633317c67042
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a>Метод ICorDebugModule3::CreateReaderForInMemorySymbols
Создает средство чтения символов отладки для динамического модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
#### <a name="parameters"></a>Параметры  
 riid  
 [in] Идентификатор IID интерфейса COM для возврата. Как правило, это [ISymUnmanagedReader-интерфейс](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).  
  
 ppObj  
 [out] Указатель на указатель на возвращенный интерфейс.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 Успешно создан средства чтения.  
  
 CORDBG_E_MODULE_LOADED_FROM_DISK  
 Модуль не является модулем в памяти или динамическим.  
  
 CORDBG_E_SYMBOLS_NOT_AVAILABLE  
 Символы, не были предоставлены приложением или еще не доступны.  
  
 E_FAIL (или другие коды возврата E_)  
 Не удалось создать средство чтения.  
  
## <a name="remarks"></a>Примечания  
 Этот метод может также быть используется, чтобы создать объект средства чтения символов для модулей (не являющегося динамическим) в памяти, но только после символов будут доступны (обозначается [метод UpdateModuleSymbols](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) обратного вызова).  
  
 Этот метод возвращает новый экземпляр средства чтения при каждом вызове (как [CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6)). Таким образом, отладчик должен кэшировать результат и запросить новый экземпляр только в том случае, если изменились базовые данные (то есть, когда [метод LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) обратного вызова).  
  
 Динамические модули не могут содержать любые символы, которые, только после загрузки первый тип (как указано в [метод LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) обратного вызова).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** 4.5, 4, 3.5 с пакетом обновления 1  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugRemoteTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [ICorDebug-интерфейс](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
