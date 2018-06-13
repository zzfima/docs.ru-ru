---
title: Функция WritePropertyValue (Справочник по неуправляемым API)
description: Функция WritePropertyValue записывает байты свойство.
ms.date: 11/06/2017
api_name:
- WritePropertyValue
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- WritePropertyValue
helpviewer_keywords:
- WritePropertyValue function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6aafb918616d27cf6289a8747f3336b2e813beb6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461088"
---
# <a name="writepropertyvalue-function"></a>Функция WritePropertyValue
Записывает указанное число байтов в свойство, идентифицируемое дескриптор свойства.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT WritePropertyValue (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
[in] Этот параметр не используется.

`ptr`  
[in] Указатель на [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) экземпляра.

`lHandle`  
[in] Целое число, содержащее дескриптор, который идентифицирует это свойство. Дескриптор можно получить, вызвав [GetPropertyHandle](getpropertyhandle.md) функции.   

`lNumBytes`  
[in] Число байтов, записываемых в свойство. В разделе [примечания](#remarks) Дополнительные сведения.

`pHandle`   
[out] Указатель на массив байтов, содержащий данные.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр не является допустимым. |
|`WBEM_E_TYPE_MISMATCH` | 0x80041005 | Несоответствие типов. |
|`WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::WritePropertyValue](https://msdn.microsoft.com/library/aa391783(v=vs.85).aspx) метод.

Эта функция позволяет задать строку и все другие не являющиеся -`DWORD` или не-`QWORD` данных.

Для значений свойств нестроковые `lNumBytes` должен быть размер правильные данные указанный тип. Строковые значения свойства `lNumBytes` должны иметь длину указанной строки в байтах и строка сам должен быть даже длины в байтах и идти символом конечное значение null.

## <a name="requirements"></a>Требования  
**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
