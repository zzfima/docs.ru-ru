---
title: Функция BlessIWbemServicesObject (Справочник по неуправляемым API)
description: Функция BlessIWbemServicesObject указывает, разрешить ли учетные данные пользователя доступ к объекту IWbemServices
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1bc31a4f074891149783dec647a592683564ba0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457923"
---
# <a name="blessiwbemservicesobject-function"></a>Функция BlessIWbemServicesObject
Указывает, разрешить ли учетные данные пользователя доступ к определенному [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) объекта.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
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

`pIWbemServices`  
[in] Указатель на объект службы WMI.

`strUser`  
[in] Имя пользователя.

`strPassword`  
[in] Пароль, связанный с `strUser`.

`strAuthority` [in] Имя домена пользователя. В разделе [ConnectServerWmi](connectserverwmi.md) функции для получения дополнительной информации.

`impLevel` [in] Уровень олицетворения.

`authnLevel` [in] Уровень авторизации.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WinError.h* заголовочный файл, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `E_INVALIDARG` | 0x80070057 | Один или несколько аргументов являются недопустимыми. |
| `E_POINTER` | отметкой 0x80004003 | Свойство `pIWbemServices` имеет значение `null`. | 
| `E_FAIL` | 0x80000008 | Произошла неизвестная ошибка. |
| `E_OUTOFMEMORY` | 0x80000002 | Недостаточно памяти для выполнения операции. | 
| `S_OK` | 0 | Успешный вызов функции. | 

## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
