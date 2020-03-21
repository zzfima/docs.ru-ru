---
title: Функция FormatFromRawValue (Неуправляемая ссылка на API)
description: Функция FormatFromRawValue преобразует необработанные данные о производительности в указанный формат.
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
ms.openlocfilehash: 0a7c0b8387f0c8e2b6e2ade94f7efeede75bd758
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176842"
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
(в) Тип счетчика. Список встречных типов можно узнать на примере [счетчика производительности WMI.](/windows/desktop/WmiSdk/wmi-performance-counter-types) `dwCounterType`может быть любой `PERF_LARGE_RAW_FRACTION` счетчик `PERF_LARGE_RAW_BASE`типа, за исключением и .

`dwFormat`\
(в) Формат, в который можно преобразовать необработанные данные о производительности. Может иметь одно из следующих значений.

|Постоянно  |Значение  |Описание |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |0x00000200 | Верните рассчитанное значение в виде двойного значения плавающей точки. |
| `PDH_FMT_LARGE` | 0x00000400 | Верните рассчитанное значение в виде 64-битного целых. |
| `PDH_FMT_LONG` | 0x00000100 | Верните рассчитанное значение в виде 32-битного целых. |

Одним из предыдущих значений может быть ORed с одним из следующих флагов масштабирования:

|Постоянно  |Значение  |Описание |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | 0x00001000 | Не применяйте факторы масштабирования счетчика. |
| `PDH_FMT_1000` | 0x00002000 | Умножьте окончательное значение на 1000. |

`pTimeBase`\
(в) Указатель на временной базой, при необходимости для преобразования формата. Если информация о временной базе не требуется для преобразования формата, значение этого параметра игнорируется.

`pRawValue1`\
(в) Указатель на [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) структуру, представляющую необработанное значение производительности.

`pRawValue2`\
(в) Указатель на [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) структуру, представляющую второе необработанное значение производительности. Если второе необработанное значение производительности `null`не требуется, этот параметр должен быть .

`pFmtValue`\
(ваут) Указатель на [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) структуру, которая получает отформатированное значение производительности.

## <a name="return-value"></a>Возвращаемое значение

Эта функция возвращает следующие значения:

|Постоянно  |Значение  |Описание  |
|---------|---------|---------|
| `ERROR_SUCCESS` | 0 | Вызов функции успешен. |
| `PDH_INVALID_ARGUMENT` | 0xC0000BBD | Необходимый аргумент отсутствует или неверен. |
| `PDH_INVALID_HANDLE` | 0xC0000BBC | Ручка не является действительным объектом PDH. |

## <a name="remarks"></a>Remarks

Эта функция завершает вызов функции [FormatFromRawValue.](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85))

## <a name="requirements"></a>Требования

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

 **Библиотека:** PerfCounter.dll

 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
