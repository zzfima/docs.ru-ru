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
ms.openlocfilehash: 342739f6c71e9c576e557433dc6abd0adbf38c8c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43528847"
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
 [in] Идентификатор IID интерфейса COM для возврата. Как правило, это [интерфейс ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).  
  
 ppObj  
 [out] Указатель на указатель на возвращенный интерфейс.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 Успешно создано средство чтения.  
  
 CORDBG_E_MODULE_LOADED_FROM_DISK  
 Модуль не является модулем в памяти или динамическим.  
  
 CORDBG_E_SYMBOLS_NOT_AVAILABLE  
 Символы не были предоставлены приложением или еще не доступны.  
  
 E_FAIL (или другие коды возврата E_)  
 Не удалось создать средство чтения.  
  
## <a name="remarks"></a>Примечания  
 Этот метод может также быть используется, чтобы создать объект средства чтения символов для модулей в памяти (нединамичного), но только после символы будут доступны (обозначается [метод UpdateModuleSymbols](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) обратного вызова).  
  
 Этот метод возвращает новый экземпляр средства чтения, каждый раз при его вызове (как [CComPtrBase::CoCreateInstance](https://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6)). Таким образом, отладчик должен кэш-памяти результат и запрашивать новый экземпляр только при изменении базовых данных (то есть, в том случае, когда [метод LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) обратного вызова).  
  
 Динамические модули не могут содержать любые символы, которые, только после загрузки первый тип (как указано в [метод LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) обратного вызова).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** 4.5, 4, 3.5 с пакетом обновления 1  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugRemoteTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [Интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
