---
title: "Функция GetPropertyHandle (Справочник по неуправляемым API)"
description: "Функция GetPropertyHandle возвращает уникальный дескриптор этого свойства удостоверения."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetPropertyHandle
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetPropertyHandle
helpviewer_keywords: GetPropertyHandle function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ab3df6d2233059de76036da7ff27f5cc1808aaf
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="5cbc5-103">Функция GetPropertyHandle</span><span class="sxs-lookup"><span data-stu-id="5cbc5-103">GetPropertyHandle function</span></span>
<span data-ttu-id="5cbc5-104">Возвращает уникальный дескриптор, который определяет свойство.</span><span class="sxs-lookup"><span data-stu-id="5cbc5-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="5cbc5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5cbc5-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyHandle (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
); 
```  

## <a name="parameters"></a><span data-ttu-id="5cbc5-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5cbc5-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="5cbc5-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="5cbc5-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="5cbc5-108">[in] Указатель на [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="5cbc5-108">[in] A pointer to an [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) instance.</span></span>

`wszPropertyName`  
<span data-ttu-id="5cbc5-109">[in] Нулем строка кодировки UTF16 знака, содержащее имя свойства.</span><span class="sxs-lookup"><span data-stu-id="5cbc5-109">[in] A null-terminated string of UTF16-encoded characaters that contains the property name.</span></span>   

`pType`  
<span data-ttu-id="5cbc5-110">[out] Указатель на [ `CIMTYPE` ](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) член перечисления, представляющее CIM-тип свойства.</span><span class="sxs-lookup"><span data-stu-id="5cbc5-110">[out] A pointer to a [`CIMTYPE`](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`   
<span data-ttu-id="5cbc5-111">[out] Указатель на целое число, содержащее дескриптор свойства.</span><span class="sxs-lookup"><span data-stu-id="5cbc5-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="5cbc5-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5cbc5-112">Return value</span></span>

<span data-ttu-id="5cbc5-113">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="5cbc5-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5cbc5-114">Константа</span><span class="sxs-lookup"><span data-stu-id="5cbc5-114">Constant</span></span>  |<span data-ttu-id="5cbc5-115">Значение</span><span class="sxs-lookup"><span data-stu-id="5cbc5-115">Value</span></span>  |<span data-ttu-id="5cbc5-116">Описание</span><span class="sxs-lookup"><span data-stu-id="5cbc5-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="5cbc5-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="5cbc5-117">0x80041002</span></span> | <span data-ttu-id="5cbc5-118">Указанное имя свойства не найден.</span><span class="sxs-lookup"><span data-stu-id="5cbc5-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5cbc5-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5cbc5-119">0x80041008</span></span> | <span data-ttu-id="5cbc5-120">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="5cbc5-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="5cbc5-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="5cbc5-121">0x8004100c</span></span> | <span data-ttu-id="5cbc5-122">Запрошенное свойство имеет тип, `CIM_OBJECT` или `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="5cbc5-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="5cbc5-123">0</span><span class="sxs-lookup"><span data-stu-id="5cbc5-123">0</span></span> | <span data-ttu-id="5cbc5-124">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="5cbc5-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="5cbc5-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="5cbc5-125">Remarks</span></span>

<span data-ttu-id="5cbc5-126">Эта функция создает оболочку для вызова [IWbemClassObject::GetPropertyHandle](https://msdn.microsoft.com/library/aa391771(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="5cbc5-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](https://msdn.microsoft.com/library/aa391771(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="5cbc5-127">Этот дескриптор можно использовать для идентификации свойств, при использовании [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) методы для чтения или записи значения свойств.</span><span class="sxs-lookup"><span data-stu-id="5cbc5-127">You can use this handle to identify properties when using  [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) methods to read or write property values.</span></span>

<span data-ttu-id="5cbc5-128">Дескрипторы может быть извлечен для свойства всех типов данных, отличный от `CIM_OBJECT` и `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="5cbc5-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="5cbc5-129">Возвращенная работу дескрипторы для всех экземпляров класса.</span><span class="sxs-lookup"><span data-stu-id="5cbc5-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="5cbc5-130">Требования</span><span class="sxs-lookup"><span data-stu-id="5cbc5-130">Requirements</span></span>  
<span data-ttu-id="5cbc5-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cbc5-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cbc5-132">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="5cbc5-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="5cbc5-133">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5cbc5-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cbc5-134">См. также</span><span class="sxs-lookup"><span data-stu-id="5cbc5-134">See also</span></span>  
[<span data-ttu-id="5cbc5-135">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="5cbc5-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
