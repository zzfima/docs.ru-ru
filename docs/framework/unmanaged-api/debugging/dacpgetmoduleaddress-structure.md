---
title: Структура DacpGetModuleAddress
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress Structure
helpviewer.keywords:
- DacpGetModuleAddress Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: ca9ce04e9a4770d46f88e10785f4dafd044c9212
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416534"
---
# <a name="dacpgetmoduleaddress-structure"></a>Структура DacpGetModuleAddress

Определяет контейнер для запроса адрес модуля.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a>Участники

| Член      | Описание                |
| ----------- | -------------------------- |
| `ModulePtr` | Указатель на модуль. |

## <a name="methods"></a>Методы

| Метод                                                                                               | Описание:                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [Запрос](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-request-method.md) | Выполняет запрос для заполнения структуры из структуры данной среды выполнения. |

## <a name="remarks"></a>Примечания

Эта структура находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек. Чтобы использовать его, определить структуру как указано выше, где `CLRDATA_ADDRESS` является 64-разрядное целое число без знака.

## <a name="requirements"></a>Требования
**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок.** Нет  
**Библиотека:** Нет  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
