---
title: Интерфейс IXCLRDataMethodDefinition
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition Interface
helpviewer.keywords:
- IXCLRDataMethodDefinition Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 708c681a98113a406249a360c2fc81087e5b97f8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790425"
---
# <a name="ixclrdatamethoddefinition-interface"></a>Интерфейс IXCLRDataMethodDefinition

Предоставляет методы для запроса сведений об определении метода.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Методы

Ниже перечислены методы, доступные в интерфейсе.

| Метод                                                                                                                          | Описание                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [стартенуминстанцес](ixclrdatamethoddefinition-startenuminstances-method.md) | Предоставляет обработчик для перечисления экземпляров методов для заданного `IXCLRDataAppDomain`. |
| [енуминстанце](ixclrdatamethoddefinition-enuminstance-method.md)             | Перечисляет экземпляры этого определения метода.                                         |
| [енденуминстанцес](ixclrdatamethoddefinition-endenuminstances-method.md)     | Освобождает ресурсы, используемые внутренними итераторами, используемыми при перечислении экземпляров.         |

## <a name="remarks"></a>Заметки

Этот интерфейс находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек. Однако это COM-интерфейс, производный от `IUnknown` с GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97`, который можно получить с помощью обычных механизмов COM.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также:

- [Отладка](index.md)
- [Интерфейсы отладки](debugging-interfaces.md)
