---
title: Перечисление CorDebugStateChange
ms.date: 02/07/2019
api_name:
- CorDebugStateChange
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05a29022d3ebad37322aef9826f10689d2b5b06b
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221138"
---
# <a name="cordebugstatechange-enumeration"></a>Перечисление CorDebugStateChange

Описывает объем кэшированных данных, которые должны быть отброшены на основе изменений, внесенных в процесс.

## <a name="syntax"></a>Синтаксис

```
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a>Участники

| Член            | Описание                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | Процесс достиг нового состояния памяти с помощью механизма прямого выполнения.            |
| `FLUSH_ALL`       | Память процесса может отличаться произвольным образом от предыдущего варианта. |

## <a name="remarks"></a>Примечания

 Является членом `CorDebugStateChange` перечисление предоставляется в качестве аргумента при вызове отладчиком `ProcessStateChanged` метод с помощью [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) или [ICorDebugProcess6:: ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)

## <a name="requirements"></a>Требования

 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

 **Заголовок.** CorDebug.idl, CorDebug.h

 **Библиотека:** CorGuids.lib

 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>См. также

- [Перечисления отладки](debugging-enumerations.md)
- [Отладка](index.md)
