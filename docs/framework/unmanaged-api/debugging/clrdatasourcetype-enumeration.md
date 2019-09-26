---
title: Перечисление Клрдатасаурцетипе
ms.date: 01/16/2019
api.name:
- CLRDataSourceType Enumeration
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDataSourceType Enumeration
helpviewer.keywords:
- CLRDataSourceType Enumeration [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7ace405e2624f15b1cdb6d383222ae87c93289bb
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274097"
---
# <a name="clrdatasourcetype-enumeration"></a>Перечисление Клрдатасаурцетипе

Предоставляет значения, используемые структурой CLRDATA_IL_ADDRESS_MAP.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a>Участники

| Член                        | Описание                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | Указание того, что ничего еще не применимо |

## <a name="remarks"></a>Примечания

Это перечисление находится внутри среды выполнения и не предоставляется через заголовки или файлы библиотек. Чтобы использовать его, определите перечисление, как определено выше в коде. Это также называется псевдонимом `CLRDATA_ENUM` , как упоминалось в [общих типах данных](../common-data-types-unmanaged-api-reference.md).

## <a name="requirements"></a>Требования

**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок.** Отсутствуют  
**Библиотечная** Отсутствуют  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Отладка](index.md)
- [Перечисления отладки](debugging-enumerations.md)
