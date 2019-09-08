---
title: Функция Жетпропертикуалифиерсет (Справочник по неуправляемым API)
description: Функция Жетпропертикуалифиерсет извлекает квалификатор, заданный для свойства.
ms.date: 11/06/2017
api_name:
- GetPropertyQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyQualifierSet
helpviewer_keywords:
- GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7bce241d10051e4c6be94cdfa40de23773fb0bb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798483"
---
# <a name="getpropertyqualifierset-function"></a>Функция Жетпропертикуалифиерсет

Получает набор квалификаторов для определенного свойства.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a>Параметры

`vFunc`\
окне Этот параметр не используется.

`ptr`\
окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszMethod`\
окне Имя свойства. `wszProperty`должен указывать на допустимое `LPCWSTR`значение.

`ppQualSet`\
заполняет Получает указатель интерфейса, который разрешает доступ к квалификаторам свойства. Параметр `ppQualSet` не может иметь значение `null`. При возникновении ошибки новый объект не возвращается, и указатель устанавливается на точку `null`.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Общий сбой. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | Указанный метод не существует. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр имеет значение `null`. |
| `WBEM_E_SYSTEM_PROPERTY` | 0x80041030 | Функция пытается получить квалификаторы системного свойства. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |

## <a name="remarks"></a>Примечания

Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: жетпропертикуалифиерсет](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) .

Вызов этой функции поддерживается только в том случае, если текущий объект является определением класса CIM. Управление методами недоступно для [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) указателей, указывающих на экземпляры CIM.

Поскольку каждый метод может иметь собственные квалификаторы, [указатель ивбемкуалифиерсет](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) позволяет вызывающей стороне добавить, изменить или удалить эти квалификаторы.

Поскольку системные свойства не имеют квалификаторов, функция возвращает `WBEM_E_SYSTEM_PROPERTY` , если попытаться получить указатель [ивбемкуалифиерсет](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) для системного свойства.

## <a name="requirements"></a>Требования

**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок.** WMINet_Utils. idl

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
