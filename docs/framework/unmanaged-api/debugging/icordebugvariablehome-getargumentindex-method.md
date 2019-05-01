---
title: Метод ICorDebugVariableHome::GetArgumentIndex
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2457dff3063e47f1fb9d040caac1bc08441e1739
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986795"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a>Метод ICorDebugVariableHome::GetArgumentIndex

Получает индекс аргумента функции.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a>Параметры

`pArgumentIndex`\
[out] Указатель на индекс аргумента.

## <a name="return-value"></a>Возвращаемое значение

Метод возвращает следующие значения.

|Значение|Описание|
|-----------|-----------------|
|`S_OK`|Вызов метода вернул индекс допустимый аргумент.|
|`E_FAIL`|Текущий [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) экземпляр представляет локальную переменную.|

## <a name="remarks"></a>Примечания

Аргумент индекса можно использовать для получения метаданных для этого аргумента.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок.** CorDebug.idl, CorDebug.h

**Библиотека:** CorGuids.lib

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
