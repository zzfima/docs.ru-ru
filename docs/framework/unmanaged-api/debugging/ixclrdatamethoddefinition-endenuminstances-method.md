---
title: 'Метод Иксклрдатамесоддефинитион:: Енденуминстанцес'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EndEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 605a4244d20ef6c0b7af3c2b26b65ff2a63fa9dd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790450"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a>Метод Иксклрдатамесоддефинитион:: Енденуминстанцес

Освобождает ресурсы, используемые внутренними итераторами, используемыми при перечислении экземпляров.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a>Параметры

`handle`\
заполняет Маркер для перечисления экземпляров.

## <a name="remarks"></a>Заметки

Предоставленный метод является частью `IXCLRDataMethodDefinition` интерфейса и соответствует пятой области таблицы виртуального метода.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также:

- [Отладка](index.md)
- [Интерфейс Иксклрдатамесоддефинитион](ixclrdatamethoddefinition-interface.md)
