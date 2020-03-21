---
title: Функция WritePropertyValue (Неуправляемая справка API)
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
ms.openlocfilehash: 4a950beef2e9bf8c0230d6a38008d75f89373410
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174840"
---
# <a name="writepropertyvalue-function"></a>Функция WritePropertyValue
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
(в) Этот параметр не используется.

`ptr`  
(в) Указатель на экземпляр [IWbemObjectAccess.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess)

`lHandle`  
(в) Цель, содержащая ручку, идентифицирует это свойство. Ручка может быть извлечена, позвонив в функцию [GetPropertyHandle.](getpropertyhandle.md)

`lNumBytes`  
(в) Количество байтов, записываемых в собственность. Дополнительную информацию можно узнать в разделе [«Замечания».](#remarks)

`pHandle`(ваут) Указатель на массив байт, содержащий данные.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:

|Постоянно  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недействительный параметр. |
|`WBEM_E_TYPE_MISMATCH` | 0x80041005 | Обнаружено несоответствие типов. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Remarks

Эта функция завершает вызов методом [IWbemClassObject::WritePropertyValue.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue)

Используйте эту функцию для установки строки и всех других не-`DWORD` или не-данных.`QWORD`

Для значений свойств, `lNumBytes` не стримных свойств, должен быть правильный размер данных указанного типа свойства. Для значений свойства `lNumBytes` строки должна быть длина указанной строки в байтах, а сама строка должна быть четной длины в байтах и следовать с символом с нулевым прекращением.

## <a name="requirements"></a>Требования  
**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
