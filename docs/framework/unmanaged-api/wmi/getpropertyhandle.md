---
title: "Функция GetPropertyHandle (Справочник по неуправляемым API)"
description: "Функция GetPropertyHandle возвращает уникальный дескриптор этого свойства удостоверения."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
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
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3af852fb4b9899a7937f288ffb65d8ca84e4aef1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="getpropertyhandle-function"></a>Функция GetPropertyHandle
Возвращает уникальный дескриптор, который определяет свойство.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetPropertyHandle (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
[in] Этот параметр не используется.

`ptr`  
[in] Указатель на [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) экземпляра.

`wszPropertyName`  
[in] Нулем строка кодировки UTF16 знака, содержащее имя свойства.   

`pType`  
[out] Указатель на [ `CIMTYPE` ](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) член перечисления, представляющее CIM-тип свойства.

`pHandle`   
[out] Указатель на целое число, содержащее дескриптор свойства.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Указанное имя свойства не найден. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр не является допустимым. |
|`WBEM_E_NOT_SUPPORTED` | 0x8004100c | Запрошенное свойство имеет тип, `CIM_OBJECT` или `CIM_ARRAY`. |
|`WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::GetPropertyHandle](https://msdn.microsoft.com/library/aa391771(v=vs.85).aspx) метод.

Этот дескриптор можно использовать для идентификации свойств, при использовании [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) методы для чтения или записи значения свойств.

Дескрипторы может быть извлечен для свойства всех типов данных, отличный от `CIM_OBJECT` и `CIM_ARRAY`. Возвращенная работу дескрипторы для всех экземпляров класса.

## <a name="requirements"></a>Требования  
**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
