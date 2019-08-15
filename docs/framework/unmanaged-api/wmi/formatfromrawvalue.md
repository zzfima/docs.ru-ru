---
title: Функция Форматфромраввалуе (Справочник по неуправляемым API)
description: Функция Форматфромраввалуе преобразует необработанные данные производительности в указанный формат.
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
ms.openlocfilehash: 681d7ce42b2b8d16353e4f5b3523f1a953a49d95
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69037889"
---
# <a name="formatfromrawvalue-function"></a>Функция FormatFromRawValue
Преобразует одно значение необработанных данных о производительности в указанный формат или делает это для двух значений, если преобразование формата зависит от времени. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис

```cpp
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

`dwCounterType`\
окне Тип счетчика. Список типов счетчиков см. в разделе [типы счетчиков производительности WMI](/windows/desktop/WmiSdk/wmi-performance-counter-types). `dwCounterType`может быть любым типом счетчика `PERF_LARGE_RAW_FRACTION` , за исключением и. `PERF_LARGE_RAW_BASE` 

`dwFormat`\
окне Формат, в который преобразуются необработанные данные производительности. Может принимать одно из следующих значений:

|Константа  |Значение  |Описание |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |0x00000200 | Возвращает вычисленное значение в виде значения с плавающей запятой двойной точности. | 
| `PDH_FMT_LARGE` | 0x00000400 | Возвращает вычисленное значение как 64-разрядное целое число. |
| `PDH_FMT_LONG` | 0x00000100 | Возвращает вычисленное значение как 32-разрядное целое число. |

Одно из предыдущих значений можно ORed с помощью одного из следующих флагов масштабирования:

|Константа  |Значение  |Описание |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | 0x00001000 | Не применяйте коэффициенты масштабирования счетчика. |
| `PDH_FMT_1000` | 0x00002000 | Умножьте окончательное значение на 1 000. | 

`pTimeBase`\
окне Указатель на базовую базу времени, если это необходимо для преобразования формата. Если для преобразования формата не требуется базовая информация времени, значение этого параметра игнорируется.

`pRawValue1`\ [in] указатель на [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) структуру, представляющую необработанное значение производительности.

`pRawValue2`\
окне Указатель на [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) структуру, представляющую второе необработанное значение производительности. Если второе необработанное значение производительности не требуется, этот параметр должен быть `null`равен.

`pFmtValue`\
заполняет Указатель на [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) структуру, получающую отформатированное значение производительности.

## <a name="return-value"></a>Возвращаемое значение

Эта функция возвращает следующие значения:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `ERROR_SUCCESS` | 0 | Вызов функции выполнен успешно. |
| `PDH_INVALID_ARGUMENT` | 0xC0000BBD | Обязательный аргумент отсутствует или неверен. | 
| `PDH_INVALID_HANDLE` | 0xC0000BBC | Этот маркер не является допустимым объектом PDH. |

## <a name="remarks"></a>Примечания

Эта функция заключает в оболочку вызов функции [форматфромраввалуе](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) .

## <a name="requirements"></a>Требования

 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

 **Библиотечная** Перфкаунтер. dll

 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
