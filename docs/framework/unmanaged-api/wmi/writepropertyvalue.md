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
ms.openlocfilehash: 26337a13ab9840b79c253d4af2d84a10e70877c5
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="writepropertyvalue-function"></a><span data-ttu-id="3b4a1-103">Функция WritePropertyValue</span><span class="sxs-lookup"><span data-stu-id="3b4a1-103">WritePropertyValue function</span></span>
<span data-ttu-id="3b4a1-104">Записывает указанное число байтов в свойство, идентифицируемое дескриптор свойства.</span><span class="sxs-lookup"><span data-stu-id="3b4a1-104">Writes a specified number of bytes to a property identified by a property handle.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="3b4a1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b4a1-105">Syntax</span></span>  
  
```  
HRESULT WritePropertyValue (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
); 
```  

## <a name="parameters"></a><span data-ttu-id="3b4a1-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3b4a1-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="3b4a1-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="3b4a1-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="3b4a1-108">[in] Указатель на [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="3b4a1-108">[in] A pointer to an [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) instance.</span></span>

`lHandle`  
<span data-ttu-id="3b4a1-109">[in] Целое число, содержащее дескриптор, который идентифицирует это свойство.</span><span class="sxs-lookup"><span data-stu-id="3b4a1-109">[in] An integer that contains the handle that identifies this property.</span></span> <span data-ttu-id="3b4a1-110">Дескриптор можно получить, вызвав [GetPropertyHandle](getpropertyhandle.md) функции.</span><span class="sxs-lookup"><span data-stu-id="3b4a1-110">The handle can be retrieved by calling the [GetPropertyHandle](getpropertyhandle.md) function.</span></span>   

`lNumBytes`  
<span data-ttu-id="3b4a1-111">[in] Число байтов, записываемых в свойство.</span><span class="sxs-lookup"><span data-stu-id="3b4a1-111">[in] The number of bytes being written to the property.</span></span> <span data-ttu-id="3b4a1-112">В разделе [примечания](#remarks) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="3b4a1-112">See the [Remarks](#remarks) section for more information.</span></span>

`pHandle`   
<span data-ttu-id="3b4a1-113">[out] Указатель на массив байтов, содержащий данные.</span><span class="sxs-lookup"><span data-stu-id="3b4a1-113">[out] A pointer to the byte array that contains the data.</span></span>

## <a name="return-value"></a><span data-ttu-id="3b4a1-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3b4a1-114">Return value</span></span>

<span data-ttu-id="3b4a1-115">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="3b4a1-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3b4a1-116">Константа</span><span class="sxs-lookup"><span data-stu-id="3b4a1-116">Constant</span></span>  |<span data-ttu-id="3b4a1-117">Значение</span><span class="sxs-lookup"><span data-stu-id="3b4a1-117">Value</span></span>  |<span data-ttu-id="3b4a1-118">Описание</span><span class="sxs-lookup"><span data-stu-id="3b4a1-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3b4a1-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3b4a1-119">0x80041008</span></span> | <span data-ttu-id="3b4a1-120">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="3b4a1-120">A parameter is not valid.</span></span> |
|`WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="3b4a1-121">0x80041005</span><span class="sxs-lookup"><span data-stu-id="3b4a1-121">0x80041005</span></span> | <span data-ttu-id="3b4a1-122">Несоответствие типов.</span><span class="sxs-lookup"><span data-stu-id="3b4a1-122">A type mismatch occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="3b4a1-123">0</span><span class="sxs-lookup"><span data-stu-id="3b4a1-123">0</span></span> | <span data-ttu-id="3b4a1-124">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="3b4a1-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="3b4a1-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="3b4a1-125">Remarks</span></span>

<span data-ttu-id="3b4a1-126">Эта функция создает оболочку для вызова [IWbemClassObject::WritePropertyValue](https://msdn.microsoft.com/library/aa391783(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="3b4a1-126">This function wraps a call to the [IWbemClassObject::WritePropertyValue](https://msdn.microsoft.com/library/aa391783(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="3b4a1-127">Эта функция позволяет задать строку и все другие не являющиеся -`DWORD` или не-`QWORD` данных.</span><span class="sxs-lookup"><span data-stu-id="3b4a1-127">Use this function to set string and all other non-`DWORD` or non-`QWORD` data.</span></span>

<span data-ttu-id="3b4a1-128">Для значений свойств нестроковые `lNumBytes` должен быть размер правильные данные указанный тип.</span><span class="sxs-lookup"><span data-stu-id="3b4a1-128">For nonstring property values, `lNumBytes` must be the correct data size of the property type specified.</span></span> <span data-ttu-id="3b4a1-129">Строковые значения свойства `lNumBytes` должны иметь длину указанной строки в байтах и строка сам должен быть даже длины в байтах и идти символом конечное значение null.</span><span class="sxs-lookup"><span data-stu-id="3b4a1-129">For string property values, `lNumBytes` must be the length of the specified string in bytes, and the string itself must be of an even length in bytes and be followed with a null-termination character.</span></span>

## <a name="requirements"></a><span data-ttu-id="3b4a1-130">Требования</span><span class="sxs-lookup"><span data-stu-id="3b4a1-130">Requirements</span></span>  
<span data-ttu-id="3b4a1-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b4a1-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b4a1-132">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3b4a1-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3b4a1-133">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3b4a1-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b4a1-134">См. также</span><span class="sxs-lookup"><span data-stu-id="3b4a1-134">See also</span></span>  
[<span data-ttu-id="3b4a1-135">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="3b4a1-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
