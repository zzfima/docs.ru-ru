---
title: Функция Вритепропертивалуе (Справочник по неуправляемым API)
description: Функция Вритепропертивалуе записывает байты в свойство.
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
ms.openlocfilehash: a3c42129835f9b30bed493a0992d49d7e2a458e2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798183"
---
# <a name="writepropertyvalue-function"></a>Функция Вритепропертивалуе
Записывает указанное число байт в свойство, заданное маркером свойства.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
окне Этот параметр не используется.

`ptr`  
окне Указатель на экземпляр [ивбемобжектакцесс](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) .

`lHandle`  
окне Целое число, содержащее маркер, определяющий это свойство. Этот маркер можно получить, вызвав функцию [жетпропертихандле](getpropertyhandle.md) .   

`lNumBytes`  
окне Число байтов, записываемых в свойство. Дополнительные сведения см. в разделе ["Примечания"](#remarks) .

`pHandle`   
заполняет Указатель на массив байтов, который содержит данные.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр. |
|`WBEM_E_TYPE_MISMATCH` | 0x80041005 | Обнаружено несоответствие типов. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |
  
## <a name="remarks"></a>Примечания

Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: вритепропертивалуе](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) .

Эта функция используется для задания строки и всех остальных не`DWORD` `QWORD` являющихся данными.

Для нестроковых значений `lNumBytes` свойств должен быть указан правильный размер данных указанного типа свойства. Для значений строковых свойств значение `lNumBytes` должно быть длиной указанной строки в байтах, а сама строка должна иметь допустимую длину в байтах и заканчиваться символом завершения null.

## <a name="requirements"></a>Требования  
**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** WMINet_Utils. idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
