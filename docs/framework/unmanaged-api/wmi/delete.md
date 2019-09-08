---
title: Функция Delete (Справочник по неуправляемым API)
description: Функция Delete удаляет указанное свойство и все его квалификаторы из определения класса CIM.
ms.date: 11/06/2017
api_name:
- Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Delete
helpviewer_keywords:
- Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1bf9bd5d93d1affee649588138456269411d280
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798669"
---
# <a name="delete-function"></a>Функция Delete

Удаляет указанное свойство и все его квалификаторы из определения класса CIM.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```

## <a name="parameters"></a>Параметры

`vFunc`\
окне Этот параметр не используется.

`ptr`\
окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszName`\
окне Имя удаляемого свойства. `wszName`должен быть указателем на допустимый `LPCWSTR`объект.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Произошла неопределенная ошибка. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | Свойство не может быть удалено. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `wszName` недопустим. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | Указанное свойство не существует. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
| `WBEM_E_PROPAGATED_PROPERTY` | 0x8004101c | Свойство наследуется от базового класса. |
| `WBEM_E_SYSTEM_PROPERTY` | | Свойство является системным свойством. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |
| `WBEM_E_RESET_TO_DEFAULT` | 0x80041030 | Функция удалила значение переопределения по умолчанию для текущего класса. Значение по умолчанию для этого свойства в родительском классе было повторно активировано. |

## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова метода [ивбемклассобжект::D удалить](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) .

## <a name="requirements"></a>Требования

**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок.** WMINet_Utils. idl

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
