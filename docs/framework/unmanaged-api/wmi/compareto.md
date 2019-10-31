---
title: Функция CompareTo (Справочник по неуправляемым API)
description: Функция CompareTo сравнивает объект с другим объектом WMI.
ms.date: 11/06/2017
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 0d210795016cd2e0179b902a224ca0c62f4ac01f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128701"
---
# <a name="compareto-function"></a>Функция CompareTo

Сравнивает объект с другим объектом управления Windows.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT CompareTo (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo
);
```

## <a name="parameters"></a>Параметры

`vFunc`\
окне Этот параметр не используется.

`ptr`\
окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`flags`\
окне Побитовое сочетание флагов, задающих характеристики объекта, которые следует учитывать при сравнении. Дополнительные сведения см. в разделе ["Примечания"](#remarks) .

`pCompareTo`\
окне Объект для сравнения. `pCompareTo` должен быть допустимым экземпляром [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) ; его невозможно `null`.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |значения  |Описание  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Произошла неопределенная ошибка. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Второй вызов `BeginEnumeration` был выполнен без промежуточного вызова [`EndEnumeration`](endenumeration.md). |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |
| `WBEM_S_DIFFERENT` | 0x40003 | Объекты различаются. |
| `WBEM_S_SAME` | 0 | Объекты одинаковы на основе флагов сравнения. |

## <a name="remarks"></a>Заметки

Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) .

Флаги, которые могут быть переданы в качестве аргумента `lEnumFlags`, определяются в файле заголовка *вбемкли. h* , или их можно определить как константы в коде. Можно указать отдельные характеристики, участвующие в сравнении, указав побитовое сочетание следующих флагов:

|Константа  |значения  |Описание  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | 2 | Игнорируйте источник (сервер и пространство имен, из которого они поступили). |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | 1 | Игнорировать все квалификаторы (включая **ключ** и **динамический**) |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | 4 | Игнорировать значения свойств по умолчанию. Этот флаг применяется только к сравнению классов. |
| `WBEM_FLAG_IGNORE_FLAVOR` | 0x20 | Не учитывать разновидности квалификаторов. Этот флаг по-прежнему учитывает квалификаторы, но не учитывает различия разновидностей, например правила распространения и ограничения переопределения. |
| `WBEM_FLAG_IGNORE_CASE` | 0x10 | Не учитывать регистр при сравнении строковых значений. Это применимо как к строкам, так и к значениям квалификаторов. При сравнении имен свойств и квалификаторов всегда учитывается регистр, независимо от того, установлен ли этот флаг. |
| `WBEM_FLAG_IGNORE_CLASS` | 0x8 | Предположим, что сравниваемые объекты являются экземплярами одного и того же класса. Следовательно, этот флаг сравнивает только сведения, относящиеся к экземпляру. Используйте эти флаги для оптимизации производительности. Если объекты не относятся к одному и тому же классу, результаты не определены. |

Или можно указать один составной флаг следующим образом:

|Константа  |значения  |Описание  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | 0 | Рассмотрите все функции в сравнении. |

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** WMINet_Utils. idl

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
