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
ms.openlocfilehash: f02fb3877d55e9f47384b281573202712c29c606
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107294"
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

|Константа  |значения  |Описание  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр. |
|`WBEM_E_TYPE_MISMATCH` | 0x80041005 | Обнаружено несоответствие типов. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |
  
## <a name="remarks"></a>Заметки

Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: вритепропертивалуе](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) .

Используйте эту функцию, чтобы задать строку и все остальные не`DWORD`ные или не`QWORD`ные данные.

Для нестроковых значений свойств `lNumBytes` должен иметь правильный размер данных указанного типа свойства. Для значений строковых свойств `lNumBytes` должно быть длиной указанной строки в байтах, а сама строка должна иметь допустимую длину в байтах и следовать за завершающим символом NULL.

## <a name="requirements"></a>Требования  
**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils. idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
