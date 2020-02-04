---
title: Интерфейс ISOSDacInterface
ms.date: 02/01/2019
api.name:
- ISOSDacInterface Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface Interface
helpviewer.keywords:
- ISOSDacInterface Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 94349a3f7b18c8ce29bb3a71cb9d10ee4eac8036
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790479"
---
# <a name="isosdacinterface-interface"></a>Интерфейс ISOSDacInterface

Предоставляет вспомогательные методы для доступа к данным из `SOS`.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Методы

| Метод                                                                                                               | Описание                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [жетмесоддескдата](isosdacinterface-getmethoddescdata-method.md) | Возвращает данные для заданного указателя MethodDesc. |
| [жетмесоддескптрфромип](isosdacinterface-getmethoddescptrfromip-method.md) | Получает указатель MethodDesc, соответствующий методу, содержащему указанный адрес собственной инструкции. |
| [жетмодуледата](isosdacinterface-getmoduledata-method.md)| Извлекает данные, соответствующие модулю, загруженному по указанному адресу. |

## <a name="remarks"></a>Заметки

Этот интерфейс находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек. Однако это COM-интерфейс, производный от `IUnknown` с GUID `436f00f2-b42a-4b9f-870c-e73db66ae930`, который можно получить с помощью обычных механизмов COM.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>См. также:

- [Отладка](index.md)
- [Интерфейсы отладки](debugging-interfaces.md)
