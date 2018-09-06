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
ms.openlocfilehash: 95ef445d41672c5c2895bd7115afb6a73a57e8f9
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43779926"
---
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="fd756-103">Функция FormatFromRawValue</span><span class="sxs-lookup"><span data-stu-id="fd756-103">FormatFromRawValue function</span></span>
<span data-ttu-id="fd756-104">Преобразует одно значение необработанных данных о производительности в указанный формат или делает это для двух значений, если преобразование формата зависит от времени.</span><span class="sxs-lookup"><span data-stu-id="fd756-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="fd756-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd756-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="fd756-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="fd756-106">Parameters</span></span>

`dwCounterType`  
<span data-ttu-id="fd756-107">[in] Тип счетчика.</span><span class="sxs-lookup"><span data-stu-id="fd756-107">[in] The counter type.</span></span> <span data-ttu-id="fd756-108">Список типов счетчиков, см. в разделе [типы счетчиков производительности WMI](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span><span class="sxs-lookup"><span data-stu-id="fd756-108">For a list of counter types, see [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span></span> <span data-ttu-id="fd756-109">`dwCounterType` может иметь любой тип счетчика, за исключением `PERF_LARGE_RAW_FRACTION` и `PERF_LARGE_RAW_BASE`.</span><span class="sxs-lookup"><span data-stu-id="fd756-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span> 

`dwFormat`  
<span data-ttu-id="fd756-110">[in] Формат, в который требуется преобразовать необработанные данные.</span><span class="sxs-lookup"><span data-stu-id="fd756-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="fd756-111">Он может принимать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="fd756-111">It can be one of the following values:</span></span>

|<span data-ttu-id="fd756-112">Константа</span><span class="sxs-lookup"><span data-stu-id="fd756-112">Constant</span></span>  |<span data-ttu-id="fd756-113">Значение</span><span class="sxs-lookup"><span data-stu-id="fd756-113">Value</span></span>  |<span data-ttu-id="fd756-114">Описание</span><span class="sxs-lookup"><span data-stu-id="fd756-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="fd756-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="fd756-115">0x00000200</span></span> | <span data-ttu-id="fd756-116">Возвращает вычисленное значение как значение с плавающей запятой двойной точности.</span><span class="sxs-lookup"><span data-stu-id="fd756-116">Return the calculated value as a double-precision floating point value.</span></span> | 
| `PDH_FMT_LARGE` | <span data-ttu-id="fd756-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="fd756-117">0x00000400</span></span> | <span data-ttu-id="fd756-118">Возвращает вычисленное значение как 64-разрядное целое число.</span><span class="sxs-lookup"><span data-stu-id="fd756-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="fd756-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="fd756-119">0x00000100</span></span> | <span data-ttu-id="fd756-120">Возвращает вычисленное значение как 32-разрядное целое число.</span><span class="sxs-lookup"><span data-stu-id="fd756-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="fd756-121">Одно из предыдущих значений может быть ORed с одним из следующих флагов масштабирования:</span><span class="sxs-lookup"><span data-stu-id="fd756-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="fd756-122">Константа</span><span class="sxs-lookup"><span data-stu-id="fd756-122">Constant</span></span>  |<span data-ttu-id="fd756-123">Значение</span><span class="sxs-lookup"><span data-stu-id="fd756-123">Value</span></span>  |<span data-ttu-id="fd756-124">Описание</span><span class="sxs-lookup"><span data-stu-id="fd756-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="fd756-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="fd756-125">0x00001000</span></span> | <span data-ttu-id="fd756-126">Коэффициенты масштабирования счетчика не применяются.</span><span class="sxs-lookup"><span data-stu-id="fd756-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="fd756-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="fd756-127">0x00002000</span></span> | <span data-ttu-id="fd756-128">Умножьте конечное значение 1000.</span><span class="sxs-lookup"><span data-stu-id="fd756-128">Multiply the final value by 1,000.</span></span> | 

`pTimeBase`  
<span data-ttu-id="fd756-129">[in] Указатель на базовое время, при необходимости для преобразования формата.</span><span class="sxs-lookup"><span data-stu-id="fd756-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="fd756-130">Если базовые сведения о времени не является обязательной для преобразования формата, значение этого параметра игнорируется.</span><span class="sxs-lookup"><span data-stu-id="fd756-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

<span data-ttu-id="fd756-131">`pRawValue1` [in] Указатель на [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) структура, представляющая значение оценки производительности.</span><span class="sxs-lookup"><span data-stu-id="fd756-131">`pRawValue1` [in] A pointer to a [`PDH_RAW_COUNTER`](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) structure that represents a raw performance value.</span></span>

<span data-ttu-id="fd756-132">`pRawValue2` [in] Указатель на [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) структура, представляющая значение секунд оценки производительности.</span><span class="sxs-lookup"><span data-stu-id="fd756-132">`pRawValue2` [in] A pointer to a [`PDH_RAW_COUNTER`](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) structure that represents a second raw performance value.</span></span> <span data-ttu-id="fd756-133">Если второе значение оценки производительности не требуется, этот параметр должен быть `null`.</span><span class="sxs-lookup"><span data-stu-id="fd756-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

<span data-ttu-id="fd756-134">`pFmtValue` [out] Указатель на [ `PDH_FMT_COUNTERVALUE` ](https://msdn.microsoft.com/library/windows/desktop/aa373050(v=vs.85).aspx) структуры, который получает значение форматированного производительности.</span><span class="sxs-lookup"><span data-stu-id="fd756-134">`pFmtValue` [out] A pointer to a [`PDH_FMT_COUNTERVALUE`](https://msdn.microsoft.com/library/windows/desktop/aa373050(v=vs.85).aspx) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="fd756-135">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fd756-135">Return value</span></span>

<span data-ttu-id="fd756-136">Эта функция возвращаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="fd756-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="fd756-137">Константа</span><span class="sxs-lookup"><span data-stu-id="fd756-137">Constant</span></span>  |<span data-ttu-id="fd756-138">Значение</span><span class="sxs-lookup"><span data-stu-id="fd756-138">Value</span></span>  |<span data-ttu-id="fd756-139">Описание</span><span class="sxs-lookup"><span data-stu-id="fd756-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="fd756-140">0</span><span class="sxs-lookup"><span data-stu-id="fd756-140">0</span></span> | <span data-ttu-id="fd756-141">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="fd756-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="fd756-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="fd756-142">0xC0000BBD</span></span> | <span data-ttu-id="fd756-143">Обязательный аргумент отсутствует или неверен.</span><span class="sxs-lookup"><span data-stu-id="fd756-143">A required argument is missing or incorrect.</span></span> | 
| `PDH_INVALID_HANDLE` | <span data-ttu-id="fd756-144">0xC0000BBC</span><span class="sxs-lookup"><span data-stu-id="fd756-144">0xC0000BBC</span></span> | <span data-ttu-id="fd756-145">Дескриптор не является допустимым PDH-объектом.</span><span class="sxs-lookup"><span data-stu-id="fd756-145">The handle is not a valid PDH object.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="fd756-146">Примечания</span><span class="sxs-lookup"><span data-stu-id="fd756-146">Remarks</span></span>

<span data-ttu-id="fd756-147">Эта функция создает оболочку для вызова [FormatFromRawValue](https://msdn.microsoft.com/library/ms231047(v=vs.85).aspx) функции.</span><span class="sxs-lookup"><span data-stu-id="fd756-147">This function wraps a call to the [FormatFromRawValue](https://msdn.microsoft.com/library/ms231047(v=vs.85).aspx) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="fd756-148">Требования</span><span class="sxs-lookup"><span data-stu-id="fd756-148">Requirements</span></span>  
 <span data-ttu-id="fd756-149">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd756-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd756-150">**Библиотека:** PerfCounter.dll</span><span class="sxs-lookup"><span data-stu-id="fd756-150">**Library:** PerfCounter.dll</span></span>  
  
 <span data-ttu-id="fd756-151">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fd756-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd756-152">См. также</span><span class="sxs-lookup"><span data-stu-id="fd756-152">See also</span></span>  
[<span data-ttu-id="fd756-153">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="fd756-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
