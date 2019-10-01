---
title: Метод ICorDebugCodeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 076b5d628dfe83decdbbe2f5e74c50e08262c580
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700687"
---
# <a name="icordebugcodeenumnext-method"></a>Метод ICorDebugCodeEnum::Next

Возвращает указанное число экземпляров ICorDebugCode из перечисления, начиная с текущей позиции.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT Next (
    [in] ULONG  celt,
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorDebugCode *values[],
    [out] ULONG *pceltFetched
);
```

## <a name="parameters"></a>Параметры

 `celt`  
 окне Число извлекаемых экземпляров `ICorDebugCode`.

 `values`  
 заполняет Массив указателей, каждый из которых указывает на объект `ICorDebugCode`.

 `pceltFetched`  
 заполняет Указатель на число фактически возвращенных экземпляров `ICorDebugCode`. Это значение может быть равно null, если `celt` является одним.

## <a name="requirements"></a>Требования

 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).

 **Заголовок.** CorDebug. idl, CorDebug. h

 **Библиотечная** Коргуидс. lib

 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
 
