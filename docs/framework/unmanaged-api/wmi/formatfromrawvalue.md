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
ms.openlocfilehash: 420a02d2f7757c52d6e8ff92a9ca30e44938cd18
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546443"
---
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="42a5b-103">Функция FormatFromRawValue</span><span class="sxs-lookup"><span data-stu-id="42a5b-103">FormatFromRawValue function</span></span>
<span data-ttu-id="42a5b-104">Преобразует одно значение необработанных данных о производительности в указанный формат или делает это для двух значений, если преобразование формата зависит от времени.</span><span class="sxs-lookup"><span data-stu-id="42a5b-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="42a5b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42a5b-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="42a5b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="42a5b-106">Parameters</span></span>

`dwCounterType`  
<span data-ttu-id="42a5b-107">[in] Тип счетчика.</span><span class="sxs-lookup"><span data-stu-id="42a5b-107">[in] The counter type.</span></span> <span data-ttu-id="42a5b-108">Список типов счетчиков, см. в разделе [типы счетчиков производительности WMI](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span><span class="sxs-lookup"><span data-stu-id="42a5b-108">For a list of counter types, see [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span></span> <span data-ttu-id="42a5b-109">`dwCounterType` может иметь любой тип счетчика, за исключением `PERF_LARGE_RAW_FRACTION` и `PERF_LARGE_RAW_BASE`.</span><span class="sxs-lookup"><span data-stu-id="42a5b-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span> 

`dwFormat`  
<span data-ttu-id="42a5b-110">[in] Формат, в который требуется преобразовать необработанные данные.</span><span class="sxs-lookup"><span data-stu-id="42a5b-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="42a5b-111">Он может принимать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="42a5b-111">It can be one of the following values:</span></span>

|<span data-ttu-id="42a5b-112">Константа</span><span class="sxs-lookup"><span data-stu-id="42a5b-112">Constant</span></span>  |<span data-ttu-id="42a5b-113">Значение</span><span class="sxs-lookup"><span data-stu-id="42a5b-113">Value</span></span>  |<span data-ttu-id="42a5b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="42a5b-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="42a5b-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="42a5b-115">0x00000200</span></span> | <span data-ttu-id="42a5b-116">Возвращает вычисленное значение как значение с плавающей запятой двойной точности.</span><span class="sxs-lookup"><span data-stu-id="42a5b-116">Return the calculated value as a double-precision floating point value.</span></span> | 
| `PDH_FMT_LARGE` | <span data-ttu-id="42a5b-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="42a5b-117">0x00000400</span></span> | <span data-ttu-id="42a5b-118">Возвращает вычисленное значение как 64-разрядное целое число.</span><span class="sxs-lookup"><span data-stu-id="42a5b-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="42a5b-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="42a5b-119">0x00000100</span></span> | <span data-ttu-id="42a5b-120">Возвращает вычисленное значение как 32-разрядное целое число.</span><span class="sxs-lookup"><span data-stu-id="42a5b-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="42a5b-121">Одно из предыдущих значений может быть ORed с одним из следующих флагов масштабирования:</span><span class="sxs-lookup"><span data-stu-id="42a5b-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="42a5b-122">Константа</span><span class="sxs-lookup"><span data-stu-id="42a5b-122">Constant</span></span>  |<span data-ttu-id="42a5b-123">Значение</span><span class="sxs-lookup"><span data-stu-id="42a5b-123">Value</span></span>  |<span data-ttu-id="42a5b-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="42a5b-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="42a5b-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="42a5b-125">0x00001000</span></span> | <span data-ttu-id="42a5b-126">Коэффициенты масштабирования счетчика не применяются.</span><span class="sxs-lookup"><span data-stu-id="42a5b-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="42a5b-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="42a5b-127">0x00002000</span></span> | <span data-ttu-id="42a5b-128">Умножьте конечное значение 1000.</span><span class="sxs-lookup"><span data-stu-id="42a5b-128">Multiply the final value by 1,000.</span></span> | 

`pTimeBase`  
<span data-ttu-id="42a5b-129">[in] Указатель на базовое время, при необходимости для преобразования формата.</span><span class="sxs-lookup"><span data-stu-id="42a5b-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="42a5b-130">Если базовые сведения о времени не является обязательной для преобразования формата, значение этого параметра игнорируется.</span><span class="sxs-lookup"><span data-stu-id="42a5b-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

<span data-ttu-id="42a5b-131">`pRawValue1` [in] Указатель на [ `PDH_RAW_COUNTER` ](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter) структура, представляющая значение оценки производительности.</span><span class="sxs-lookup"><span data-stu-id="42a5b-131">`pRawValue1` [in] A pointer to a [`PDH_RAW_COUNTER`](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter) structure that represents a raw performance value.</span></span>

<span data-ttu-id="42a5b-132">`pRawValue2` [in] Указатель на [ `PDH_RAW_COUNTER` ](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter) структура, представляющая значение секунд оценки производительности.</span><span class="sxs-lookup"><span data-stu-id="42a5b-132">`pRawValue2` [in] A pointer to a [`PDH_RAW_COUNTER`](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter) structure that represents a second raw performance value.</span></span> <span data-ttu-id="42a5b-133">Если второе значение оценки производительности не требуется, этот параметр должен быть `null`.</span><span class="sxs-lookup"><span data-stu-id="42a5b-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

<span data-ttu-id="42a5b-134">`pFmtValue` [out] Указатель на [ `PDH_FMT_COUNTERVALUE` ](/windows/desktop/api/pdh/ns-pdh-_pdh_fmt_countervalue) структуры, который получает значение форматированного производительности.</span><span class="sxs-lookup"><span data-stu-id="42a5b-134">`pFmtValue` [out] A pointer to a [`PDH_FMT_COUNTERVALUE`](/windows/desktop/api/pdh/ns-pdh-_pdh_fmt_countervalue) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="42a5b-135">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="42a5b-135">Return value</span></span>

<span data-ttu-id="42a5b-136">Эта функция возвращаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="42a5b-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="42a5b-137">Константа</span><span class="sxs-lookup"><span data-stu-id="42a5b-137">Constant</span></span>  |<span data-ttu-id="42a5b-138">Значение</span><span class="sxs-lookup"><span data-stu-id="42a5b-138">Value</span></span>  |<span data-ttu-id="42a5b-139">Описание</span><span class="sxs-lookup"><span data-stu-id="42a5b-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="42a5b-140">0</span><span class="sxs-lookup"><span data-stu-id="42a5b-140">0</span></span> | <span data-ttu-id="42a5b-141">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="42a5b-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="42a5b-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="42a5b-142">0xC0000BBD</span></span> | <span data-ttu-id="42a5b-143">Обязательный аргумент отсутствует или неверен.</span><span class="sxs-lookup"><span data-stu-id="42a5b-143">A required argument is missing or incorrect.</span></span> | 
| `PDH_INVALID_HANDLE` | <span data-ttu-id="42a5b-144">0xC0000BBC</span><span class="sxs-lookup"><span data-stu-id="42a5b-144">0xC0000BBC</span></span> | <span data-ttu-id="42a5b-145">Дескриптор не является допустимым PDH-объектом.</span><span class="sxs-lookup"><span data-stu-id="42a5b-145">The handle is not a valid PDH object.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="42a5b-146">Примечания</span><span class="sxs-lookup"><span data-stu-id="42a5b-146">Remarks</span></span>

<span data-ttu-id="42a5b-147">Эта функция создает оболочку для вызова [FormatFromRawValue](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/ms231047%28v=vs.85%29) функции.</span><span class="sxs-lookup"><span data-stu-id="42a5b-147">This function wraps a call to the [FormatFromRawValue](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/ms231047%28v=vs.85%29) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="42a5b-148">Требования</span><span class="sxs-lookup"><span data-stu-id="42a5b-148">Requirements</span></span>  
 <span data-ttu-id="42a5b-149">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42a5b-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42a5b-150">**Библиотека:** PerfCounter.dll</span><span class="sxs-lookup"><span data-stu-id="42a5b-150">**Library:** PerfCounter.dll</span></span>  
  
 <span data-ttu-id="42a5b-151">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="42a5b-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42a5b-152">См. также</span><span class="sxs-lookup"><span data-stu-id="42a5b-152">See also</span></span>
- [<span data-ttu-id="42a5b-153">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="42a5b-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
