---
title: Функция Жетмесодкуалифиерсет (Справочник по неуправляемым API)
description: Функция Жетмесодкуалифиерсет извлекает набор квалификаторов метода.
ms.date: 11/06/2017
api_name:
- GetMethodQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodQualifierSet
helpviewer_keywords:
- GetMethodQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86a7788736c3c12cfcfd405de88dfadfb14c1eca
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798532"
---
# <a name="getmethodqualifierset-function"></a>Функция GetMethodQualifierSet

Получает набор квалификаторов для определенного метода.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a>Параметры

`vFunc`\
окне Этот параметр не используется.

`ptr`\
окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszMethod`\
окне Имя метода. `wszMethod`должен указывать на допустимое `LPCWSTR`значение.

`ppQualSet`\
заполняет Получает указатель интерфейса, который разрешает доступ к квалификаторам метода. Параметр `ppQualSet` не может иметь значение `null`. При возникновении ошибки новый объект не возвращается, и указатель устанавливается на точку `null`.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Указанный метод не существует. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр имеет значение `null`. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |

## <a name="remarks"></a>Примечания

Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: жетмесодкуалифиерсет](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) .

Вызов этой функции поддерживается только в том случае, если текущий объект является определением класса CIM. Управление методами недоступно для [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) указателей, указывающих на экземпляры CIM.

Поскольку каждый метод может иметь собственные квалификаторы, [указатель ивбемкуалифиерсет](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) позволяет вызывающей стороне добавить, изменить или удалить эти квалификаторы.

## <a name="requirements"></a>Требования

**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок.** WMINet_Utils. idl

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
