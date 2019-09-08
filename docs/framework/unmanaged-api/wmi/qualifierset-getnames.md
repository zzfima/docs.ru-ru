---
title: Функция QualifierSet_GetNames (Справочник по неуправляемым API)
description: Функция QualifierSet_GetNames извлекает имена квалификаторов из объекта или свойства.
ms.date: 11/06/2017
api_name:
- QualifierSet_GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_GetNames
helpviewer_keywords:
- QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 266462a5393c8e26aa2bc3f2ec8ab72d4410a431
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798290"
---
# <a name="qualifierset_getnames-function"></a>Функция QualifierSet_GetNames

Извлекает имена всех квалификаторов или определенных квалификаторов, доступных из текущего объекта или свойства.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
);
```

## <a name="parameters"></a>Параметры

`vFunc`\
окне Этот параметр не используется.

`ptr`\
окне Указатель на экземпляр [ивбемкуалифиерсет](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

`lFlags`\
окне Один из следующих флагов или значений, указывающих, какие имена следует включить в перечисление.

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|  | 0 | Возвращает имена всех квалификаторов. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Возврат только имен квалификаторов, относящихся к текущему свойству или объекту. <br/> Для свойства: Возвращают только квалификаторы, относящиеся к свойству (включая переопределения), а не эти квалификаторы, распространяемые из определения класса. <br/> Для экземпляра: Возвращать только имена квалификаторов для конкретных экземпляров. <br/> Для класса: Возвращать только квалификаторы, относящиеся к производному классу.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | Возвращать только имена квалификаторов, распространяемых из другого объекта. <br/> Для свойства: Возвращают только те квалификаторы, которые распространяются на это свойство из определения класса, а не из самого свойства. <br/> Для экземпляра: Возвращать только те квалификаторы, которые распространяются из определения класса. <br/> Для класса: Возвращать только имена квалификаторов, унаследованные от родительских классов. |

`pstrNames`\
заполняет Новый `SAFEARRAY` объект, содержащий запрошенные имена. Массив может иметь 0 элементов. При возникновении ошибки новый `SAFEARRAY` объект не возвращается.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для начала нового перечисления. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |

## <a name="remarks"></a>Примечания

Эта функция заключает в оболочку вызов метода [ивбемкуалифиерсет:: Names](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) .

После получения имен квалификаторов можно получить доступ к каждому квалификатору по имени, вызвав функцию [QualifierSet_Get](qualifierset-get.md) .

Не является ошибкой, чтобы заданный объект имел нулевые квалификаторы, поэтому число строк в `pstrNames` on Return может быть равно 0, даже если функция возвращает. `WBEM_S_NO_ERROR`

## <a name="requirements"></a>Требования

**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок.** WMINet_Utils. idl

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
