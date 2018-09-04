---
title: Функция PutMethod (Справочник по неуправляемым API)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7cdf34ff6ae506ba209300685da3752820b250a2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516754"
---
# <a name="putmethod-function"></a><span data-ttu-id="d7ae8-103">Функция PutMethod</span><span class="sxs-lookup"><span data-stu-id="d7ae8-103">PutMethod function</span></span>
<span data-ttu-id="d7ae8-104">Создает метод.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="d7ae8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7ae8-105">Syntax</span></span>  
  
```  
HRESULT PutMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*  ptr, 
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
); 
```  

## <a name="parameters"></a><span data-ttu-id="d7ae8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d7ae8-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="d7ae8-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="d7ae8-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="d7ae8-109">[in] Имя метода для создания.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-109">[in] The name of the method to create.</span></span> 

`lFlags`  
<span data-ttu-id="d7ae8-110">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-110">[in] Reserved.</span></span> <span data-ttu-id="d7ae8-111">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="d7ae8-112">[in] Указатель на копию [__Parameters системный класс](/windows/desktop/WmiSdk/--parameters) , содержащий `in` параметры метода.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-112">[in] A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="d7ae8-113">Этот параметр учитывается, если значение `null`.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="d7ae8-114">[in]  Указатель на копию [__Parameters системный класс](/windows/desktop/WmiSdk/--parameters) , содержащий `out` параметры метода.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-114">[in]  A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="d7ae8-115">Этот параметр учитывается, если значение `null`.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-115">This parameter is ignored if set to `null`.</span></span>
 

## <a name="return-value"></a><span data-ttu-id="d7ae8-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d7ae8-116">Return value</span></span>

<span data-ttu-id="d7ae8-117">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="d7ae8-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d7ae8-118">Константа</span><span class="sxs-lookup"><span data-stu-id="d7ae8-118">Constant</span></span>  |<span data-ttu-id="d7ae8-119">Значение</span><span class="sxs-lookup"><span data-stu-id="d7ae8-119">Value</span></span>  |<span data-ttu-id="d7ae8-120">Описание</span><span class="sxs-lookup"><span data-stu-id="d7ae8-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="d7ae8-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="d7ae8-121">0x80041008</span></span> | <span data-ttu-id="d7ae8-122">Один или несколько параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="d7ae8-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="d7ae8-123">0x80041043</span></span> | <span data-ttu-id="d7ae8-124">`[in, out]` Параметра метода, указанных в свойствах *pInSignature* и *pOutSignature* объекты имеют разные квалификаторы.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="d7ae8-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="d7ae8-125">0x80041036</span></span> | <span data-ttu-id="d7ae8-126">Параметр метода отсутствует спецификация **идентификатор** квалификатор.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="d7ae8-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="d7ae8-127">0x80041038</span></span> | <span data-ttu-id="d7ae8-128">Серии идентификатор, присвоенный параметры метода не является последовательных или не начинаются с 0.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="d7ae8-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="d7ae8-129">0x80041039</span></span> | <span data-ttu-id="d7ae8-130">Возвращаемое значение метода имеет **идентификатор** квалификатор.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="d7ae8-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="d7ae8-131">0x80041034</span></span> | <span data-ttu-id="d7ae8-132">Была предпринята попытка повторно использовать существующее имя метода из класса-родителя, а не соответствует подписи.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="d7ae8-133">0</span><span class="sxs-lookup"><span data-stu-id="d7ae8-133">0</span></span> | <span data-ttu-id="d7ae8-134">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="d7ae8-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="d7ae8-135">Remarks</span></span>

<span data-ttu-id="d7ae8-136">Эта функция создает оболочку для вызова [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) метод.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-136">This function wraps a call to the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

<span data-ttu-id="d7ae8-137">Вызов этого метода поддерживается только в том случае, если `ptr` является определение класса CIM.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="d7ae8-138">Метод манипуляции не доступен из [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) указатели, которые указывают на экземпляры CIM.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-138">Method manipulation is not available from [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) pointers that point to CIM instances.</span></span>

<span data-ttu-id="d7ae8-139">Пользователи не могут создавать методы с именами, начинаться или заканчиваться символом подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="d7ae8-140">Этот атрибут зарезервирован для системных классов и свойств.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="d7ae8-141">Для метода `in` и `out` параметры описаны в виде свойств [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) объектов.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) objects.</span></span>

<span data-ttu-id="d7ae8-142">`[in/out]` Параметра можно определить путем добавления одного свойства обоих объектов, указываемых `pInSignature` и `pOutSignature` параметров.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="d7ae8-143">В этом случае свойства одного и того же **идентификатор** значение квалификатора.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="d7ae8-144">Каждое свойство в [__Parameters](/windows/desktop/WmiSdk/--parameters) класса объектов, отличных от `ReturnValue` должен иметь **идентификатор** квалификатор, отсчитываемый от нуля числовое значение, определяющее порядок, в котором параметры появляются.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-144">Each property in a [__Parameters](/windows/desktop/WmiSdk/--parameters) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="d7ae8-145">Нет два параметра могут иметь такой же **идентификатор** значения и **идентификатор** значение может быть пропущен.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="d7ae8-146">Если любое из этих условий, `PutMethod` возвращает `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="d7ae8-147">Пример</span><span class="sxs-lookup"><span data-stu-id="d7ae8-147">Example</span></span>

<span data-ttu-id="d7ae8-148">Например, см. в разделе [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) метод.</span><span class="sxs-lookup"><span data-stu-id="d7ae8-148">For an example, see the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="d7ae8-149">Требования</span><span class="sxs-lookup"><span data-stu-id="d7ae8-149">Requirements</span></span>  
 <span data-ttu-id="d7ae8-150">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7ae8-150">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7ae8-151">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d7ae8-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="d7ae8-152">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d7ae8-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7ae8-153">См. также</span><span class="sxs-lookup"><span data-stu-id="d7ae8-153">See also</span></span>  
[<span data-ttu-id="d7ae8-154">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="d7ae8-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
