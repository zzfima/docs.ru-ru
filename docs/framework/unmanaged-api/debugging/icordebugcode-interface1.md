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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75cc8ea9d88dda42362f50b519864b1a78e1a64b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960793"
---
# <a name="icordebugcode-interface"></a>Интерфейс ICorDebugCode

Представляет сегмент кода на языке MSIL или сегмент машинного кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|Создает точку останова по указанному смещению.|  
|[Метод GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|Возвращает относительный виртуальный адрес (RVA) сегмента кода, который представляет `ICorDebugCode` этот объект.|  
|[Метод GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|Возвращает весь код для указанной функции, отформатированный для дизассемблирования. Этот метод не рекомендуется к использованию. Вместо этого используйте [ICorDebugCode2:: жеткодечункс](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) .|  
|[Метод GetEnCRemapSequencePoints](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|Не реализовано.|  
|[Метод GetFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|Возвращает "ICorDebugFunction", связанный с этим `ICorDebugCode`.|  
|[Метод GetILToNativeMapping](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|Возвращает массив экземпляров "COR_DEBUG_IL_TO_NATIVE_MAP", представляющих сопоставления от смещений MSIL до собственных смещений.|  
|[Метод GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|Возвращает размер двоичного кода, представленного этим `ICorDebugCode`объектом, в байтах.|  
|[Метод GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|Возвращает номер, отсчитываемый от единицы, определяющий версию кода, который представляет данный `ICorDebugCode` объект.|  
|[Метод IsIL](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|Возвращает значение, указывающее, компилируется `ICorDebugCode` ли это в MSIL.|  
  
## <a name="remarks"></a>Примечания  
 `ICorDebugCode`может представлять язык MSIL или машинный код. Объект "ICorDebugFunction", представляющий код MSIL, может быть связан с нулем или `ICorDebugCode` с одним объектом. Объект "ICorDebugFunction", представляющий машинный код, может иметь любое количество `ICorDebugCode` связанных с ним объектов.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugCode3](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
