---
title: Функция PUT (Справочник по неуправляемым API)
description: Функция Put присваивает новое значение именованного свойства.
ms.date: 11/06/2017
api_name:
- Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Put
helpviewer_keywords:
- Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02c8ab3aa7fcc603b76fb4b1d09e7e73d04494be
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369202"
---
# <a name="put-function"></a>Функция PUT

Задает новое значение для именованного свойства.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT Put (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
);
```

## <a name="parameters"></a>Параметры

`vFunc`\
[in] Этот параметр не используется.

`ptr`\
[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.

`wszName`\
[in] Имя свойства. Этот параметр не может быть `null`.

`lFlags`\
[in] Зарезервировано. Этот параметр должен быть 0.

`pVal`\
[in] Указатель на допустимую `VARIANT` , становится новым значением свойства. Если `pVal` — `null` или указывает на `VARIANT` типа `VT_NULL`, свойство имеет значение `null`.

`vtType`\
[in] Тип `VARIANT` , на которые указывают `pVal`. См. в разделе ["Примечания"](#remarks) Дополнительные сведения.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Произошел общий сбой. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Один или несколько параметров недопустимы. |
|`WBEM_E_INVALID_PROPERTY_TYPE` | 0x8004102a | Тип свойства не распознан. Это значение возвращается в том случае, если при создании экземпляров класса класс уже существует. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
| `WBEM_E_TYPE_MISMATCH` | 0x80041005 | Для экземпляров: Указывает, что `pVal` указывает `VARIANT` неверного типа для свойства. <br/> Для определения класса: Свойство уже существует в родительском классе, и новый тип COM отличается от старого COM-типом. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным. |

## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) метод.

Эта функция всегда перезаписывает его текущее значение свойства. Если [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) указывает на определение класса `Put` создает или обновляет значение свойства. Когда [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) указывает на экземпляр CIM `Put` обновляет значение свойства. `Put` не удается создать значение свойства.

`__CLASS` Системное свойство только для записи во время создания класса, когда он может не быть пустым. Все остальные свойства системы доступны только для чтения.

Пользователь не может создавать свойства с именами, начинаться или заканчиваться символ подчеркивания («_»). Этот атрибут зарезервирован для системных классов и свойств.

Если свойство задано `Put` функция существует в родительском классе, по умолчанию значение свойства изменяется в том случае, если тип свойства не соответствует типу класса родительского. Если свойство не существует, он не является несоответствие типов создается свойство.

Используйте `vtType` параметр только в том случае, при создании новых свойств в определении класса CIM и `pVal` — `null` или указывает на `VARIANT` типа `VT_NULL`. В этом случае `vType` параметр указывает тип CIM данного свойства. Во всех остальных случаях `vtType` должно быть равно 0. `vtType` также должен быть равен 0, если базовый объект является экземпляром (даже если `Val` — `null`), так как тип свойства является фиксированным и его нельзя изменить.

## <a name="example"></a>Пример

Например, см. в разделе [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) метод.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок.** WMINet_Utils.idl

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)