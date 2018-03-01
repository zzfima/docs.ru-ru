---
title: "Метод ICorDebugCode3::GetReturnValueLiveOffset"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- cpp
api_name:
- ICorDebugCode3.GetReturnValueLiveOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5d10d298a031e7146eaf6cf7988538e6f7020136
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a>Метод ICorDebugCode3::GetReturnValueLiveOffset
Для заданного смещения IL возвращает собственные смещения, где разместить точку останова, чтобы отладчик можно получить возвращаемое значение из функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,   
    [out] ULONG32 *pFetched,   
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ILoffset`  
 Смещение на промежуточном Языке. Он должен быть место вызова функции или функции вызов завершится ошибкой.  
  
 `bufferSize`  
 Число байтов, доступных для хранения `pOffsets`.  
  
 `pFetched`  
 Указатель на число фактически извлеченных смещений. Обычно его значение равно 1, но одной инструкции IL можно сопоставить с несколькими `CALL` инструкции ассемблера.  
  
 `pOffsets`  
 Массив из машинного кода. Как правило `pOffsets` содержит один смещение, несмотря на то, что можно сопоставить несколько карты к нескольким одной инструкции IL `CALL` инструкции ассемблера.  
  
## <a name="remarks"></a>Примечания  
 Этот метод используется вместе с [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) метод для получения возвращаемого значения метода, который возвращает ссылочный тип. Передача IL смещение к место вызова функции в этот метод возвращает один или несколько собственные смещения. Затем отладчик можно установить точки останова на этих смещениях машинного кода в функцию. Если отладчик обнаруживает одной из точек останова, затем можно передать одинаковое смещение IL, который передан в этот метод, чтобы [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) метод для получения возвращаемого значения. Отладчик должен выполнить очистку все точки останова, которые оно задано.  
  
> [!WARNING]
>  `ICorDebugCode3::GetReturnValueLiveOffset` И [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) методы позволяют получить сведения о возвращаемых значениях только для ссылочных типов. Получение сведений о возвращаемое значение от типов значений (то есть, все типы, производные от <xref:System.ValueType>) не поддерживается.  
  
 Функция возвращает `HRESULT` значений, приведенных в следующей таблице.  
  
|Значение `HRESULT`|Описание:|  
|---------------------|-----------------|  
|`S_OK`|Выполнено.|  
|`CORDBG_E_INVALID_OPCODE`|Данного сайта смещении IL не инструкцию вызова или возвращаемого функцией `void`.|  
|`CORDBG_E_UNSUPPORTED`|С указанным смещением IL-код — это правильный вызов, но тип возвращаемого значения не поддерживается для получения возвращаемого значения.|  
  
 `ICorDebugCode3::GetReturnValueLiveOffset` Метод доступен только для x86 86 и AMD64 систем.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Метод GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)  
 [Интерфейс ICorDebugCode3](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
