---
title: "Функция GetPropertyQualifierSet (Справочник по неуправляемым API)"
description: "Функция GetPropertyQualifierSet получает квалификатор для свойства."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetPropertyQualifierSet
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetPropertyQualifierSet
helpviewer_keywords: GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ca2981c8833abaafd5d206b66d6e91f34e2c91d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="getpropertyqualifierset-function"></a><span data-ttu-id="33278-103">Функция GetPropertyQualifierSet</span><span class="sxs-lookup"><span data-stu-id="33278-103">GetPropertyQualifierSet function</span></span>
<span data-ttu-id="33278-104">Извлекает квалификатор для конкретного свойства.</span><span class="sxs-lookup"><span data-stu-id="33278-104">Retrieves the qualifier set for a particular property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="33278-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33278-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="33278-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="33278-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="33278-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="33278-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="33278-108">[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="33278-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethod`  
<span data-ttu-id="33278-109">[in] Имя свойства.</span><span class="sxs-lookup"><span data-stu-id="33278-109">[in] The property  name.</span></span> <span data-ttu-id="33278-110">`wszProperty`должен указывать на допустимый `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="33278-110">`wszProperty` must point to a valid `LPCWSTR`.</span></span> 

`ppQualSet`  
<span data-ttu-id="33278-111">[out] Получает указатель интерфейса, обеспечивающего доступ к квалификаторы свойства.</span><span class="sxs-lookup"><span data-stu-id="33278-111">[out] Receives the interface pointer that allows access to the qualifiers of the property.</span></span> <span data-ttu-id="33278-112">Параметр `ppQualSet` не может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="33278-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="33278-113">Если возникает ошибка не возвращается новый объект и указатель устанавливается на `null`.</span><span class="sxs-lookup"><span data-stu-id="33278-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="33278-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="33278-114">Return value</span></span>

<span data-ttu-id="33278-115">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="33278-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="33278-116">Константа</span><span class="sxs-lookup"><span data-stu-id="33278-116">Constant</span></span>  |<span data-ttu-id="33278-117">Значение</span><span class="sxs-lookup"><span data-stu-id="33278-117">Value</span></span>  |<span data-ttu-id="33278-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="33278-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="33278-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="33278-119">0x80041001</span></span> | <span data-ttu-id="33278-120">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="33278-120">There has been a general failure.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="33278-121">0x80041002</span><span class="sxs-lookup"><span data-stu-id="33278-121">0x80041002</span></span> | <span data-ttu-id="33278-122">Указанный метод не существует.</span><span class="sxs-lookup"><span data-stu-id="33278-122">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="33278-123">0x80041006</span><span class="sxs-lookup"><span data-stu-id="33278-123">0x80041006</span></span> | <span data-ttu-id="33278-124">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="33278-124">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="33278-125">0x80041008</span><span class="sxs-lookup"><span data-stu-id="33278-125">0x80041008</span></span> | <span data-ttu-id="33278-126">Параметр — `null`.</span><span class="sxs-lookup"><span data-stu-id="33278-126">A parameter is `null`.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | <span data-ttu-id="33278-127">0x80041030</span><span class="sxs-lookup"><span data-stu-id="33278-127">0x80041030</span></span> | <span data-ttu-id="33278-128">Функция пытается получить квалификаторы для системного свойства.</span><span class="sxs-lookup"><span data-stu-id="33278-128">The function attempts to get qualifiers of a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="33278-129">0</span><span class="sxs-lookup"><span data-stu-id="33278-129">0</span></span> | <span data-ttu-id="33278-130">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="33278-130">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="33278-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="33278-131">Remarks</span></span>

<span data-ttu-id="33278-132">Эта функция создает оболочку для вызова [IWbemClassObject::GetPropertyQualifierSet](https://msdn.microsoft.com/library/aa391450(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="33278-132">This function wraps a call to the [IWbemClassObject::GetPropertyQualifierSet](https://msdn.microsoft.com/library/aa391450(v=vs.85).aspx) method.</span></span> 

<span data-ttu-id="33278-133">Вызов эта функция поддерживается только в том случае, если текущий объект является определение класса CIM.</span><span class="sxs-lookup"><span data-stu-id="33278-133">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="33278-134">Метод обработки не доступен для [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters, указывают на экземпляры CIM.</span><span class="sxs-lookup"><span data-stu-id="33278-134">Method manipulation is not available for [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters that point to CIM instances.</span></span>

<span data-ttu-id="33278-135">Так как каждый метод может иметь свой собственный квалификаторы [IWbemQualifierSet указатель](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) позволяет вызывающему объекту добавить, изменить или удалить эти квалификаторы.</span><span class="sxs-lookup"><span data-stu-id="33278-135">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) lets the caller add, edit, or delete these qualifiers.</span></span>

<span data-ttu-id="33278-136">Поскольку свойства системы без квалификаторов, функция возвращает `WBEM_E_SYSTEM_PROPERTY` при попытке получить [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) указатель для системного свойства.</span><span class="sxs-lookup"><span data-stu-id="33278-136">Because system properties have no qualifiers, the function returns `WBEM_E_SYSTEM_PROPERTY` if you attempt to obtain a [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) pointer for a system property.</span></span>

## <a name="requirements"></a><span data-ttu-id="33278-137">Требования</span><span class="sxs-lookup"><span data-stu-id="33278-137">Requirements</span></span>  
<span data-ttu-id="33278-138">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33278-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33278-139">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="33278-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="33278-140">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="33278-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33278-141">См. также</span><span class="sxs-lookup"><span data-stu-id="33278-141">See also</span></span>  
[<span data-ttu-id="33278-142">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="33278-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
