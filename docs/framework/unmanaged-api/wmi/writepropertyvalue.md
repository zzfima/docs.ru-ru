---
title: "Функция WritePropertyValue (Справочник по неуправляемым API)"
description: "Функция WritePropertyValue записывает байты свойство."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: WritePropertyValue
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: WritePropertyValue
helpviewer_keywords: WritePropertyValue function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7221c9e0f1cb49ab0e27130ce69c0527ba903148
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="writepropertyvalue-function"></a><span data-ttu-id="04179-103">Функция WritePropertyValue</span><span class="sxs-lookup"><span data-stu-id="04179-103">WritePropertyValue function</span></span>
<span data-ttu-id="04179-104">Записывает указанное число байтов в свойство, идентифицируемое дескриптор свойства.</span><span class="sxs-lookup"><span data-stu-id="04179-104">Writes a specified number of bytes to a property identified by a property handle.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="04179-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04179-105">Syntax</span></span>  
  
```  
HRESULT WritePropertyValue (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
); 
```  

## <a name="parameters"></a><span data-ttu-id="04179-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="04179-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="04179-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="04179-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="04179-108">[in] Указатель на [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="04179-108">[in] A pointer to an [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) instance.</span></span>

`lHandle`  
<span data-ttu-id="04179-109">[in] Целое число, содержащее дескриптор, который идентифицирует это свойство.</span><span class="sxs-lookup"><span data-stu-id="04179-109">[in] An integer that contains the handle that identifies this property.</span></span> <span data-ttu-id="04179-110">Дескриптор можно получить, вызвав [GetPropertyHandle](getpropertyhandle.md) функции.</span><span class="sxs-lookup"><span data-stu-id="04179-110">The handle can be retrieved by calling the [GetPropertyHandle](getpropertyhandle.md) function.</span></span>   

`lNumBytes`  
<span data-ttu-id="04179-111">[in] Число байтов, записываемых в свойство.</span><span class="sxs-lookup"><span data-stu-id="04179-111">[in] The number of bytes being written to the property.</span></span> <span data-ttu-id="04179-112">В разделе [примечания](#remarks) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="04179-112">See the [Remarks](#remarks) section for more information.</span></span>

`pHandle`   
<span data-ttu-id="04179-113">[out] Указатель на массив байтов, содержащий данные.</span><span class="sxs-lookup"><span data-stu-id="04179-113">[out] A pointer to the byte array that contains the data.</span></span>

## <a name="return-value"></a><span data-ttu-id="04179-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="04179-114">Return value</span></span>

<span data-ttu-id="04179-115">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="04179-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="04179-116">Константа</span><span class="sxs-lookup"><span data-stu-id="04179-116">Constant</span></span>  |<span data-ttu-id="04179-117">Значение</span><span class="sxs-lookup"><span data-stu-id="04179-117">Value</span></span>  |<span data-ttu-id="04179-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="04179-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="04179-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="04179-119">0x80041008</span></span> | <span data-ttu-id="04179-120">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="04179-120">A parameter is not valid.</span></span> |
|`WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="04179-121">0x80041005</span><span class="sxs-lookup"><span data-stu-id="04179-121">0x80041005</span></span> | <span data-ttu-id="04179-122">Несоответствие типов.</span><span class="sxs-lookup"><span data-stu-id="04179-122">A type mismatch occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="04179-123">0</span><span class="sxs-lookup"><span data-stu-id="04179-123">0</span></span> | <span data-ttu-id="04179-124">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="04179-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="04179-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="04179-125">Remarks</span></span>

<span data-ttu-id="04179-126">Эта функция создает оболочку для вызова [IWbemClassObject::WritePropertyValue](https://msdn.microsoft.com/library/aa391783(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="04179-126">This function wraps a call to the [IWbemClassObject::WritePropertyValue](https://msdn.microsoft.com/library/aa391783(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="04179-127">Эта функция позволяет задать строку и все другие не являющиеся -`DWORD` или не-`QWORD` данных.</span><span class="sxs-lookup"><span data-stu-id="04179-127">Use this function to set string and all other non-`DWORD` or non-`QWORD` data.</span></span>

<span data-ttu-id="04179-128">Для значений свойств нестроковые `lNumBytes` должен быть размер правильные данные указанный тип.</span><span class="sxs-lookup"><span data-stu-id="04179-128">For nonstring property values, `lNumBytes` must be the correct data size of the property type specified.</span></span> <span data-ttu-id="04179-129">Строковые значения свойства `lNumBytes` должны иметь длину указанной строки в байтах и строка сам должен быть даже длины в байтах и идти символом конечное значение null.</span><span class="sxs-lookup"><span data-stu-id="04179-129">For string property values, `lNumBytes` must be the length of the specified string in bytes, and the string itself must be of an even length in bytes and be followed with a null-termination character.</span></span>

## <a name="requirements"></a><span data-ttu-id="04179-130">Требования</span><span class="sxs-lookup"><span data-stu-id="04179-130">Requirements</span></span>  
<span data-ttu-id="04179-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04179-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04179-132">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="04179-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="04179-133">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="04179-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04179-134">См. также</span><span class="sxs-lookup"><span data-stu-id="04179-134">See also</span></span>  
[<span data-ttu-id="04179-135">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="04179-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
