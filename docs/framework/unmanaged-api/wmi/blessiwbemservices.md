---
title: Функция BlessIWbemServices (Справочник по неуправляемым API)
description: Функция BlessIWbemServices указывает, разрешить ли учетные данные пользователя доступ к классу IWbemServices.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23b72856015d028e50c1e3bfd4a12e0f220291c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049327"
---
# <a name="blessiwbemservices-function"></a>Функция BlessIWbemServices
Указывает, разрешает ли учетные данные пользователя доступ к указанным [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) класса.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
[in] Указатель на [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) объекта, для которого требуются разрешения.

`strUser`\
[in] Имя пользователя.

`strPassword`\
[in] Пароль, связанный с `strUser`.

`strAuthority`\
[in] Имя домена пользователя. См. в разделе [ConnectServerWmi](connectserverwmi.md) функции подробнее.

`impLevel`\
[in] Уровень олицетворения.

`authnLevel`\
[in] Уровень авторизации.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WinError.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `E_INVALIDARG` | 0x80070057 | Один или несколько аргументов являются недопустимыми. |
| `E_POINTER` | 0x80004003 | Свойство `pIWbemServices` имеет значение `null`. | 
| `E_FAIL` | 0x80000008 | Произошла неизвестная ошибка. |
| `E_OUTOFMEMORY` | 0x80000002 | Недостаточно памяти для выполнения операции. | 
| `S_OK` | 0 | Вызов функции был успешным. | 

## <a name="requirements"></a>Требования  

 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)