---
title: Получить функцию (Справочник по неуправляемым API)
description: Функция Get получает значение указанного свойства.
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb7475623961fe2ee5fc821c5f237f0a2acfae1a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507666"
---
# <a name="get-function"></a><span data-ttu-id="46f34-103">Функция get</span><span class="sxs-lookup"><span data-stu-id="46f34-103">Get function</span></span>
<span data-ttu-id="46f34-104">Получает значение указанного свойства, если он существует.</span><span class="sxs-lookup"><span data-stu-id="46f34-104">Retrieves the specified property value if it exists.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="46f34-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46f34-105">Syntax</span></span>  
  
```  
HRESULT Get (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
); 
```  

## <a name="parameters"></a><span data-ttu-id="46f34-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="46f34-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="46f34-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="46f34-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="46f34-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="46f34-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="46f34-109">[in] Имя свойства.</span><span class="sxs-lookup"><span data-stu-id="46f34-109">[in] The name of the property.</span></span>

<span data-ttu-id="46f34-110">`lFlags` [in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="46f34-110">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="46f34-111">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="46f34-111">This parameter must be 0.</span></span>

<span data-ttu-id="46f34-112">`pVal` [out] Если функция возвращает успешно, содержит значение `wszName` свойства.</span><span class="sxs-lookup"><span data-stu-id="46f34-112">`pVal` [out] If the function returns successfully, contains the value of the `wszName` property.</span></span> <span data-ttu-id="46f34-113">`pval` Аргумент назначается правильный тип и значение квалификатора.</span><span class="sxs-lookup"><span data-stu-id="46f34-113">The `pval` argument is assigned the correct type and value for the qualifier.</span></span>

<span data-ttu-id="46f34-114">`pvtType` [out] Если функция возвращает успешно, содержит [тип CIM константа](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) , указывающее тип свойства.</span><span class="sxs-lookup"><span data-stu-id="46f34-114">`pvtType` [out] If the function returns successfully, contains a [CIM-type constant](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) that indicates the property type.</span></span> <span data-ttu-id="46f34-115">Его значение может также быть `null`.</span><span class="sxs-lookup"><span data-stu-id="46f34-115">Its value can also be `null`.</span></span> 

<span data-ttu-id="46f34-116">`plFlavor` [out] Если функция возвращает успешно, получает сведения о происхождении свойства.</span><span class="sxs-lookup"><span data-stu-id="46f34-116">`plFlavor` [out] If the function returns successfully, receives information about the origin of the property.</span></span> <span data-ttu-id="46f34-117">Его значение может быть `null`, или один из следующих WBEM_FLAVOR_TYPE констант, определенных в *WbemCli.h* заголовочный файл:</span><span class="sxs-lookup"><span data-stu-id="46f34-117">Its value can be `null`, or one of the following WBEM_FLAVOR_TYPE constants defined in the *WbemCli.h* header file:</span></span> 

|<span data-ttu-id="46f34-118">Константа</span><span class="sxs-lookup"><span data-stu-id="46f34-118">Constant</span></span>  |<span data-ttu-id="46f34-119">Значение</span><span class="sxs-lookup"><span data-stu-id="46f34-119">Value</span></span>  |<span data-ttu-id="46f34-120">Описание</span><span class="sxs-lookup"><span data-stu-id="46f34-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="46f34-121">0x40</span><span class="sxs-lookup"><span data-stu-id="46f34-121">0x40</span></span> | <span data-ttu-id="46f34-122">Свойство является свойством стандартной системы.</span><span class="sxs-lookup"><span data-stu-id="46f34-122">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="46f34-123">0x20</span><span class="sxs-lookup"><span data-stu-id="46f34-123">0x20</span></span> | <span data-ttu-id="46f34-124">Для класса: свойство наследуется от родительского класса.</span><span class="sxs-lookup"><span data-stu-id="46f34-124">For a class: The property is inherited from the parent class.</span></span> </br> <span data-ttu-id="46f34-125">Для экземпляра: свойство, хотя наследуется от родительского класса, не был изменен в экземпляре.</span><span class="sxs-lookup"><span data-stu-id="46f34-125">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="46f34-126">0</span><span class="sxs-lookup"><span data-stu-id="46f34-126">0</span></span> | <span data-ttu-id="46f34-127">Для класса: свойство принадлежит к производному классу.</span><span class="sxs-lookup"><span data-stu-id="46f34-127">For a class: The property belongs to the derived class.</span></span> </br> <span data-ttu-id="46f34-128">Для экземпляра: свойство изменяется в экземпляре; то есть значение было предоставлено или квалификатор был добавлен или изменен.</span><span class="sxs-lookup"><span data-stu-id="46f34-128">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="return-value"></a><span data-ttu-id="46f34-129">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="46f34-129">Return value</span></span>

<span data-ttu-id="46f34-130">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="46f34-130">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="46f34-131">Константа</span><span class="sxs-lookup"><span data-stu-id="46f34-131">Constant</span></span>  |<span data-ttu-id="46f34-132">Значение</span><span class="sxs-lookup"><span data-stu-id="46f34-132">Value</span></span>  |<span data-ttu-id="46f34-133">Описание</span><span class="sxs-lookup"><span data-stu-id="46f34-133">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="46f34-134">0x80041001</span><span class="sxs-lookup"><span data-stu-id="46f34-134">0x80041001</span></span> | <span data-ttu-id="46f34-135">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="46f34-135">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="46f34-136">0x80041008</span><span class="sxs-lookup"><span data-stu-id="46f34-136">0x80041008</span></span> | <span data-ttu-id="46f34-137">Один или несколько параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="46f34-137">One or more parameters are not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="46f34-138">0x80041002</span><span class="sxs-lookup"><span data-stu-id="46f34-138">0x80041002</span></span> | <span data-ttu-id="46f34-139">Указанное свойство не найден.</span><span class="sxs-lookup"><span data-stu-id="46f34-139">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="46f34-140">0x80041006</span><span class="sxs-lookup"><span data-stu-id="46f34-140">0x80041006</span></span> | <span data-ttu-id="46f34-141">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="46f34-141">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="46f34-142">0</span><span class="sxs-lookup"><span data-stu-id="46f34-142">0</span></span> | <span data-ttu-id="46f34-143">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="46f34-143">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="46f34-144">Примечания</span><span class="sxs-lookup"><span data-stu-id="46f34-144">Remarks</span></span>

<span data-ttu-id="46f34-145">Эта функция создает оболочку для вызова [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) метод.</span><span class="sxs-lookup"><span data-stu-id="46f34-145">This function wraps a call to the [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) method.</span></span>

<span data-ttu-id="46f34-146">`Get` Функция также может возвращать свойства системы.</span><span class="sxs-lookup"><span data-stu-id="46f34-146">The `Get` function can also return system properties.</span></span>

<span data-ttu-id="46f34-147">`pVal` Аргумент назначается правильный тип и значение для квалификатора и COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) функции</span><span class="sxs-lookup"><span data-stu-id="46f34-147">The `pVal` argument is assigned the correct type and value for the qualifier and the COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) function</span></span>

## <a name="requirements"></a><span data-ttu-id="46f34-148">Требования</span><span class="sxs-lookup"><span data-stu-id="46f34-148">Requirements</span></span>  
 <span data-ttu-id="46f34-149">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46f34-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46f34-150">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="46f34-150">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="46f34-151">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="46f34-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46f34-152">См. также</span><span class="sxs-lookup"><span data-stu-id="46f34-152">See also</span></span>  
[<span data-ttu-id="46f34-153">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="46f34-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
