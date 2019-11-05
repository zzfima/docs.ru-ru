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
ms.openlocfilehash: 239e3a82df0e6010278669f9f429bfad0d163319
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133724"
---
# <a name="cordebugstatechange-enumeration"></a>Перечисление CorDebugStateChange

Описывает объем кэшированных данных, которые должны быть отброшены на основе изменений, внесенных в процесс.

## <a name="syntax"></a>Синтаксис

```cpp
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a>Члены

| Член            | Описание                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | Процесс достиг нового состояния памяти с помощью механизма прямого выполнения.            |
| `FLUSH_ALL`       | Память процесса может отличаться произвольным образом от предыдущего варианта. |

## <a name="remarks"></a>Заметки

 Член перечисления `CorDebugStateChange` предоставляется в качестве аргумента, когда отладчик вызывает метод `ProcessStateChanged` с помощью [ICorDebugProcess4::P роцессстатечанжед](icordebugprocess4-processstatechanged-method.md) или [ICorDebugProcess6::P роцессстатечанжед](icordebugprocess6-processstatechanged-method.md)

## <a name="requirements"></a>Требования

 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

 **Заголовок:** CorDebug.idl, CorDebug.h

 **Библиотека:** CorGuids.lib

 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>См. также

- [Перечисления отладки](debugging-enumerations.md)
- [Отладка](index.md)
