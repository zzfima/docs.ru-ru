---
title: Структура CLRDATA_IL_ADDRESS_MAP
ms.date: 01/16/2019
api.name:
- CLRDATA_IL_ADDRESS_MAP Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure
helpviewer.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: e680a7a0dc3209d1988f6c84be0864572a74b3a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179379"
---
# <a name="clrdata_il_address_map-structure"></a>Структура CLRDATA_IL_ADDRESS_MAP

Определяет ИЛ для решения картографирования.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a>Члены

| Участник         | Описание                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | IL смещение для содержащегося диапазона адресов              |
| `startAddress` | Стартовый адрес диапазона.                        |
| `endAddress`   | Конечный адрес диапазона.                          |
| `type`         | Тип данных. Это значение в настоящее время не используется |

## <a name="remarks"></a>Remarks

Эта структура живет в времени выполнения и не подвергается воздействию каких-либо заголовков или файлов библиотек. Чтобы использовать его, определите структуру, указанную выше, где `CLRDATA_ADDRESS` находится 64-битный неподписанный целый ряд.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** Ни один  
**Библиотека:** Нет **рамочных версий .NET:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также раздел

- [Перечисление CLRDataSourceType](clrdatasourcetype-enumeration.md)
- [Отладки](index.md)
- [Структуры отладки](debugging-structures.md)
