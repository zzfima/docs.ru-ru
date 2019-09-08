---
title: Функция Жетпропертихандле (Справочник по неуправляемым API)
description: Функция Жетпропертихандле Возвращает уникальный маркер, идентифицирующий свойство.
ms.date: 11/06/2017
api_name:
- GetPropertyHandle
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyHandle
helpviewer_keywords:
- GetPropertyHandle function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d72b0da43971a74a08a249b19dfc0d446eeb5e6a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798544"
---
# <a name="getpropertyhandle-function"></a>Функция GetPropertyHandle

Возвращает уникальный маркер, определяющий свойство.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetPropertyHandle (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
);
```

## <a name="parameters"></a>Параметры

`vFunc`\
окне Этот параметр не используется.

`ptr`\
окне Указатель на экземпляр [ивбемобжектакцесс](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) .

`wszPropertyName`\
окне Строка символов в кодировке UTF16, заканчивающаяся нулем и содержащая имя свойства.

`pType`\
заполняет Указатель на [`CIMTYPE`](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) член перечисления, представляющий CIM-тип свойства.

`pHandle`\
заполняет Указатель на целое число, содержащее маркер свойства.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Указанное имя свойства не найдено. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр. |
|`WBEM_E_NOT_SUPPORTED` | 0x8004100c | Запрошенное свойство имеет тип `CIM_OBJECT` или. `CIM_ARRAY` |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |

## <a name="remarks"></a>Примечания

Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: жетпропертихандле](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) .

Этот обработчик можно использовать для обнаружения свойств при использовании методов [ивбемобжектакцесс](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) для чтения или записи значений свойств.

Дескрипторы могут быть получены для свойств всех типов `CIM_OBJECT` данных, кроме и. `CIM_ARRAY` Возвращаемые дескрипторы работают для всех экземпляров класса.

## <a name="requirements"></a>Требования

**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок.** WMINet_Utils. idl

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
