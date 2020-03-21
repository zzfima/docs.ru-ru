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
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="1fcda-103">Функция FormatFromRawValue</span><span class="sxs-lookup"><span data-stu-id="1fcda-103">FormatFromRawValue function</span></span>
<span data-ttu-id="1fcda-104">Преобразует одно значение необработанных данных о производительности в указанный формат или делает это для двух значений, если преобразование формата зависит от времени.</span><span class="sxs-lookup"><span data-stu-id="1fcda-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="1fcda-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1fcda-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="1fcda-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1fcda-106">Parameters</span></span>

`dwCounterType`\
<span data-ttu-id="1fcda-107">(в) Тип счетчика.</span><span class="sxs-lookup"><span data-stu-id="1fcda-107">[in] The counter type.</span></span> <span data-ttu-id="1fcda-108">Список встречных типов можно узнать на примере [счетчика производительности WMI.](/windows/desktop/WmiSdk/wmi-performance-counter-types)</span><span class="sxs-lookup"><span data-stu-id="1fcda-108">For a list of counter types, see [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span></span> <span data-ttu-id="1fcda-109">`dwCounterType`может быть любой `PERF_LARGE_RAW_FRACTION` счетчик `PERF_LARGE_RAW_BASE`типа, за исключением и .</span><span class="sxs-lookup"><span data-stu-id="1fcda-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span>

`dwFormat`\
<span data-ttu-id="1fcda-110">(в) Формат, в который можно преобразовать необработанные данные о производительности.</span><span class="sxs-lookup"><span data-stu-id="1fcda-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="1fcda-111">Может иметь одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="1fcda-111">It can be one of the following values:</span></span>

|<span data-ttu-id="1fcda-112">Постоянно</span><span class="sxs-lookup"><span data-stu-id="1fcda-112">Constant</span></span>  |<span data-ttu-id="1fcda-113">Значение</span><span class="sxs-lookup"><span data-stu-id="1fcda-113">Value</span></span>  |<span data-ttu-id="1fcda-114">Описание</span><span class="sxs-lookup"><span data-stu-id="1fcda-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="1fcda-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="1fcda-115">0x00000200</span></span> | <span data-ttu-id="1fcda-116">Верните рассчитанное значение в виде двойного значения плавающей точки.</span><span class="sxs-lookup"><span data-stu-id="1fcda-116">Return the calculated value as a double-precision floating point value.</span></span> |
| `PDH_FMT_LARGE` | <span data-ttu-id="1fcda-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="1fcda-117">0x00000400</span></span> | <span data-ttu-id="1fcda-118">Верните рассчитанное значение в виде 64-битного целых.</span><span class="sxs-lookup"><span data-stu-id="1fcda-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="1fcda-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="1fcda-119">0x00000100</span></span> | <span data-ttu-id="1fcda-120">Верните рассчитанное значение в виде 32-битного целых.</span><span class="sxs-lookup"><span data-stu-id="1fcda-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="1fcda-121">Одним из предыдущих значений может быть ORed с одним из следующих флагов масштабирования:</span><span class="sxs-lookup"><span data-stu-id="1fcda-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="1fcda-122">Постоянно</span><span class="sxs-lookup"><span data-stu-id="1fcda-122">Constant</span></span>  |<span data-ttu-id="1fcda-123">Значение</span><span class="sxs-lookup"><span data-stu-id="1fcda-123">Value</span></span>  |<span data-ttu-id="1fcda-124">Описание</span><span class="sxs-lookup"><span data-stu-id="1fcda-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="1fcda-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="1fcda-125">0x00001000</span></span> | <span data-ttu-id="1fcda-126">Не применяйте факторы масштабирования счетчика.</span><span class="sxs-lookup"><span data-stu-id="1fcda-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="1fcda-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="1fcda-127">0x00002000</span></span> | <span data-ttu-id="1fcda-128">Умножьте окончательное значение на 1000.</span><span class="sxs-lookup"><span data-stu-id="1fcda-128">Multiply the final value by 1,000.</span></span> |

`pTimeBase`\
<span data-ttu-id="1fcda-129">(в) Указатель на временной базой, при необходимости для преобразования формата.</span><span class="sxs-lookup"><span data-stu-id="1fcda-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="1fcda-130">Если информация о временной базе не требуется для преобразования формата, значение этого параметра игнорируется.</span><span class="sxs-lookup"><span data-stu-id="1fcda-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

`pRawValue1`\
<span data-ttu-id="1fcda-131">(в) Указатель на [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) структуру, представляющую необработанное значение производительности.</span><span class="sxs-lookup"><span data-stu-id="1fcda-131">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a raw performance value.</span></span>

`pRawValue2`\
<span data-ttu-id="1fcda-132">(в) Указатель на [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) структуру, представляющую второе необработанное значение производительности.</span><span class="sxs-lookup"><span data-stu-id="1fcda-132">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a second raw performance value.</span></span> <span data-ttu-id="1fcda-133">Если второе необработанное значение производительности `null`не требуется, этот параметр должен быть .</span><span class="sxs-lookup"><span data-stu-id="1fcda-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

`pFmtValue`\
<span data-ttu-id="1fcda-134">(ваут) Указатель на [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) структуру, которая получает отформатированное значение производительности.</span><span class="sxs-lookup"><span data-stu-id="1fcda-134">[out] A pointer to a [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="1fcda-135">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1fcda-135">Return value</span></span>

<span data-ttu-id="1fcda-136">Эта функция возвращает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="1fcda-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="1fcda-137">Постоянно</span><span class="sxs-lookup"><span data-stu-id="1fcda-137">Constant</span></span>  |<span data-ttu-id="1fcda-138">Значение</span><span class="sxs-lookup"><span data-stu-id="1fcda-138">Value</span></span>  |<span data-ttu-id="1fcda-139">Описание</span><span class="sxs-lookup"><span data-stu-id="1fcda-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="1fcda-140">0</span><span class="sxs-lookup"><span data-stu-id="1fcda-140">0</span></span> | <span data-ttu-id="1fcda-141">Вызов функции успешен.</span><span class="sxs-lookup"><span data-stu-id="1fcda-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="1fcda-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="1fcda-142">0xC0000BBD</span></span> | <span data-ttu-id="1fcda-143">Необходимый аргумент отсутствует или неверен.</span><span class="sxs-lookup"><span data-stu-id="1fcda-143">A required argument is missing or incorrect.</span></span> |
| `PDH_INVALID_HANDLE` | <span data-ttu-id="1fcda-144">0xC0000BBC</span><span class="sxs-lookup"><span data-stu-id="1fcda-144">0xC0000BBC</span></span> | <span data-ttu-id="1fcda-145">Ручка не является действительным объектом PDH.</span><span class="sxs-lookup"><span data-stu-id="1fcda-145">The handle is not a valid PDH object.</span></span> |

## <a name="remarks"></a><span data-ttu-id="1fcda-146">Remarks</span><span class="sxs-lookup"><span data-stu-id="1fcda-146">Remarks</span></span>

<span data-ttu-id="1fcda-147">Эта функция завершает вызов функции [FormatFromRawValue.](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="1fcda-147">This function wraps a call to the [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="1fcda-148">Требования</span><span class="sxs-lookup"><span data-stu-id="1fcda-148">Requirements</span></span>

 <span data-ttu-id="1fcda-149">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fcda-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="1fcda-150">**Библиотека:** PerfCounter.dll</span><span class="sxs-lookup"><span data-stu-id="1fcda-150">**Library:** PerfCounter.dll</span></span>

 <span data-ttu-id="1fcda-151">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1fcda-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1fcda-152">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1fcda-152">See also</span></span>

- [<span data-ttu-id="1fcda-153">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="1fcda-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
