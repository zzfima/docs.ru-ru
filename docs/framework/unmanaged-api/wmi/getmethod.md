---
title: Функция GetMethod (Справочник по неуправляемым API)
description: Функция GetMethod получает сведения о методе.
ms.date: 11/06/2017
api_name:
- GetMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethod
helpviewer_keywords:
- GetMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65b8cb74a028892a3494e818f2b523f75e8766a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460451"
---
# <a name="getmethod-function"></a><span data-ttu-id="639c8-103">GetMethod-функция</span><span class="sxs-lookup"><span data-stu-id="639c8-103">GetMethod function</span></span>
<span data-ttu-id="639c8-104">Возвращает сведения об указанном методе.</span><span class="sxs-lookup"><span data-stu-id="639c8-104">Retrieves information about the specified method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="639c8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="639c8-105">Syntax</span></span>  
  
```  
HRESULT GetMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
); 
```  

## <a name="parameters"></a><span data-ttu-id="639c8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="639c8-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="639c8-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="639c8-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="639c8-108">[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="639c8-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="639c8-109">[in] Имя метода.</span><span class="sxs-lookup"><span data-stu-id="639c8-109">[in] The method name.</span></span> <span data-ttu-id="639c8-110">Этот параметр не может быть `null` и должен указывать на допустимый `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="639c8-110">This parameter cannot be `null` and must point to a valid `LPCWSTR`.</span></span>

`lFlags`  
<span data-ttu-id="639c8-111">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="639c8-111">[in] Reserved.</span></span> <span data-ttu-id="639c8-112">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="639c8-112">This parameter must be 0.</span></span>

`ppInSignature`   
<span data-ttu-id="639c8-113">[out] Указатель на адрес [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) , описывающий в paramteers к методу экземпляра.</span><span class="sxs-lookup"><span data-stu-id="639c8-113">[out] A pointer to the address of an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance that describes the in paramteers to the method.</span></span> <span data-ttu-id="639c8-114">Этот параметр учитывается, если задано значение `null`.</span><span class="sxs-lookup"><span data-stu-id="639c8-114">This parameter is ignored if it is set to `null`.</span></span> 

`ppOutSignature`  
<span data-ttu-id="639c8-115">[out] Указатель на адрес [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляр, описывающий выходные параметры метода.</span><span class="sxs-lookup"><span data-stu-id="639c8-115">[out] A pointer to the address of an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance that describes the out parameters to the method.</span></span> <span data-ttu-id="639c8-116">Этот параметр учитывается, если задано значение `null`.</span><span class="sxs-lookup"><span data-stu-id="639c8-116">This parameter is ignored if it is set to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="639c8-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="639c8-117">Return value</span></span>

<span data-ttu-id="639c8-118">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="639c8-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="639c8-119">Константа</span><span class="sxs-lookup"><span data-stu-id="639c8-119">Constant</span></span>  |<span data-ttu-id="639c8-120">Значение</span><span class="sxs-lookup"><span data-stu-id="639c8-120">Value</span></span>  |<span data-ttu-id="639c8-121">Описание</span><span class="sxs-lookup"><span data-stu-id="639c8-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="639c8-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="639c8-122">0x80041002</span></span> | <span data-ttu-id="639c8-123">Указанное свойство не найдено.</span><span class="sxs-lookup"><span data-stu-id="639c8-123">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="639c8-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="639c8-124">0x80041006</span></span> | <span data-ttu-id="639c8-125">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="639c8-125">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="639c8-126">0</span><span class="sxs-lookup"><span data-stu-id="639c8-126">0</span></span> | <span data-ttu-id="639c8-127">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="639c8-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="639c8-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="639c8-128">Remarks</span></span>

<span data-ttu-id="639c8-129">Эта функция создает оболочку для вызова [IWbemClassObject::GetMethod](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="639c8-129">This function wraps a call to the [IWbemClassObject::GetMethod](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="639c8-130">Можно установить Windows Management [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) указатель `null` Если метод имеет входные параметры нет.</span><span class="sxs-lookup"><span data-stu-id="639c8-130">Windows Management can set the [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) pointer to `null` if the method has no in parameters.</span></span>

<span data-ttu-id="639c8-131">В `ppInSignature` и `ppOutSignature` описывают входные и выходные параметры, соответственно, как свойства в `IWbemClassObject` экземпляр класса системы [_Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="639c8-131">In `ppInSignature` and `ppOutSignature` describe in and out parameters, respectively, as properties in a `IWbemClassObject` instance of the system class [_Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx).</span></span> <span data-ttu-id="639c8-132">Свойства в `ppInsignature` именуются **Param *** n*, где *n* позиция параметра в сигнатуре метода (например, `Param1`, `Param2`и т. д.).</span><span class="sxs-lookup"><span data-stu-id="639c8-132">The properties in `ppInsignature` are named **Param***n*, where *n* is the position of the parameter in the method signature (such as `Param1`, `Param2`, etc.).</span></span> <span data-ttu-id="639c8-133">Свойства в `ppOutSignature` также называются **Param *** n*, а возвращаемое значение совпадает с именем **ReturnValue**.</span><span class="sxs-lookup"><span data-stu-id="639c8-133">The properties in `ppOutSignature` are also named **Param***n*, and the return value is named **ReturnValue**.</span></span> <span data-ttu-id="639c8-134">Дополнительные сведения и пример см. в разделе [IWbemClassObject::GetMethod метод](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="639c8-134">For more information and an example, see [IWbemClassObject::GetMethod method](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx).</span></span>

## <a name="requirements"></a><span data-ttu-id="639c8-135">Требования</span><span class="sxs-lookup"><span data-stu-id="639c8-135">Requirements</span></span>  
<span data-ttu-id="639c8-136">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="639c8-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="639c8-137">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="639c8-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="639c8-138">**Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="639c8-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="639c8-139">См. также</span><span class="sxs-lookup"><span data-stu-id="639c8-139">See also</span></span>  
[<span data-ttu-id="639c8-140">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="639c8-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
