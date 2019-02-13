---
title: Интерфейс ICorDebugProcess4
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4
helpviewer_keywords:
- ICorDebugProcess4 interface [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 1bdc958f2516bcd7c2eb74312fbf478e6d49535a
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221441"
---
# <a name="icordebugprocess4-interface"></a>Интерфейс ICorDebugProcess4

Обеспечивает поддержку вне контроля выполнения процесса.

## <a name="methods"></a>Методы

| Метод                                                                 | Описание:                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) | Уведомляет конвейера ICorDebug о том, что внепроцессные отладчик процесс продолжает выполнение отлаживаемого кода. |

## <a name="remarks"></a>Примечания

Этот интерфейс находится внутри среды выполнения и не предоставляется с помощью любой заголовков или библиотек. Однако это COM-интерфейс, наследуемый от `IUnknown` с идентификатором GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` , можно получить с помощью обычных механизмов COM.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок.** Нет

**Библиотека:** Нет

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
