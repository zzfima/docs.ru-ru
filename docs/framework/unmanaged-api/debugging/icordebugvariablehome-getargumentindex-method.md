---
title: 'Метод ICorDebugVariableHome:: Жетаргументиндекс'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetArgumentIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type:
- apiref
ms.openlocfilehash: 12d4e63480f03bfad613f30362ddaeaf12b57a88
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791053"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a>Метод ICorDebugVariableHome:: Жетаргументиндекс

Возвращает индекс аргумента функции.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a>Параметры

`pArgumentIndex`\
заполняет Указатель на индекс аргумента.

## <a name="return-value"></a>Возвращаемое значение

Метод возвращает следующие значения.

|{2&gt;Value&lt;2}|Описание|
|-----------|-----------------|
|`S_OK`|Вызов метода вернул допустимый индекс аргумента.|
|`E_FAIL`|Текущий экземпляр [ICorDebugVariableHome](icordebugvariablehome-interface.md) представляет локальную переменную.|

## <a name="remarks"></a>Заметки

Индекс аргумента можно использовать для получения метаданных для этого аргумента.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок:** CorDebug.idl, CorDebug.h

**Библиотека:** CorGuids.lib

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]

## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugVariableHome](icordebugvariablehome-interface.md)
