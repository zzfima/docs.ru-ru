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
ms.openlocfilehash: 34d543dd76de05bdf55d8187cf192455d1387a9f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178944"
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a>Метод ICorDebugCode3::GetReturnValueLiveOffset
Для указанного смещения IL получается родная смещения, где должна быть размещена точка разрыва, чтобы отладчик мог получить значение возврата от функции.  
  
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
 IL смещения. Это должен быть сайт вызова функции или вызов функции не удастся.  
  
 `bufferSize`  
 Количество байтов, доступных для хранения. `pOffsets`  
  
 `pFetched`  
 Указатель на количество смещений фактически вернулся. Обычно его значение составляет 1, но одна инструкция IL может сопоставить с несколькими `CALL` инструкциями сборки.  
  
 `pOffsets`  
 Массив родных смещений. Как `pOffsets` правило, содержит одно смещение, хотя одна инструкция IL может сопоставить на нескольких картах несколько `CALL` инструкций сборки.  
  
## <a name="remarks"></a>Remarks  
 Этот метод используется вместе с методом [ICorDebugILFrame3::GetReturnValueILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) для получения значения возврата метода, возвращающему эталонный тип. Передача смещения IL на сайт вызова функции к этому методу возвращает один или несколько родных смещений. Затем отладчик может устанавливать точки разрыва на этих родных смещениях в функции. Когда отладчик попадает в одну из точек разрыва, вы можете передать тот же IL смещения, что вы перешли к этому методу [ICorDebugILFrame3:GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) метод, чтобы получить значение возврата. Затем отладчик должен очистить все установленные моменты разрыва.  
  
> [!WARNING]
> И `ICorDebugCode3::GetReturnValueLiveOffset` [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) методы позволяют получить информацию о значении возврата только для эталонных типов. Извлечение информации о значении возврата из типов <xref:System.ValueType>значений (т.е. все типы, которые вытекают из ) не поддерживается.  
  
 Функция возвращает `HRESULT` значения, указанные в следующей таблице.  
  
|Значение `HRESULT`|Описание|  
|---------------------|-----------------|  
|`S_OK`|Успешно.|  
|`CORDBG_E_INVALID_OPCODE`|Данный сайт смещения IL не является `void`инструкцией по вызову или возвращает функцию.|  
|`CORDBG_E_UNSUPPORTED`|Данное смещение IL является правильным вызовом, но тип возврата не поддерживается для получения значения возврата.|  
  
 Метод `ICorDebugCode3::GetReturnValueLiveOffset` доступен только на системах x86 и AMD64.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md)
- [Интерфейс ICorDebugCode3](icordebugcode3-interface.md)
