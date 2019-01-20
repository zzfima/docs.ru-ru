---
title: Перечисление CLRDataSourceType
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
ms.openlocfilehash: 36651de5053e994103f79c9021e8e18e126f91fa
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416517"
---
# <a name="clrdatasourcetype-enumeration"></a>Перечисление CLRDataSourceType

Предоставляет значения, которые используются в структуре CLRDATA_IL_ADDRESS_MAP.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a>Участники

| Член                        | Описание                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | Чтобы указать, что ничего применяется |

## <a name="remarks"></a>Примечания

Это перечисление находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек. Чтобы использовать его, определите перечисление, как указано выше, в коде. Это также псевдонимом `CLRDATA_ENUM` как уже упоминалось в [общие типы данных](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок.** Нет  
**Библиотека:** Нет  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
