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
ms.openlocfilehash: 4b24b3dfe6a931866acd7eba966811071ff39ea5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788930"
---
# <a name="icordebugcode-interface"></a>Интерфейс ICorDebugCode

Представляет сегмент кода на языке MSIL или сегмент машинного кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateBreakpoint](icordebugcode-createbreakpoint-method.md)|Создает точку останова по указанному смещению.|  
|[Метод GetAddress](icordebugcode-getaddress-method.md)|Возвращает относительный виртуальный адрес (RVA) сегмента кода, который представляет этот `ICorDebugCode`.|  
|[Метод GetCode](icordebugcode-getcode-method.md)|Возвращает весь код для указанной функции, отформатированный для дизассемблирования. Этот метод не рекомендуется к использованию. Вместо этого используйте [ICorDebugCode2:: жеткодечункс](icordebugcode2-getcodechunks-method.md) .|  
|[Метод GetEnCRemapSequencePoints](icordebugcode-getencremapsequencepoints-method.md)|Не реализовано.|  
|[Метод GetFunction](icordebugcode-getfunction-method.md)|Возвращает "ICorDebugFunction", связанный с этим `ICorDebugCode`.|  
|[Метод GetILToNativeMapping](icordebugcode-getiltonativemapping-method.md)|Возвращает массив экземпляров "COR_DEBUG_IL_TO_NATIVE_MAP", которые представляют сопоставления от смещений MSIL до собственных смещений.|  
|[Метод GetSize](icordebugcode-getsize-method.md)|Возвращает размер двоичного кода (в байтах), представленного этим `ICorDebugCode`.|  
|[Метод GetVersionNumber](icordebugcode-getversionnumber-method.md)|Возвращает номер, отсчитываемый от единицы, определяющий версию кода, который представляет этот `ICorDebugCode`.|  
|[Метод IsIL](icordebugcode-isil-method.md)|Возвращает значение, указывающее, компилируется ли этот `ICorDebugCode` в MSIL.|  
  
## <a name="remarks"></a>Заметки  
 `ICorDebugCode` может представлять MSIL или машинный код. Объект "ICorDebugFunction", представляющий код MSIL, может иметь либо ноль, либо один `ICorDebugCode` связанных с ним объектов. Объект "ICorDebugFunction", представляющий машинный код, может содержать любое количество `ICorDebugCode` объектов, связанных с ним.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugCode3](icordebugcode3-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
