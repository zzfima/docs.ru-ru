---
title: "Функция PutMethod (Справочник по неуправляемым API)"
description: "Функция PutMethod создает метод."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: PutMethod
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: PutMethod
helpviewer_keywords: PutMethod function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7e97ffcf44a738234f67d9736382c46c42e5b61e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="putmethod-function"></a><span data-ttu-id="1bbc4-103">Функция PutMethod</span><span class="sxs-lookup"><span data-stu-id="1bbc4-103">PutMethod function</span></span>
<span data-ttu-id="1bbc4-104">Создает метод.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="1bbc4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1bbc4-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="1bbc4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1bbc4-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="1bbc4-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="1bbc4-108">[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="1bbc4-109">[in] Имя метода для создания.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-109">[in] The name of the method to create.</span></span> 

`lFlags`  
<span data-ttu-id="1bbc4-110">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-110">[in] Reserved.</span></span> <span data-ttu-id="1bbc4-111">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="1bbc4-112">[in] Указатель на копию [__Parameters системный класс](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) , содержащий `in` параметры для метода.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-112">[in] A pointer to a copy of the [__Parameters system class](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="1bbc4-113">Этот параметр учитывается, если значение `null`.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="1bbc4-114">[in]  Указатель на копию [__Parameters системный класс](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) , содержащий `out` параметры для метода.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-114">[in]  A pointer to a copy of the [__Parameters system class](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="1bbc4-115">Этот параметр учитывается, если значение `null`.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-115">This parameter is ignored if set to `null`.</span></span>
 

## <a name="return-value"></a><span data-ttu-id="1bbc4-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1bbc4-116">Return value</span></span>

<span data-ttu-id="1bbc4-117">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="1bbc4-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1bbc4-118">Константа</span><span class="sxs-lookup"><span data-stu-id="1bbc4-118">Constant</span></span>  |<span data-ttu-id="1bbc4-119">Значение</span><span class="sxs-lookup"><span data-stu-id="1bbc4-119">Value</span></span>  |<span data-ttu-id="1bbc4-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="1bbc4-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1bbc4-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1bbc4-121">0x80041008</span></span> | <span data-ttu-id="1bbc4-122">Один или несколько параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="1bbc4-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="1bbc4-123">0x80041043</span></span> | <span data-ttu-id="1bbc4-124">`[in, out]` Параметра метода, указанного в оба *pInSignature* и *pOutSignature* объекты имеют разные квалификаторы.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="1bbc4-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="1bbc4-125">0x80041036</span></span> | <span data-ttu-id="1bbc4-126">Параметр метода отсутствует спецификация **идентификатор** квалификатор.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="1bbc4-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="1bbc4-127">0x80041038</span></span> | <span data-ttu-id="1bbc4-128">Ряд идентификатор, присвоенный параметры метода не последовательных или не начинается с 0.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="1bbc4-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="1bbc4-129">0x80041039</span></span> | <span data-ttu-id="1bbc4-130">Возвращаемое значение метода имеет **идентификатор** квалификатор.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="1bbc4-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="1bbc4-131">0x80041034</span></span> | <span data-ttu-id="1bbc4-132">Была предпринята попытка повторно использовать существующее имя метода из родительского класса, а не соответствует подписи.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="1bbc4-133">0</span><span class="sxs-lookup"><span data-stu-id="1bbc4-133">0</span></span> | <span data-ttu-id="1bbc4-134">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="1bbc4-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="1bbc4-135">Remarks</span></span>

<span data-ttu-id="1bbc4-136">Эта функция создает оболочку для вызова [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-136">This function wraps a call to the [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="1bbc4-137">Вызов этого метода поддерживается только в том случае, если `ptr` является определение класса CIM.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="1bbc4-138">Метод обработки не доступен из [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) указателей, указывающих на экземпляры CIM.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-138">Method manipulation is not available from [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) pointers that point to CIM instances.</span></span>

<span data-ttu-id="1bbc4-139">Пользователи не могут создавать методы с именами, начинаться или заканчиваться символом подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="1bbc4-140">Данное свойство зарезервировано для системных классов и свойств.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="1bbc4-141">Для метода `in` и `out` параметры описаны как свойства в [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) объектов.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) objects.</span></span>

<span data-ttu-id="1bbc4-142">`[in/out]` Параметра можно определить путем добавления и то же свойство для обоих объектов, указываемых `pInSignature` и `pOutSignature` параметров.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="1bbc4-143">В этом случае свойства того же **идентификатор** значение квалификатора.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="1bbc4-144">Каждое свойство в [__Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) класса объекта, отличного от `ReturnValue` должен иметь **идентификатор** квалификатор, отсчитываемый от нуля числовое значение, определяющее порядок, в котором параметры появляются.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-144">Each property in a [__Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="1bbc4-145">Нет два параметра может иметь такой же **идентификатор** значение и нет **идентификатор** значение может быть пропущен.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="1bbc4-146">Если любое из этих условий `PutMethod` возврата функцией `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="1bbc4-147">Пример</span><span class="sxs-lookup"><span data-stu-id="1bbc4-147">Example</span></span>

<span data-ttu-id="1bbc4-148">Пример см. в разделе [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-148">For an example, see the [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="1bbc4-149">Требования</span><span class="sxs-lookup"><span data-stu-id="1bbc4-149">Requirements</span></span>  
 <span data-ttu-id="1bbc4-150">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bbc4-150">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bbc4-151">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1bbc4-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1bbc4-152">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1bbc4-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bbc4-153">См. также</span><span class="sxs-lookup"><span data-stu-id="1bbc4-153">See also</span></span>  
[<span data-ttu-id="1bbc4-154">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="1bbc4-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
