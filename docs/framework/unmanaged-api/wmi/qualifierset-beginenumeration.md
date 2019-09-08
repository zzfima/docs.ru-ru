---
title: Функция QualifierSet_BeginEnumeration (Справочник по неуправляемым API)
description: Функция QualifierSet_BeginEnumeration Сбрасывает перечислитель квалификаторов объекта.
ms.date: 11/06/2017
api_name:
- QualifierSet_BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_BeginEnumeration
helpviewer_keywords:
- QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b75c51ebddd78e447fed57b22a96c2d5c35004e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798349"
---
# <a name="qualifierset_beginenumeration-function"></a>Функция QualifierSet_BeginEnumeration

Сбрасывает перечислитель квалификаторов объекта в начало перечисления.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags
);
```

## <a name="parameters"></a>Параметры

`vFunc`\
окне Этот параметр не используется.

`ptr`\
окне Указатель на экземпляр [ивбемкуалифиерсет](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

`lFlags`\
окне Побитовое сочетание флагов или значений, описанных в разделе « [Примечания](#remarks) », в котором указываются квалификаторы, включаемые в перечисление.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр `lFlags`. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Второй вызов `QualifierSet_BeginEnumeration` был выполнен без промежуточного [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md)вызова. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для начала нового перечисления. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |

## <a name="remarks"></a>Примечания

Эта функция заключает в оболочку вызов метода [ивбемкуалифиерсет:: BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) .

Чтобы перечислить все квалификаторы объекта, этот метод должен вызываться перед первым вызовом [QualifierSet_Next](qualifierset-next.md). Порядок перечисления квалификаторов гарантированно является инвариантным для данного перечисления.

Флаги, которые могут быть переданы `lEnumFlags` в качестве аргумента, определяются в файле заголовка *вбемкли. h* или могут быть определены в коде в виде констант.

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|  | 0 | Возвращает имена всех квалификаторов. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Возврат только имен квалификаторов, относящихся к текущему свойству или объекту. <br/> Для свойства: Возвращают только квалификаторы, относящиеся к свойству (включая переопределения), а не эти квалификаторы, распространяемые из определения класса. <br/> Для экземпляра: Возвращать только имена квалификаторов для конкретных экземпляров. <br/> Для класса: Возвращать только квалификаторы, относящиеся к производному классу.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | Возвращать только имена квалификаторов, распространяемых из другого объекта. <br/> Для свойства: Возвращают только те квалификаторы, которые распространяются на это свойство из определения класса, а не из самого свойства. <br/> Для экземпляра: Возвращать только те квалификаторы, которые распространяются из определения класса. <br/> Для класса: Возвращать только имена квалификаторов, унаследованные от родительских классов. |

## <a name="requirements"></a>Требования

**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок.** WMINet_Utils. idl

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
