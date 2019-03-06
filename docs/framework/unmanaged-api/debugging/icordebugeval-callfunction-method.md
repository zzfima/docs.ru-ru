---
title: Метод ICorDebugEval::CallFunction
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 66e51dc15f7d44ede26634571fa04c58e9735694
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364155"
---
# <a name="icordebugevalcallfunction-method"></a>Метод ICorDebugEval::CallFunction

Настраивает вызов указанной функции.

Этот метод является устаревшим в .NET Framework версии 2.0. Используйте [ICorDebugEval2::CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) вместо этого.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT CallFunction (
    [in] ICorDebugFunction  *pFunction,
    [in] ULONG32            nArgs,
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]
);
```

## <a name="parameters"></a>Параметры

`pFunction`\
[in] Указатель на объект ICorDebugFunction, который указывает функция, которая вызывается.

`nArgs`\
[in] Число аргументов для функции.

`ppArgs`\
[in] Массив указателей, каждый из которых указывает на объект ICorDebugValue, который указывает аргумент, передаваемый в функцию.

## <a name="remarks"></a>Примечания

Если функция является виртуальной, `CallFunction` выполнит виртуальной диспетчеризации. Если функция находится в другом домене приложения, будет выполнен переход, до тех пор, пока все аргументы имеют также в этом домене приложения.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок.** CorDebug.idl, CorDebug.h

**Библиотека:** CorGuids.lib

**Версии платформы .NET framework:** 1.1, 1.0

## <a name="see-also"></a>См. также

- [Метод CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md)