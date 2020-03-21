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
# <a name="writepropertyvalue-function"></a><span data-ttu-id="4c06a-103">Функция WritePropertyValue</span><span class="sxs-lookup"><span data-stu-id="4c06a-103">WritePropertyValue function</span></span>
<span data-ttu-id="4c06a-104">Записывает указанное число байт в свойство, заданное маркером свойства.</span><span class="sxs-lookup"><span data-stu-id="4c06a-104">Writes a specified number of bytes to a property identified by a property handle.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="4c06a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c06a-105">Syntax</span></span>  
  
```cpp  
HRESULT WritePropertyValue (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
);
```  

## <a name="parameters"></a><span data-ttu-id="4c06a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4c06a-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="4c06a-107">(в) Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="4c06a-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="4c06a-108">(в) Указатель на экземпляр [IWbemObjectAccess.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess)</span><span class="sxs-lookup"><span data-stu-id="4c06a-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`lHandle`  
<span data-ttu-id="4c06a-109">(в) Цель, содержащая ручку, идентифицирует это свойство.</span><span class="sxs-lookup"><span data-stu-id="4c06a-109">[in] An integer that contains the handle that identifies this property.</span></span> <span data-ttu-id="4c06a-110">Ручка может быть извлечена, позвонив в функцию [GetPropertyHandle.](getpropertyhandle.md)</span><span class="sxs-lookup"><span data-stu-id="4c06a-110">The handle can be retrieved by calling the [GetPropertyHandle](getpropertyhandle.md) function.</span></span>

`lNumBytes`  
<span data-ttu-id="4c06a-111">(в) Количество байтов, записываемых в собственность.</span><span class="sxs-lookup"><span data-stu-id="4c06a-111">[in] The number of bytes being written to the property.</span></span> <span data-ttu-id="4c06a-112">Дополнительную информацию можно узнать в разделе [«Замечания».](#remarks)</span><span class="sxs-lookup"><span data-stu-id="4c06a-112">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="4c06a-113">`pHandle`(ваут) Указатель на массив байт, содержащий данные.</span><span class="sxs-lookup"><span data-stu-id="4c06a-113">`pHandle` [out] A pointer to the byte array that contains the data.</span></span>

## <a name="return-value"></a><span data-ttu-id="4c06a-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4c06a-114">Return value</span></span>

<span data-ttu-id="4c06a-115">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="4c06a-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4c06a-116">Постоянно</span><span class="sxs-lookup"><span data-stu-id="4c06a-116">Constant</span></span>  |<span data-ttu-id="4c06a-117">Значение</span><span class="sxs-lookup"><span data-stu-id="4c06a-117">Value</span></span>  |<span data-ttu-id="4c06a-118">Описание</span><span class="sxs-lookup"><span data-stu-id="4c06a-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="4c06a-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="4c06a-119">0x80041008</span></span> | <span data-ttu-id="4c06a-120">Недействительный параметр.</span><span class="sxs-lookup"><span data-stu-id="4c06a-120">A parameter is not valid.</span></span> |
|`WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="4c06a-121">0x80041005</span><span class="sxs-lookup"><span data-stu-id="4c06a-121">0x80041005</span></span> | <span data-ttu-id="4c06a-122">Обнаружено несоответствие типов.</span><span class="sxs-lookup"><span data-stu-id="4c06a-122">A type mismatch occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="4c06a-123">0</span><span class="sxs-lookup"><span data-stu-id="4c06a-123">0</span></span> | <span data-ttu-id="4c06a-124">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="4c06a-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="4c06a-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="4c06a-125">Remarks</span></span>

<span data-ttu-id="4c06a-126">Эта функция завершает вызов методом [IWbemClassObject::WritePropertyValue.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue)</span><span class="sxs-lookup"><span data-stu-id="4c06a-126">This function wraps a call to the [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) method.</span></span>

<span data-ttu-id="4c06a-127">Используйте эту функцию для установки строки и всех других не-`DWORD` или не-данных.`QWORD`</span><span class="sxs-lookup"><span data-stu-id="4c06a-127">Use this function to set string and all other non-`DWORD` or non-`QWORD` data.</span></span>

<span data-ttu-id="4c06a-128">Для значений свойств, `lNumBytes` не стримных свойств, должен быть правильный размер данных указанного типа свойства.</span><span class="sxs-lookup"><span data-stu-id="4c06a-128">For nonstring property values, `lNumBytes` must be the correct data size of the property type specified.</span></span> <span data-ttu-id="4c06a-129">Для значений свойства `lNumBytes` строки должна быть длина указанной строки в байтах, а сама строка должна быть четной длины в байтах и следовать с символом с нулевым прекращением.</span><span class="sxs-lookup"><span data-stu-id="4c06a-129">For string property values, `lNumBytes` must be the length of the specified string in bytes, and the string itself must be of an even length in bytes and be followed with a null-termination character.</span></span>

## <a name="requirements"></a><span data-ttu-id="4c06a-130">Требования</span><span class="sxs-lookup"><span data-stu-id="4c06a-130">Requirements</span></span>  
<span data-ttu-id="4c06a-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c06a-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c06a-132">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4c06a-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4c06a-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4c06a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c06a-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4c06a-134">See also</span></span>

- [<span data-ttu-id="4c06a-135">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="4c06a-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
