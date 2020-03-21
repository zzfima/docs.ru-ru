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
ms.openlocfilehash: e7e53615e38d0ab76f9e7c0a753be3c13780057d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178376"
---
# <a name="ixclrdataprocess-interface"></a>Интерфейс IXCLRDataProcess

Предоставляет методы запроса информации о процессе.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Методы

| Метод                                                                                                                                               | Описание                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [GetAppDomainByUniqueId](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | Получает `AppDomain` в процессе своим уникальным идентификатором.                                              |
| [StartEnumModules](ixclrdataprocess-startenummodules-method.md)                                   | Обеспечивает ручку для перечисления модулей процесса.                                        |
| [EnumModule](ixclrdataprocess-enummodule-method.md)                                               | Перечисляет модули этого процесса.                                                         |
| [EndEnumModules](ixclrdataprocess-endenummodules-method.md)                                       | Выпускает ресурсы, используемые внутренними итераторами, используемыми при перечислении модулей.               |
| [StartEnumMethodInstancesByAddress](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | Обеспечивает ручку для перечисления экземпляров `AppDomain` метода, начиная с заданного адреса. |
| [EnumMethodInstanceByAddress](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | Перечисляет экземпляры метода этого процесса, начиная с смещения адреса.                  |
| [EndEnumMethodInstancesByAddress](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | Выпускает ресурсы, используемые внутренними итераторами, используемыми во время перечисления экземпляра.             |

## <a name="remarks"></a>Remarks

Этот интерфейс живет внутри времени выполнения и не подвергается воздействию каких-либо заголовков или файлов библиотек. Тем не менее, это интерфейс COM, который вытекает из `IUnknown` с GUID, `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` которые могут быть получены с помощью обычных механизмов COM.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).
**Заголовок:** Ни один  
**Библиотека:** Ни один  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также раздел

- [Отладки](index.md)
- [Интерфейсы отладки](debugging-interfaces.md)
