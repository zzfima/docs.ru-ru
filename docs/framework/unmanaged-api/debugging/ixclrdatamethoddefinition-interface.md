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
ms.openlocfilehash: 4b1e8cb1cf34bb1c5ade1353351aab953e2b734a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670109"
---
# <a name="ixclrdatamethoddefinition-interface"></a>Интерфейс IXCLRDataMethodDefinition

Предоставляет методы для запроса на получение сведений об определении метода.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Методы

Следующие методы перечислены методы, доступные в интерфейсе.

| Метод                                                                                                                          | Описание                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [StartEnumInstances](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-startenuminstances-method.md) | Предоставляет дескриптор для перечисления экземпляров метода для заданного `IXCLRDataAppDomain`. |
| [EnumInstance](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-enuminstance-method.md)             | Перечисление экземпляров класса определения метода.                                         |
| [EndEnumInstances](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-endenuminstances-method.md)     | Освобождает ресурсы, используемые внутренней итераторы, используется в процессе экземпляра перечисления.         |

## <a name="remarks"></a>Примечания

Этот интерфейс находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек. Однако это COM-интерфейс, наследуемый от `IUnknown` с идентификатором GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` , можно получить с помощью обычных механизмов COM.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок.** Нет  
**Библиотека:** Нет  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
