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
ms.openlocfilehash: e306834166051ae48fd283d51f18d9458091578f
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416664"
---
# <a name="ixclrdatamodule-interface"></a>Интерфейс IXCLRDataModule

Предоставляет методы для запроса на получение сведений о загруженном модуле.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Методы

| Метод                                                                                                                                | Описание:                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [GetMethodDefinitionByToken](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-getmethoddefinitionbytoken-method.md) | Возвращает определение метода, соответствующей токену метаданных. |
| [Запрос](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-request-method.md)                                       | Запросы, чтобы заполнить буфер с данными модуля.       |
| [GetVersionId](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-getversionid-method.md)                             | Получает идентификатор версии модуля.                                       |

## <a name="remarks"></a>Примечания

Этот интерфейс находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек. Однако это COM-интерфейс, наследуемый от `IUnknown` с идентификатором GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` , можно получить с помощью обычных механизмов COM.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок.** Нет  
**Библиотека:** Нет  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
