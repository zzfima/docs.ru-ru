---
title: "Функция Next (Справочник по неуправляемым API)"
description: "Далее функция retireves далее свойства перечисления."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Next
helpviewer_keywords:
- Next function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e59ef3f65b75a91708dc65f7d4e3d811dc2d3f9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="next-function"></a><span data-ttu-id="0bf62-103">Функция Next</span><span class="sxs-lookup"><span data-stu-id="0bf62-103">Next function</span></span>
<span data-ttu-id="0bf62-104">Извлекает свойство next в перечисление, которое начинается с вызова [BeginEnumeration](beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="0bf62-104">Retrieves the next property in an enumeration that begins with a call to [BeginEnumeration](beginenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="0bf62-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0bf62-105">Syntax</span></span>  
  
```  
HRESULT Next (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lFlags,
   [out] BSTR*            pstrName,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor     
); 
```  

## <a name="parameters"></a><span data-ttu-id="0bf62-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0bf62-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="0bf62-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="0bf62-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="0bf62-108">[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0bf62-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="0bf62-109">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="0bf62-109">[in] Reserved.</span></span> <span data-ttu-id="0bf62-110">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="0bf62-110">This parameter must be 0.</span></span>

`pstrName`  
<span data-ttu-id="0bf62-111">[out] Новый `BSTR` , содержащий имя свойства.</span><span class="sxs-lookup"><span data-stu-id="0bf62-111">[out] A new `BSTR` that contains the property name.</span></span> <span data-ttu-id="0bf62-112">Этот параметр можно задавать `null` Если имя не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="0bf62-112">You can set this parameter to `null` if the name is not required.</span></span>

`pVal`  
<span data-ttu-id="0bf62-113">[out] Объект `VARIANT` заполняются значением свойства.</span><span class="sxs-lookup"><span data-stu-id="0bf62-113">[out] A `VARIANT` filled with the value of the property.</span></span> <span data-ttu-id="0bf62-114">Этот параметр можно задавать `null` Если значение не требуется.</span><span class="sxs-lookup"><span data-stu-id="0bf62-114">You can set this parameter to `null` if the value is not required.</span></span> <span data-ttu-id="0bf62-115">Если функция возвращает код ошибки `VARIANT` передаваемый `pVal` влево без изменений.</span><span class="sxs-lookup"><span data-stu-id="0bf62-115">If the function returns an error code, the `VARIANT` passed to `pVal` is left unmodified.</span></span> 

`pvtType`  
<span data-ttu-id="0bf62-116">[out] Указатель на `CIMTYPE` переменной ( `LONG` в который помещается тип свойства).</span><span class="sxs-lookup"><span data-stu-id="0bf62-116">[out] A pointer to a `CIMTYPE` variable (a `LONG` into which the type of the property is placed).</span></span> <span data-ttu-id="0bf62-117">Значение этого свойства может быть `VT_NULL_VARIANT`, в этом случае необходимо определить фактический тип свойства.</span><span class="sxs-lookup"><span data-stu-id="0bf62-117">The value of this property can be a `VT_NULL_VARIANT`, in which case it is necessary to determine the actual type of the property.</span></span> <span data-ttu-id="0bf62-118">Этот параметр также может быть `null`.</span><span class="sxs-lookup"><span data-stu-id="0bf62-118">This parameter can also be `null`.</span></span> 

`plFlavor`  
<span data-ttu-id="0bf62-119">[out] `null`, или значение, которое получает сведения об источнике свойства.</span><span class="sxs-lookup"><span data-stu-id="0bf62-119">[out] `null`, or a value that receives information on the origin of the property.</span></span> <span data-ttu-id="0bf62-120">В разделе [Примечание] для возможных значений.</span><span class="sxs-lookup"><span data-stu-id="0bf62-120">See the [Remarks] section for possible values.</span></span> 

## <a name="return-value"></a><span data-ttu-id="0bf62-121">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0bf62-121">Return value</span></span>

<span data-ttu-id="0bf62-122">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="0bf62-122">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0bf62-123">Константа</span><span class="sxs-lookup"><span data-stu-id="0bf62-123">Constant</span></span>  |<span data-ttu-id="0bf62-124">Значение</span><span class="sxs-lookup"><span data-stu-id="0bf62-124">Value</span></span>  |<span data-ttu-id="0bf62-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="0bf62-125">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="0bf62-126">0x80041001</span><span class="sxs-lookup"><span data-stu-id="0bf62-126">0x80041001</span></span> | <span data-ttu-id="0bf62-127">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="0bf62-127">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0bf62-128">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0bf62-128">0x80041008</span></span> | <span data-ttu-id="0bf62-129">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="0bf62-129">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="0bf62-130">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="0bf62-130">0x8004101d</span></span> | <span data-ttu-id="0bf62-131">Был не вызов [ `BeginEnumeration` ](beginenumeration.md) функции.</span><span class="sxs-lookup"><span data-stu-id="0bf62-131">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0bf62-132">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0bf62-132">0x80041006</span></span> | <span data-ttu-id="0bf62-133">Чтобы начать новое перечисление доступен не хватает памяти.</span><span class="sxs-lookup"><span data-stu-id="0bf62-133">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="0bf62-134">0x80041015</span><span class="sxs-lookup"><span data-stu-id="0bf62-134">0x80041015</span></span> | <span data-ttu-id="0bf62-135">Удаленный вызов процедур в диапазоне от текущего процесса и управления Windows не удалось.</span><span class="sxs-lookup"><span data-stu-id="0bf62-135">The remote procedure call betweeen the current process and Windows Management failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="0bf62-136">0</span><span class="sxs-lookup"><span data-stu-id="0bf62-136">0</span></span> | <span data-ttu-id="0bf62-137">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="0bf62-137">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="0bf62-138">0x40005</span><span class="sxs-lookup"><span data-stu-id="0bf62-138">0x40005</span></span> | <span data-ttu-id="0bf62-139">Нет дополнительных свойств в перечислении.</span><span class="sxs-lookup"><span data-stu-id="0bf62-139">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="0bf62-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="0bf62-140">Remarks</span></span>

<span data-ttu-id="0bf62-141">Эта функция создает оболочку для вызова [IWbemClassObject::Next](https://msdn.microsoft.com/library/aa391453(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="0bf62-141">This function wraps a call to the [IWbemClassObject::Next](https://msdn.microsoft.com/library/aa391453(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="0bf62-142">Этот метод также возвращает системные свойства.</span><span class="sxs-lookup"><span data-stu-id="0bf62-142">This method also returns system properties.</span></span>

<span data-ttu-id="0bf62-143">Если базовый тип свойства является путь к объекту, даты или времени или другой специальный тип, возвращаемый тип не содержит достаточно информации.</span><span class="sxs-lookup"><span data-stu-id="0bf62-143">If the underlying type of the property is an object path, a date or time, or another special type, then the returned type does not contain enough information.</span></span> <span data-ttu-id="0bf62-144">Вызывающий объект должен проверить `CIMTYPE` для заданного свойства определить, является ли свойство ссылку на объект, даты или времени или другой специальный тип.</span><span class="sxs-lookup"><span data-stu-id="0bf62-144">The caller must examine the `CIMTYPE` for the specified property to determine if the property is an object reference, a date or time, or another special type.</span></span>

<span data-ttu-id="0bf62-145">Если `plFlavor` не `null`, `LONG` значение получает информацию о происхождении свойства следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0bf62-145">If `plFlavor` is not `null`, the `LONG` value receives information about the origin of the property, as follows:</span></span>

|<span data-ttu-id="0bf62-146">Константа</span><span class="sxs-lookup"><span data-stu-id="0bf62-146">Constant</span></span>  |<span data-ttu-id="0bf62-147">Значение</span><span class="sxs-lookup"><span data-stu-id="0bf62-147">Value</span></span>  |<span data-ttu-id="0bf62-148">Описание:</span><span class="sxs-lookup"><span data-stu-id="0bf62-148">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="0bf62-149">0x40</span><span class="sxs-lookup"><span data-stu-id="0bf62-149">0x40</span></span> | <span data-ttu-id="0bf62-150">Свойство является свойством стандартной системы.</span><span class="sxs-lookup"><span data-stu-id="0bf62-150">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="0bf62-151">0x20</span><span class="sxs-lookup"><span data-stu-id="0bf62-151">0x20</span></span> | <span data-ttu-id="0bf62-152">Для класса: свойство наследуется от родительского класса.</span><span class="sxs-lookup"><span data-stu-id="0bf62-152">For a class: The property is inherited from the parent class.</span></span> </br> <span data-ttu-id="0bf62-153">Для экземпляра: свойство, пока наследуется от родительского класса, не был изменен в экземпляре.</span><span class="sxs-lookup"><span data-stu-id="0bf62-153">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="0bf62-154">0</span><span class="sxs-lookup"><span data-stu-id="0bf62-154">0</span></span> | <span data-ttu-id="0bf62-155">Для класса: свойство принадлежит производного класса.</span><span class="sxs-lookup"><span data-stu-id="0bf62-155">For a class: The property belongs to the derived class.</span></span> </br> <span data-ttu-id="0bf62-156">Для экземпляра: свойство изменяется в экземпляре; то есть указано значение или квалификатор была добавлена или изменена.</span><span class="sxs-lookup"><span data-stu-id="0bf62-156">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="requirements"></a><span data-ttu-id="0bf62-157">Требования</span><span class="sxs-lookup"><span data-stu-id="0bf62-157">Requirements</span></span>  
 <span data-ttu-id="0bf62-158">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bf62-158">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bf62-159">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="0bf62-159">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="0bf62-160">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0bf62-160">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bf62-161">См. также</span><span class="sxs-lookup"><span data-stu-id="0bf62-161">See also</span></span>  
[<span data-ttu-id="0bf62-162">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="0bf62-162">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
