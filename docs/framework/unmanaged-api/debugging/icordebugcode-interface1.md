---
title: Интерфейс ICorDebugCode
ms.date: 03/30/2017
api_name:
- ICorDebugCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode
helpviewer_keywords:
- ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type:
- apiref
ms.openlocfilehash: 8cb95fad4394e2ce9b7f922e720071d8c4434edb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125592"
---
# <a name="icordebugcode-interface"></a>Интерфейс ICorDebugCode

Представляет сегмент кода на языке MSIL или сегмент машинного кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|Создает точку останова по указанному смещению.|  
|[Метод GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|Возвращает относительный виртуальный адрес (RVA) сегмента кода, который представляет этот `ICorDebugCode`.|  
|[Метод GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|Возвращает весь код для указанной функции, отформатированный для дизассемблирования. Этот метод не рекомендуется к использованию. Вместо этого используйте [ICorDebugCode2:: жеткодечункс](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) .|  
|[Метод GetEnCRemapSequencePoints](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|Не реализовано.|  
|[Метод GetFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|Возвращает "ICorDebugFunction", связанный с этим `ICorDebugCode`.|  
|[Метод GetILToNativeMapping](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|Возвращает массив экземпляров "COR_DEBUG_IL_TO_NATIVE_MAP", представляющих сопоставления от смещений MSIL до собственных смещений.|  
|[Метод GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|Возвращает размер двоичного кода (в байтах), представленного этим `ICorDebugCode`.|  
|[Метод GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|Возвращает номер, отсчитываемый от единицы, определяющий версию кода, который представляет этот `ICorDebugCode`.|  
|[Метод IsIL](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|Возвращает значение, указывающее, компилируется ли этот `ICorDebugCode` в MSIL.|  
  
## <a name="remarks"></a>Заметки  
 `ICorDebugCode` может представлять MSIL или машинный код. Объект "ICorDebugFunction", представляющий код MSIL, может иметь либо ноль, либо один `ICorDebugCode` связанных с ним объектов. Объект "ICorDebugFunction", представляющий машинный код, может содержать любое количество `ICorDebugCode` объектов, связанных с ним.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugCode3](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
