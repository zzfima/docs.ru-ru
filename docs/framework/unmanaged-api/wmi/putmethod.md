---
title: Функция PutMethod (Неуправляемая ссылка API)
description: Функция PutMethod создает метод.
ms.date: 11/06/2017
api_name:
- PutMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutMethod
helpviewer_keywords:
- PutMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 93347b7290211b5d62829604678261fdf4da1ec3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174918"
---
# <a name="putmethod-function"></a><span data-ttu-id="a7619-103">Функция PutMethod</span><span class="sxs-lookup"><span data-stu-id="a7619-103">PutMethod function</span></span>
<span data-ttu-id="a7619-104">Создает метод.</span><span class="sxs-lookup"><span data-stu-id="a7619-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="a7619-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7619-105">Syntax</span></span>  
  
```cpp  
HRESULT PutMethod (
   [in] int                vFunc,
   [in] IWbemClassObject*  ptr,
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
);
```  

## <a name="parameters"></a><span data-ttu-id="a7619-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a7619-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="a7619-107">(в) Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="a7619-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="a7619-108">(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="a7619-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="a7619-109">(в) Название метода для создания.</span><span class="sxs-lookup"><span data-stu-id="a7619-109">[in] The name of the method to create.</span></span>

`lFlags`  
<span data-ttu-id="a7619-110">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="a7619-110">[in] Reserved.</span></span> <span data-ttu-id="a7619-111">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="a7619-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="a7619-112">(в) Указатель на копию [класса __Parameters системы,](/windows/desktop/WmiSdk/--parameters) содержащий `in` параметры для метода.</span><span class="sxs-lookup"><span data-stu-id="a7619-112">[in] A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="a7619-113">Этот параметр игнорируется, `null`если установлен на .</span><span class="sxs-lookup"><span data-stu-id="a7619-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="a7619-114">(в)  Указатель на копию [класса __Parameters системы,](/windows/desktop/WmiSdk/--parameters) содержащий `out` параметры для метода.</span><span class="sxs-lookup"><span data-stu-id="a7619-114">[in]  A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="a7619-115">Этот параметр игнорируется, `null`если установлен на .</span><span class="sxs-lookup"><span data-stu-id="a7619-115">This parameter is ignored if set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="a7619-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a7619-116">Return value</span></span>

<span data-ttu-id="a7619-117">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="a7619-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a7619-118">Постоянно</span><span class="sxs-lookup"><span data-stu-id="a7619-118">Constant</span></span>  |<span data-ttu-id="a7619-119">Значение</span><span class="sxs-lookup"><span data-stu-id="a7619-119">Value</span></span>  |<span data-ttu-id="a7619-120">Описание</span><span class="sxs-lookup"><span data-stu-id="a7619-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="a7619-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="a7619-121">0x80041008</span></span> | <span data-ttu-id="a7619-122">Один или несколько параметров недействительны.</span><span class="sxs-lookup"><span data-stu-id="a7619-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="a7619-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="a7619-123">0x80041043</span></span> | <span data-ttu-id="a7619-124">Параметр `[in, out]` метода, указанный как в объектах *pInSignature,* так и *pOutSignature,* имеет различные квалификаторы.</span><span class="sxs-lookup"><span data-stu-id="a7619-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="a7619-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="a7619-125">0x80041036</span></span> | <span data-ttu-id="a7619-126">Параметр метода отсутствует спецификация квалификатора **id.**</span><span class="sxs-lookup"><span data-stu-id="a7619-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="a7619-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="a7619-127">0x80041038</span></span> | <span data-ttu-id="a7619-128">Серия идентификаторов, присвоенная параметрам метода, не является последовательной или не начинается с 0.</span><span class="sxs-lookup"><span data-stu-id="a7619-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="a7619-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="a7619-129">0x80041039</span></span> | <span data-ttu-id="a7619-130">Значение возврата для метода имеет квалификатор **идентификатора.**</span><span class="sxs-lookup"><span data-stu-id="a7619-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="a7619-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="a7619-131">0x80041034</span></span> | <span data-ttu-id="a7619-132">Была предпринята попытка повторного использования существующего имени метода из родительского класса, и подписи не совпадают.</span><span class="sxs-lookup"><span data-stu-id="a7619-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="a7619-133">0</span><span class="sxs-lookup"><span data-stu-id="a7619-133">0</span></span> | <span data-ttu-id="a7619-134">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="a7619-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="a7619-135">Remarks</span><span class="sxs-lookup"><span data-stu-id="a7619-135">Remarks</span></span>

<span data-ttu-id="a7619-136">Эта функция завершает вызов методом [IWbemClassObject::PutMethod.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)</span><span class="sxs-lookup"><span data-stu-id="a7619-136">This function wraps a call to the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

<span data-ttu-id="a7619-137">Этот вызов метода `ptr` поддерживается только в том случае, если это определение класса CIM.</span><span class="sxs-lookup"><span data-stu-id="a7619-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="a7619-138">Манипуляция методом недоступна в указателях [IWbemClassObject,](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) которые указывают на экземпляры CIM.</span><span class="sxs-lookup"><span data-stu-id="a7619-138">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="a7619-139">Пользователи не могут создавать методы с именами, которые начинаются или заканчиваются с подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="a7619-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="a7619-140">Это зарезервировано для системных классов и свойств.</span><span class="sxs-lookup"><span data-stu-id="a7619-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="a7619-141">Для метода `in` и `out` параметры описываются как свойства в объектах [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="a7619-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objects.</span></span>

<span data-ttu-id="a7619-142">Параметр `[in/out]` может быть определен путем добавления одного `pInSignature` `pOutSignature` и того же свойства к обоим объектам, указанным по параметрам.</span><span class="sxs-lookup"><span data-stu-id="a7619-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="a7619-143">В этом случае свойства имеют одно и то же значение квалификатора **id.**</span><span class="sxs-lookup"><span data-stu-id="a7619-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="a7619-144">Каждое свойство в [объекте __Parameters](/windows/desktop/WmiSdk/--parameters) класса, кроме `ReturnValue` обязательного, имеет квалификатор **идентификатора,** нулевое числовое значение, которое определяет порядок, в котором отображаются параметры.</span><span class="sxs-lookup"><span data-stu-id="a7619-144">Each property in a [__Parameters](/windows/desktop/WmiSdk/--parameters) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="a7619-145">Нет двух параметров может иметь то же значение **id,** и значение **идентификатора** не может быть пропущено.</span><span class="sxs-lookup"><span data-stu-id="a7619-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="a7619-146">При возникновении одного `PutMethod` из `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`условий функция возвращается.</span><span class="sxs-lookup"><span data-stu-id="a7619-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="a7619-147">Пример</span><span class="sxs-lookup"><span data-stu-id="a7619-147">Example</span></span>

<span data-ttu-id="a7619-148">Например, см. метод [IWbemClassObject::PutMethod.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)</span><span class="sxs-lookup"><span data-stu-id="a7619-148">For an example, see the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="a7619-149">Требования</span><span class="sxs-lookup"><span data-stu-id="a7619-149">Requirements</span></span>  
 <span data-ttu-id="a7619-150">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7619-150">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7619-151">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="a7619-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="a7619-152">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a7619-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7619-153">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a7619-153">See also</span></span>

- [<span data-ttu-id="a7619-154">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="a7619-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
