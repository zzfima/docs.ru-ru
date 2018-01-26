---
title: "Функция FormatFromRawValue (Справочник по неуправляемым API)"
description: "Функция FormatFromRawValue преобразует необработанные данные производительности в указанный формат."
ms.date: 11/21/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: FormatFromRawValue
api_location: PerfCounter.dll
api_type: DLLExport
f1_keywords: FormatFromRawValue
helpviewer_keywords: FormatFromRawValue function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3daa89ec0b40bb9c08898ecd682f05f0f0ce09a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="formatfromrawvalue-function"></a>Функция FormatFromRawValue
Преобразует одно значение данных оценки производительности в указанный формат или два значения данных для оценки производительности, если преобразование формата выполняется на основе времени.   
  
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
[in] Тип счетчика. Список типов счетчиков см. в разделе [типы счетчиков производительности WMI](https://msdn.microsoft.com/library/aa394569(v=vs.85).aspx). `dwCounterType`может иметь любой тип счетчика, за исключением `PERF_LARGE_RAW_FRACTION` и `PERF_LARGE_RAW_BASE`. 

`dwFormat`  
[in] Формат, в который требуется преобразовать необработанные данные производительности. Он может принимать одно из следующих значений:

|Константа  |Значение  |Описание: |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |0x00000200 | Возвращает вычисленное значение как значение с плавающей запятой двойной точности. | 
| `PDH_FMT_LARGE` | 0x00000400 | Возвращает вычисленное значение как 64-разрядное целое число. |
| `PDH_FMT_LONG` | 0x00000100 | Возвращает вычисленное значение как 32-разрядное целое число. |

Одно из предыдущих значений можно связать логическим с одним из следующих флагов масштабирования:

|Константа  |Значение  |Описание: |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | 0x00001000 | Коэффициенты масштабирования счетчика не применяются. |
| `PDH_FMT_1000` | 0x00002000 | Умножьте окончательное значение 1000. | 

`pTimeBase`  
[in] Указатель на базовое время, если это необходимо для преобразования формата. Если базовые сведения о времени не является обязательной для преобразования формата, значение этого параметра учитывается.

`pRawValue1`[in] Указатель на [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) структуру, которая представляет значение оценки производительности.

`pRawValue2`[in] Указатель на [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) структуру, которая представляет значение секунд оценки производительности. Если второе значение оценки производительности не является обязательной, этот параметр должен быть `null`.

`pFmtValue`[out] Указатель на [ `PDH_FMT_COUNTERVALUE` ](https://msdn.microsoft.com/library/windows/desktop/aa373050(v=vs.85).aspx) структуру, которая получает значение форматированные производительности.

## <a name="return-value"></a>Возвращаемое значение

Эта функция возвращаются следующие значения.

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `ERROR_SUCCESS` | 0 | Вызов функции выполняется успешно. |
| `PDH_INVALID_ARGUMENT` | 0xC0000BBD | Обязательный аргумент отсутствует или является недопустимым. | 
| `PDH_INVALID_HANDLE` | 0xC0000BBC | Дескриптор не является допустимым PDH-объектом. |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [FormatFromRawValue](https://msdn.microsoft.com/library/ms231047(v=vs.85).aspx) функции.

## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Библиотека:** PerfCounter.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
