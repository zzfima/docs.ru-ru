---
title: 'Метод Иксклрдатамесоддефинитион:: Енуминстанце'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EnumInstance Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: b6393d7fa4853c230203521e665bbe89d7b228e2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790443"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a>Метод Иксклрдатамесоддефинитион:: Енуминстанце

Перечисляет экземпляры этого определения метода.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a>Параметры

`handle`\
[вход, выход] Маркер для перечисления экземпляров.

`instance`\
заполняет Перечислимый экземпляр.

## <a name="remarks"></a>Заметки

Предоставленный метод является частью `IXCLRDataMethodDefinition` интерфейса и соответствует четвертому слоту таблицы виртуального метода.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также:

- [Перечисление Клрдатасаурцетипе](clrdatasourcetype-enumeration.md)
- [Отладка](index.md)
- [Интерфейс Иксклрдатамесоддефинитион](ixclrdatamethoddefinition-interface.md)
- [Интерфейс Иксклрдатамесодинстанце](ixclrdatamethodinstance-interface.md)
