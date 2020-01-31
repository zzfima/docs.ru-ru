---
title: Интерфейс IXCLRDataMethodInstance
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance Interface
helpviewer.keywords:
- IXCLRDataMethodInstance Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: c51825433bbc86c897c097475d5c15c855f6ec8b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790413"
---
# <a name="ixclrdatamethodinstance-interface"></a>Интерфейс IXCLRDataMethodInstance

Предоставляет методы для запроса сведений об экземпляре метода.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Методы

| Метод                                                                                                                  | Описание                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [жетиладдрессмап](ixclrdatamethodinstance-getiladdressmap-method.md) | Возвращает IL для сопоставления сведений о сопоставлении. |
| [жетрепресентативинтряддресс](ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | Возвращает наиболее репрезентативный адрес точки входа для собственной компиляции всех возможных точек входа для метода. |

## <a name="remarks"></a>Заметки

Этот интерфейс находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек. Однако это COM-интерфейс, производный от `IUnknown` с GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5`, который можно получить с помощью обычных механизмов COM.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также:

- [Отладка](index.md)
- [Интерфейсы отладки](debugging-interfaces.md)
