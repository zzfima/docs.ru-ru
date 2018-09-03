---
title: Функция WritePropertyValue (Справочник по неуправляемым API)
description: Функция WritePropertyValue записывает байты к свойству.
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
ms.openlocfilehash: f2a4eb444967390492be33b25866de8a93a1698c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43393911"
---
# <a name="writepropertyvalue-function"></a>Функция WritePropertyValue
Записывает указанное число байтов для свойства, идентифицируемого по дескриптор свойства.

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
[in] Указатель на [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) экземпляра.

`lHandle`  
[in] Целое число, которое содержит дескриптор, определяющий это свойство. Дескриптор можно получить, вызвав [GetPropertyHandle](getpropertyhandle.md) функции.   

`lNumBytes`  
[in] Число байтов, записываемых в свойство. См. в разделе ["Примечания"](#remarks) Дополнительные сведения.

`pHandle`   
[out] Указатель на массив байтов, содержащий данные.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр не является допустимым. |
|`WBEM_E_TYPE_MISMATCH` | 0x80041005 | Несоответствие типов. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) метод.

Эта функция позволяет задать строки и всех других отличных`DWORD` или отличные от-`QWORD` данных.

Для значений свойств нестроковые `lNumBytes` должен быть тип свойства, заданный размер правильные данные. Для значений свойств строки `lNumBytes` должны иметь длину указанной строки в байтах, и строка сам должен быть даже длины в байтах и следовать знак завершения null.

## <a name="requirements"></a>Требования  
**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
