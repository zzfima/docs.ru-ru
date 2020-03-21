---
title: Структура DacpModuleData
ms.date: 02/01/2019
api.name:
- DacpModuleData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpModuleData Structure
helpviewer.keywords:
- DacpModuleData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: c24bdce64eb7e208bf3830940d7beab1ebf92e78
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179188"
---
# <a name="dacpmoduledata-structure"></a>Структура DacpModuleData

Определяет транспортный буфер для информации о времени выполнения модуля.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File;
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a>Члены

| Участник    | Описание                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | Адрес объекта модуля.                                           |
| `File`    | Указатель на портативный исполняемый (PE) файл.                       |
| `ilBase`  | Адрес базы загруженного изображения.                                 |
| `payLoad` | Буфер полезной нагрузки для дополнительной информации о модуле, используемой временем выполнения. |

## <a name="remarks"></a>Remarks

Эта структура живет в времени выполнения и не подвергается воздействию каких-либо заголовков или файлов библиотек. Чтобы использовать его, определите структуру, указанную выше.

## <a name="requirements"></a>Требования
**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок:** Ни один  
**Библиотека:** Ни один  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также раздел

- [Отладки](index.md)
- [Структуры отладки](debugging-structures.md)
