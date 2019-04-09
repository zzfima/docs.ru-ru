---
title: Метод ICorDebugCode3::GetReturnValueLiveOffset
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03ee275336d3ae71f63d82add694fe1308efbe8b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125941"
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a>Метод ICorDebugCode3::GetReturnValueLiveOffset
Для указанного смещения на промежуточном Языке получает смещения в машинном коде, где должны размещаться точку останова, чтобы отладчик мог получить возвращаемое значение из функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,   
    [out] ULONG32 *pFetched,   
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ILoffset`  
 Смещение на промежуточном Языке. Он должен находиться на сайт вызова функции или вызов функции завершится ошибкой.  
  
 `bufferSize`  
 Число байтов для хранения `pOffsets`.  
  
 `pFetched`  
 Указатель на количество фактически возвращенных смещений. Как правило, его значение равно 1, но одна инструкция IL может сопоставляться нескольким `CALL` инструкции ассемблера.  
  
 `pOffsets`  
 Массив смещений в машинном коде. Как правило `pOffsets` содержит одно смещение, несмотря на то, что одна инструкция IL может сопоставляться несколькими к нескольким `CALL` инструкции ассемблера.  
  
## <a name="remarks"></a>Примечания  
 Этот метод используется вместе с [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) способ получения возвращаемого значения метода, который возвращает ссылочный тип. Передача смещения на сайт вызова функции в этот метод IL возвращает один или несколько смещений в машинном коде. Отладчик может установить точки останова на этих естественных смещениях функции. Когда отладчик достигает одной из точек останова, затем можно передать то же смещение IL, которое было передано в этот метод, чтобы [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) способ получения возвращаемого значения. Затем он должен очистить все точки останова, он задан.  
  
> [!WARNING]
>  `ICorDebugCode3::GetReturnValueLiveOffset` И [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) методы позволяют получить сведения о возвращаемом значении только для ссылочных типов. Получение сведений о возвращаемое значение из типов значений (то есть всех типов, производных от <xref:System.ValueType>) не поддерживается.  
  
 Функция возвращает `HRESULT` значений, приведенных в следующей таблице.  
  
|`HRESULT` value|Описание|  
|---------------------|-----------------|  
|`S_OK`|Выполнено.|  
|`CORDBG_E_INVALID_OPCODE`|Заданное смещение сайта IL не является инструкцией вызова, или функция возвращает `void`.|  
|`CORDBG_E_UNSUPPORTED`|Заданное смещение IL является правильным вызовом, но возвращаемый тип не поддерживается для получения возвращаемого значения.|  
  
 `ICorDebugCode3::GetReturnValueLiveOffset` Метод доступен только на x86 и системах AMD64.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)
- [Интерфейс ICorDebugCode3](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
