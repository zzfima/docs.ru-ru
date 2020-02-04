---
title: Интерфейс IXCLRDataProcess
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess Interface
helpviewer.keywords:
- IXCLRDataProcess Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: a5d707d61513b030e5968af28db3c2a606e4419b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790376"
---
# <a name="ixclrdataprocess-interface"></a>Интерфейс IXCLRDataProcess

Предоставляет методы для запроса сведений о процессе.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Методы

| Метод                                                                                                                                               | Описание                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [жетаппдомаинбюникуеид](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | Возвращает `AppDomain` в процессе по его уникальному идентификатору.                                              |
| [стартенуммодулес](ixclrdataprocess-startenummodules-method.md)                                   | Предоставляет описатель для перечисления модулей процесса.                                        |
| [енуммодуле](ixclrdataprocess-enummodule-method.md)                                               | Перечисляет модули этого процесса.                                                         |
| [енденуммодулес](ixclrdataprocess-endenummodules-method.md)                                       | Освобождает ресурсы, используемые внутренними итераторами, используемыми при перечислении модулей.               |
| [стартенуммесодинстанцесбяддресс](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | Предоставляет описатель для перечисления экземпляров методов `AppDomain`, начиная с заданного адреса. |
| [енуммесодинстанцебяддресс](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | Перечисляет экземпляры методов этого процесса, начиная с смещения адреса.                  |
| [енденуммесодинстанцесбяддресс](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | Освобождает ресурсы, используемые внутренними итераторами, используемыми при перечислении экземпляров.             |

## <a name="remarks"></a>Заметки

Этот интерфейс находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек. Однако это COM-интерфейс, производный от `IUnknown` с GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7`, который можно получить с помощью обычных механизмов COM.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).   
**Заголовок:** None  
**Библиотека:** None  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также:

- [Отладка](index.md)
- [Интерфейсы отладки](debugging-interfaces.md)
