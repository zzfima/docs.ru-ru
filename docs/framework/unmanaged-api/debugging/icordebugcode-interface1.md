---
title: "ICorDebugCode интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode
helpviewer_keywords: ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7813381c345db3d14318dddd93df1b491b46549e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcode-interface1"></a>ICorDebugCode интерфейс1
Представляет сегмент кода на языке MSIL или сегмент машинного кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|Создает точку останова с указанным смещением.|  
|[GetAddress-метод](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|Получает относительный виртуальный адрес (RVA) сегмента кода, это `ICorDebugCode` представляет.|  
|[Метод GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|Возвращает весь код для заданной функции, отформатированной для дизассемблирования. Этот метод является устаревшим; Используйте [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) вместо него.|  
|[Метод GetEnCRemapSequencePoints](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|Не реализовано.|  
|[Метод GetFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|Возвращает «ICorDebugFunction», связанный с этим `ICorDebugCode`.|  
|[Метод GetILToNativeMapping](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|Возвращает массив экземпляров «COR_DEBUG_IL_TO_NATIVE_MAP», представляющих сопоставления из смещений MSIL в собственные смещения.|  
|[GetSize-метод](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|Возвращает размер в байтах двоичного кода, представленный этим `ICorDebugCode`.|  
|[Метод GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|Возвращает число от единицы, определяющее версию кода этим `ICorDebugCode` представляет.|  
|[Метод IsIL](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|Возвращает значение, указывающее, является ли это `ICorDebugCode` скомпилированные в MSIL.|  
  
## <a name="remarks"></a>Примечания  
 `ICorDebugCode`может представлять MSIL или машинный код. Объект «ICorDebugFunction», который представляет код MSIL может иметь ноль или один `ICorDebugCode` связанные с ним объекты. Объект «ICorDebugFunction», который представляет машинный код может иметь любое количество `ICorDebugCode` связанные с ним объекты.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
    
 [Интерфейс ICorDebugCode3](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
