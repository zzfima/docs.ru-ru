---
title: Функция PUT (Справочник по неуправляемым API)
description: Функция Put присваивает новое значение именованного свойства.
ms.date: 11/06/2017
api_name:
- Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Put
helpviewer_keywords:
- Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c37bae87f56745cf75031923db820ec2439fe04
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625774"
---
# <a name="put-function"></a><span data-ttu-id="e2cec-103">Функция PUT</span><span class="sxs-lookup"><span data-stu-id="e2cec-103">Put function</span></span>
<span data-ttu-id="e2cec-104">Задает новое значение для именованного свойства.</span><span class="sxs-lookup"><span data-stu-id="e2cec-104">Sets a named property to a new value.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="e2cec-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2cec-105">Syntax</span></span>  
  
```  
HRESULT Put (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
); 
```  

## <a name="parameters"></a><span data-ttu-id="e2cec-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e2cec-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e2cec-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="e2cec-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="e2cec-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="e2cec-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="e2cec-109">[in] Имя свойства.</span><span class="sxs-lookup"><span data-stu-id="e2cec-109">[in] The name of the property.</span></span> <span data-ttu-id="e2cec-110">Этот параметр не может быть `null`.</span><span class="sxs-lookup"><span data-stu-id="e2cec-110">This parameter cannot be `null`.</span></span>

`lFlags`  
<span data-ttu-id="e2cec-111">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="e2cec-111">[in] Reserved.</span></span> <span data-ttu-id="e2cec-112">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="e2cec-112">This parameter must be 0.</span></span>

`pVal`   
<span data-ttu-id="e2cec-113">[in] Указатель на допустимую `VARIANT` , становится новым значением свойства.</span><span class="sxs-lookup"><span data-stu-id="e2cec-113">[in] A pointer to a valid `VARIANT` that becomes the new property value.</span></span> <span data-ttu-id="e2cec-114">Если `pVal` — `null` или указывает на `VARIANT` типа `VT_NULL`, свойство имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="e2cec-114">If `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`, the property is set to `null`.</span></span> 

`vtType`  
<span data-ttu-id="e2cec-115">[in] Тип `VARIANT` , на которые указывают `pVal`.</span><span class="sxs-lookup"><span data-stu-id="e2cec-115">[in] The type of `VARIANT` pointed to by `pVal`.</span></span> <span data-ttu-id="e2cec-116">См. в разделе ["Примечания"](#remarks) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="e2cec-116">See the [Remarks](#remarks) section for more information.</span></span>
 

## <a name="return-value"></a><span data-ttu-id="e2cec-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e2cec-117">Return value</span></span>

<span data-ttu-id="e2cec-118">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="e2cec-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e2cec-119">Константа</span><span class="sxs-lookup"><span data-stu-id="e2cec-119">Constant</span></span>  |<span data-ttu-id="e2cec-120">Значение</span><span class="sxs-lookup"><span data-stu-id="e2cec-120">Value</span></span>  |<span data-ttu-id="e2cec-121">Описание</span><span class="sxs-lookup"><span data-stu-id="e2cec-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="e2cec-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="e2cec-122">0x80041001</span></span> | <span data-ttu-id="e2cec-123">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="e2cec-123">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e2cec-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e2cec-124">0x80041008</span></span> | <span data-ttu-id="e2cec-125">Один или несколько параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="e2cec-125">One or more parameters are not valid.</span></span> |
|`WBEM_E_INVALID_PROPERTY_TYPE` | <span data-ttu-id="e2cec-126">0x8004102a</span><span class="sxs-lookup"><span data-stu-id="e2cec-126">0x8004102a</span></span> | <span data-ttu-id="e2cec-127">Тип свойства не распознан.</span><span class="sxs-lookup"><span data-stu-id="e2cec-127">The property type is not recognized.</span></span> <span data-ttu-id="e2cec-128">Это значение возвращается в том случае, если при создании экземпляров класса класс уже существует.</span><span class="sxs-lookup"><span data-stu-id="e2cec-128">This value is returned when creating class instances if the class already exists.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e2cec-129">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e2cec-129">0x80041006</span></span> | <span data-ttu-id="e2cec-130">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="e2cec-130">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="e2cec-131">0x80041005</span><span class="sxs-lookup"><span data-stu-id="e2cec-131">0x80041005</span></span> | <span data-ttu-id="e2cec-132">Для экземпляров: Указывает, что `pVal` указывает `VARIANT` неверного типа для свойства.</span><span class="sxs-lookup"><span data-stu-id="e2cec-132">For instances: Indicates that `pVal` points to a `VARIANT` of an incorrect type for the property.</span></span> <br/> <span data-ttu-id="e2cec-133">Для определения класса: Свойство уже существует в родительском классе, и новый тип COM отличается от старого COM-типом.</span><span class="sxs-lookup"><span data-stu-id="e2cec-133">For class definitions: The property already exists in the parent class, and the new COM type is different from the old COM type.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e2cec-134">0</span><span class="sxs-lookup"><span data-stu-id="e2cec-134">0</span></span> | <span data-ttu-id="e2cec-135">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="e2cec-135">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="e2cec-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="e2cec-136">Remarks</span></span>

<span data-ttu-id="e2cec-137">Эта функция создает оболочку для вызова [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) метод.</span><span class="sxs-lookup"><span data-stu-id="e2cec-137">This function wraps a call to the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

<span data-ttu-id="e2cec-138">Эта функция всегда перезаписывает его текущее значение свойства.</span><span class="sxs-lookup"><span data-stu-id="e2cec-138">This function always overwrites the current property value with a new one.</span></span> <span data-ttu-id="e2cec-139">Если [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) указывает на определение класса `Put` создает или обновляет значение свойства.</span><span class="sxs-lookup"><span data-stu-id="e2cec-139">If the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a class definition, `Put` creates or updates the property value.</span></span> <span data-ttu-id="e2cec-140">Когда [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) указывает на экземпляр CIM `Put` обновляет значение свойства. `Put` не удается создать значение свойства.</span><span class="sxs-lookup"><span data-stu-id="e2cec-140">When [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a CIM instance, `Put` updates the property value only; `Put` cannot create a property value.</span></span>

<span data-ttu-id="e2cec-141">`__CLASS` Системное свойство только для записи во время создания класса, когда он может не быть пустым.</span><span class="sxs-lookup"><span data-stu-id="e2cec-141">The `__CLASS` system property is only writable during class creation, when it may not be left blank.</span></span> <span data-ttu-id="e2cec-142">Все остальные свойства системы доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="e2cec-142">All other system properties are read-only.</span></span>

<span data-ttu-id="e2cec-143">Пользователь не может создавать свойства с именами, начинаться или заканчиваться символ подчеркивания («_»).</span><span class="sxs-lookup"><span data-stu-id="e2cec-143">A user cannot create properties with names that begin or end with an underscore ("_").</span></span> <span data-ttu-id="e2cec-144">Этот атрибут зарезервирован для системных классов и свойств.</span><span class="sxs-lookup"><span data-stu-id="e2cec-144">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="e2cec-145">Если свойство задано `Put` функция существует в родительском классе, по умолчанию значение свойства изменяется в том случае, если тип свойства не соответствует типу класса родительского.</span><span class="sxs-lookup"><span data-stu-id="e2cec-145">If the property set by the `Put` function exists in the parent class, the default value of the property is changed unless the property type does not match the parent class type.</span></span> <span data-ttu-id="e2cec-146">Если свойство не существует и не является несоответствие типов, свойство является созданный.</span><span class="sxs-lookup"><span data-stu-id="e2cec-146">If the property does not exist and it is not a type mismatch, the property is ceated.</span></span>

<span data-ttu-id="e2cec-147">Используйте `vtType` параметр только в том случае, при создании новых свойств в определении класса CIM и `pVal` — `null` или указывает на `VARIANT` типа `VT_NULL`.</span><span class="sxs-lookup"><span data-stu-id="e2cec-147">Use the `vtType` parameter only when creating new properties in a CIM class definition and `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`.</span></span> <span data-ttu-id="e2cec-148">В этом случае `vType` параметр указывает тип CIM данного свойства.</span><span class="sxs-lookup"><span data-stu-id="e2cec-148">In this case, the `vType` parameter specifies the CIM type of the property.</span></span> <span data-ttu-id="e2cec-149">Во всех остальных случаях `vtType` должно быть равно 0.</span><span class="sxs-lookup"><span data-stu-id="e2cec-149">In every other case, `vtType` must be 0.</span></span> <span data-ttu-id="e2cec-150">`vtType` также должен быть равен 0, если базовый объект является экземпляром (даже если `Val` — `null`), так как тип свойства является фиксированным и его нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="e2cec-150">`vtType` must also be 0 if the underlying object is an instance (even if `Val` is `null`) because the type of the property is fixed and cannot be changed.</span></span>   

## <a name="example"></a><span data-ttu-id="e2cec-151">Пример</span><span class="sxs-lookup"><span data-stu-id="e2cec-151">Example</span></span>

<span data-ttu-id="e2cec-152">Например, см. в разделе [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) метод.</span><span class="sxs-lookup"><span data-stu-id="e2cec-152">For an example, see the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="e2cec-153">Требования</span><span class="sxs-lookup"><span data-stu-id="e2cec-153">Requirements</span></span>  
 <span data-ttu-id="e2cec-154">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2cec-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2cec-155">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e2cec-155">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e2cec-156">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e2cec-156">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2cec-157">См. также</span><span class="sxs-lookup"><span data-stu-id="e2cec-157">See also</span></span>
- [<span data-ttu-id="e2cec-158">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="e2cec-158">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
