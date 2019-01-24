---
title: Интерфейс1 ICorDebugCode
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
ms.openlocfilehash: db2fe1e854069d9b5d566fc00420615e0c06b3d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575951"
---
# <a name="icordebugcode-interface1"></a>Интерфейс1 ICorDebugCode
Представляет сегмент кода на языке MSIL или сегмент машинного кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|Создает точку останова с указанным смещением.|  
|[Метод GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|Возвращает относительный виртуальный адрес (RVA) в фрагменте кода, это `ICorDebugCode` представляет.|  
|[Метод GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|Получает весь код для указанной функции, отформатированных для Дизассемблированный код. Этот метод является устаревшим; Используйте [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) вместо этого.|  
|[Метод GetEnCRemapSequencePoints](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|Не реализовано.|  
|[Метод GetFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|Возвращает «ICorDebugFunction», связанный с данным `ICorDebugCode`.|  
|[Метод GetILToNativeMapping](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|Возвращает массив экземпляров «COR_DEBUG_IL_TO_NATIVE_MAP», которые представляют сопоставление из смещений MSIL в собственные смещения.|  
|[Метод GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|Получает размер в байтах двоичного кода, представленного данным `ICorDebugCode`.|  
|[Метод GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|Возвращает число от единицы, которое определяет версию кода, `ICorDebugCode` представляет.|  
|[Метод IsIL](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|Получает значение, указывающее, является ли это `ICorDebugCode` компилируется в код MSIL.|  
  
## <a name="remarks"></a>Примечания  
 `ICorDebugCode` может представлять MSIL или машинный код. Объект «ICorDebugFunction», который представляет код MSIL может иметь ноль или один `ICorDebugCode` объекты, связанные с ним. Объект «ICorDebugFunction», который представляет машинный код может иметь любое количество `ICorDebugCode` объекты, связанные с ним.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugCode3](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
