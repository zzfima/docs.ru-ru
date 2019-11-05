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
ms.openlocfilehash: bd0a67987dd8ffa825114726d066249aed40cf05
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141691"
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

|Константа  |значения  |Описание  |
|---------|---------|---------|
|  | 0 | Возвращает имена всех квалификаторов. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Возврат только имен квалификаторов, относящихся к текущему свойству или объекту. <br/> Для свойства: возвращают только квалификаторы, относящиеся к свойству (включая переопределения), а не эти квалификаторы, распространенные из определения класса. <br/> Для экземпляра: возвращать только имена квалификаторов, относящиеся только к экземпляру. <br/> Для класса: возвращать только квалификаторы, относящиеся к производному классу.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | Возвращать только имена квалификаторов, распространяемых из другого объекта. <br/> Для свойства: возвращают только те квалификаторы, которые распространяются на это свойство из определения класса, а не из самого свойства. <br/> Для экземпляра: возврат только тех квалификаторов, которые распространяются из определения класса. <br/> Для класса: возвращают только имена квалификаторов, унаследованные от родительских классов. |

`pstrNames`\
заполняет Новый `SAFEARRAY`, содержащий запрошенные имена. Массив может иметь 0 элементов. При возникновении ошибки новый `SAFEARRAY` не возвращается.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |значения  |Описание  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для начала нового перечисления. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |

## <a name="remarks"></a>Заметки

Эта функция заключает в оболочку вызов метода [ивбемкуалифиерсет:: Names](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) .

После получения имен квалификаторов можно получить доступ к каждому квалификатору по имени, вызвав функцию [QualifierSet_Get](qualifierset-get.md) .

Не является ошибкой, чтобы заданный объект имел нулевые квалификаторы, так что число строк в `pstrNames` возвращаемого значения может равняться 0, даже если функция возвращает `WBEM_S_NO_ERROR`.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** WMINet_Utils. idl

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
