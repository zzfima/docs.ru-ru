---
title: Функция GetMethodQualifierSet (Справочник по неуправляемым API)
description: Функция GetMethodQualifierSet извлекает набор описателей метода.
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
ms.openlocfilehash: 9257ba57e0d087e3d6b9c7bb995b49a6b814c5f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62040746"
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
[in] Этот параметр не используется.

`ptr`\
[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.

`wszMethod`\
[in] Имя метода. `wszMethod` должен указывать на допустимый `LPCWSTR`.

`ppQualSet`\
[out] Получает указатель интерфейса, которое разрешает доступ к квалификаторы метода. Параметр `ppQualSet` не может иметь значение `null`. Если возникает ошибка, не возвращается новый объект и указатель имеет значение для указания `null`.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Указанный метод не существует. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр — `null`. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |

## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) метод.

Вызов этой функции поддерживается только в том случае, если текущий объект является определение класса CIM. Метод манипуляции не доступен для [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) указатели, которые указывают на экземпляры CIM.

Так как каждый метод может иметь свой собственный квалификаторы [IWbemQualifierSet указатель](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) позволяет вызывающему объекту добавить, изменить или удалить эти квалификаторы.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок.** WMINet_Utils.idl

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)