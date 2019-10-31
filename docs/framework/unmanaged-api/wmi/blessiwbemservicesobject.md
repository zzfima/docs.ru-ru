---
title: Функция Блессивбемсервицесобжект (Справочник по неуправляемым API)
description: Функция Блессивбемсервицесобжект указывает, допускают ли учетные данные пользователя доступ к объекту IWbemServices.
ms.date: 11/06/2017
api_name:
- BlessIWbemServicesObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServicesObject
helpviewer_keywords:
- BlessIWbemServicesObject function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f77ff394668a235dd63cf0cddf71ea418a28125b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141683"
---
# <a name="blessiwbemservicesobject-function"></a>Функция BlessIWbemServicesObject
Указывает, допускают ли учетные данные пользователя доступ к указанному объекту [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) . 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT BlessIWbemServicesObject (
   [in] IUnknown* pIUnknown,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```

## <a name="parameters"></a>Параметры

`pIWbemServices`\
окне Указатель на объект службы WMI.

`strUser`\
окне Имя пользователя.

`strPassword`\
окне Пароль, связанный с `strUser`.

`strAuthority`\
окне Доменное имя пользователя. Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .

`impLevel`\
окне Уровень олицетворения.

`authnLevel`\
окне Уровень авторизации.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *Winerror. h* , или их можно определить как константы в коде:

|Константа  |значения  |Описание  |
|---------|---------|---------|
| `E_INVALIDARG` | 0x80070057 | Один или несколько аргументов недопустимы. |
| `E_POINTER` | 0x80004003 | Свойство `pIWbemServices` имеет значение `null`. | 
| `E_FAIL` | 0x80000008 | Произошла неопределенная ошибка. |
| `E_OUTOFMEMORY` | 0x80000002 | Недостаточно свободной памяти для выполнения операции. | 
| `S_OK` | 0 | Вызов функции выполнен успешно. | 

## <a name="requirements"></a>Требования

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

 **Заголовок:** WMINet_Utils. idl

 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
