---
title: Функция BlessIWbemServices (Неуправляемая справка API)
description: Функция BlessIWbemServices указывает, позволяют ли учетные данные пользователей получить доступ к классу IWbemServices.
ms.date: 11/06/2017
api_name:
- BlessIWbemServices
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServices
helpviewer_keywords:
- BlessIWbemServices function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 4b15af840cc00b3ec261604db4f3625c6b975d3e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176868"
---
# <a name="blessiwbemservices-function"></a>Функция BlessIWbemServices
Указывает, позволяют ли учетные данные пользователя получить доступ к указанному классу [IWbemServices.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT BlessIWbemServices (
   [in] IWbemServices* pIWbemServices,
   [in] BSTR strUser,
   [in] BSTR strPassword,
   [in] BSTR strAuthority,
   [in] DWORD impLevel,
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a>Параметры

`pIWbemServices`\
(в) Указатель на объект [IWbemServices,](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) для которого требуются разрешения.

`strUser`\
(в) Имя пользователя.

`strPassword`\
(в) Пароль, связанный с `strUser`.

`strAuthority`\
(в) Доменное имя пользователя. Дополнительную информацию можно узнать из функции [ConnectServerWmi.](connectserverwmi.md)

`impLevel`\
(в) Уровень олицетворения.

`authnLevel`\
(в) Уровень авторизации.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WinError.h* или вы можете определить их как константы в коде:

|Постоянно  |Значение  |Описание  |
|---------|---------|---------|
| `E_INVALIDARG` | 0x80070057 | Один или несколько аргументов недействительны. |
| `E_POINTER` | 0x80004003 | Параметр `pIWbemServices` равен `null`. |
| `E_FAIL` | 0x80000008 | Возникла неопределенная ошибка. |
| `E_OUTOFMEMORY` | 0x80000002 | Недостаточно памяти доступно для выполнения операции. |
| `S_OK` | 0 | Вызов функции был успешным. |

## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
