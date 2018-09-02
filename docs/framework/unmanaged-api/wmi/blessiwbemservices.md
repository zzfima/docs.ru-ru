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
ms.openlocfilehash: a65c3c14507b2520c69875a1bc101ce826ace7ba
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43466454"
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

`pIWbemServices`  
[in] Указатель на [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) объекта, для которого требуются разрешения.

`strUser`  
[in] Имя пользователя.

`strPassword`  
[in] Пароль, связанный с `strUser`.

`strAuthority` [in] Имя домена пользователя. См. в разделе [ConnectServerWmi](connectserverwmi.md) функции подробнее.

`impLevel` [in] Уровень олицетворения.

`authnLevel` [in] Уровень авторизации.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WinError.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
| `E_INVALIDARG` | 0x80070057 | Один или несколько аргументов являются недопустимыми. |
| `E_POINTER` | 0x80004003 | Свойство `pIWbemServices` имеет значение `null`. | 
| `E_FAIL` | 0x80000008 | Произошла неизвестная ошибка. |
| `E_OUTOFMEMORY` | 0x80000002 | Недостаточно памяти для выполнения операции. | 
| `S_OK` | 0 | Вызов функции был успешным. | 

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
