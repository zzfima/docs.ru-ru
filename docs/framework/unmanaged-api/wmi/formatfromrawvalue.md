---
title: Функция FormatFromRawValue (Справочник по неуправляемым API)
description: Функция FormatFromRawValue преобразует необработанные данные производительности в указанный формат.
ms.date: 11/21/2017
api_name:
- FormatFromRawValue
api_location:
- PerfCounter.dll
api_type:
- DLLExport
f1_keywords:
- FormatFromRawValue
helpviewer_keywords:
- FormatFromRawValue function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 90af7d01d78cf74cbb304e3b987d5fe58e23f76e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2018
ms.locfileid: "50196704"
---
# <a name="formatfromrawvalue-function"></a>Функция FormatFromRawValue
Преобразует одно значение необработанных данных о производительности в указанный формат или делает это для двух значений, если преобразование формата зависит от времени.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
int FormatFromRawValue (
   [in] uint                    dwCounterType, 
   [in] uint                    dwFormat, 
   [in] long*                   pTimeBase,
   [in] PDH_RAW_COUNTER*        pRawValue1,
   [in] PDH_RAW_COUNTER*        pRawValue2,
   [out] PDH_FMT_COUNTERVALUE*  pFmtValue
); 
```  

## <a name="parameters"></a>Параметры

`dwCounterType`  
[in] Тип счетчика. Список типов счетчиков, см. в разделе [типы счетчиков производительности WMI](/windows/desktop/WmiSdk/wmi-performance-counter-types). `dwCounterType` может иметь любой тип счетчика, за исключением `PERF_LARGE_RAW_FRACTION` и `PERF_LARGE_RAW_BASE`. 

`dwFormat`  
[in] Формат, в который требуется преобразовать необработанные данные. Он может принимать одно из следующих значений:

|Константа  |Значение  |Описание |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |0x00000200 | Возвращает вычисленное значение как значение с плавающей запятой двойной точности. | 
| `PDH_FMT_LARGE` | 0x00000400 | Возвращает вычисленное значение как 64-разрядное целое число. |
| `PDH_FMT_LONG` | 0x00000100 | Возвращает вычисленное значение как 32-разрядное целое число. |

Одно из предыдущих значений может быть ORed с одним из следующих флагов масштабирования:

|Константа  |Значение  |Описание |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | 0x00001000 | Коэффициенты масштабирования счетчика не применяются. |
| `PDH_FMT_1000` | 0x00002000 | Умножьте конечное значение 1000. | 

`pTimeBase`  
[in] Указатель на базовое время, при необходимости для преобразования формата. Если базовые сведения о времени не является обязательной для преобразования формата, значение этого параметра игнорируется.

`pRawValue1` [in] Указатель на [ `PDH_RAW_COUNTER` ](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter) структура, представляющая значение оценки производительности.

`pRawValue2` [in] Указатель на [ `PDH_RAW_COUNTER` ](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter) структура, представляющая значение секунд оценки производительности. Если второе значение оценки производительности не требуется, этот параметр должен быть `null`.

`pFmtValue` [out] Указатель на [ `PDH_FMT_COUNTERVALUE` ](/windows/desktop/api/pdh/ns-pdh-_pdh_fmt_countervalue) структуры, который получает значение форматированного производительности.

## <a name="return-value"></a>Возвращаемое значение

Эта функция возвращаются следующие значения:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `ERROR_SUCCESS` | 0 | Вызов функции был успешным. |
| `PDH_INVALID_ARGUMENT` | 0xC0000BBD | Обязательный аргумент отсутствует или неверен. | 
| `PDH_INVALID_HANDLE` | 0xC0000BBC | Дескриптор не является допустимым PDH-объектом. |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [FormatFromRawValue](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/ms231047%28v=vs.85%29) функции.

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Библиотека:** PerfCounter.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
