---
title: Интерфейс IXCLRDataModule
ms.date: 01/16/2019
api.name:
- IXCLRDataModule Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule Interface
helpviewer.keywords:
- IXCLRDataModule Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 8757642db6c4375cf55d1f7288669c4c8a752a38
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790394"
---
# <a name="ixclrdatamodule-interface"></a>Интерфейс IXCLRDataModule

Предоставляет методы для запроса сведений о загруженном модуле.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Методы

| Метод                                                                                                                                | Описание                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [жетмесоддефинитионбитокен](ixclrdatamodule-getmethoddefinitionbytoken-method.md) | Возвращает определение метода, соответствующее заданному маркеру метаданных. |
| [Запрос](ixclrdatamodule-request-method.md)                                       | Запросы на заполнение буфера данными модуля.       |
| [жетверсионид](ixclrdatamodule-getversionid-method.md)                             | Возвращает идентификатор версии модуля.                                       |

## <a name="remarks"></a>Заметки

Этот интерфейс находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек. Однако это COM-интерфейс, производный от `IUnknown` с GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2`, который можно получить с помощью обычных механизмов COM.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также:

- [Отладка](index.md)
- [Интерфейсы отладки](debugging-interfaces.md)
