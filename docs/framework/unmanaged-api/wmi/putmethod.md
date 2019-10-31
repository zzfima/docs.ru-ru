---
title: Функция Путмесод (Справочник по неуправляемым API)
description: Функция Путмесод создает метод.
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
ms.openlocfilehash: 1d409507de593cf198fe87340eece6820eaefc63
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127335"
---
# <a name="putmethod-function"></a><span data-ttu-id="5a1cc-103">Функция Путмесод</span><span class="sxs-lookup"><span data-stu-id="5a1cc-103">PutMethod function</span></span>
<span data-ttu-id="5a1cc-104">Создает метод.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="5a1cc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a1cc-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="5a1cc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5a1cc-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="5a1cc-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="5a1cc-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="5a1cc-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="5a1cc-109">окне Имя создаваемого метода.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-109">[in] The name of the method to create.</span></span> 

`lFlags`  
<span data-ttu-id="5a1cc-110">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-110">[in] Reserved.</span></span> <span data-ttu-id="5a1cc-111">Этот параметр должен иметь значение 0.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="5a1cc-112">окне Указатель на копию [системного класса __Parameters](/windows/desktop/WmiSdk/--parameters) , которая содержит параметры `in` для метода.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-112">[in] A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="5a1cc-113">Этот параметр игнорируется, если имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="5a1cc-114">окне  Указатель на копию [системного класса __Parameters](/windows/desktop/WmiSdk/--parameters) , которая содержит параметры `out` для метода.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-114">[in]  A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="5a1cc-115">Этот параметр игнорируется, если имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-115">This parameter is ignored if set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="5a1cc-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5a1cc-116">Return value</span></span>

<span data-ttu-id="5a1cc-117">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="5a1cc-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5a1cc-118">Константа</span><span class="sxs-lookup"><span data-stu-id="5a1cc-118">Constant</span></span>  |<span data-ttu-id="5a1cc-119">значения</span><span class="sxs-lookup"><span data-stu-id="5a1cc-119">Value</span></span>  |<span data-ttu-id="5a1cc-120">Описание</span><span class="sxs-lookup"><span data-stu-id="5a1cc-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5a1cc-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5a1cc-121">0x80041008</span></span> | <span data-ttu-id="5a1cc-122">Один или несколько параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="5a1cc-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="5a1cc-123">0x80041043</span></span> | <span data-ttu-id="5a1cc-124">Параметр метода `[in, out]`, указанный в объектах *пинсигнатуре* и *паутсигнатуре* , имеет разные квалификаторы.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="5a1cc-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="5a1cc-125">0x80041036</span></span> | <span data-ttu-id="5a1cc-126">В параметре метода отсутствует спецификация квалификатора **идентификатора** .</span><span class="sxs-lookup"><span data-stu-id="5a1cc-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="5a1cc-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="5a1cc-127">0x80041038</span></span> | <span data-ttu-id="5a1cc-128">Серия ИДЕНТИФИКАТОРов, назначенных параметрам метода, не является последовательным или не начинается с 0.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="5a1cc-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="5a1cc-129">0x80041039</span></span> | <span data-ttu-id="5a1cc-130">Возвращаемое значение метода имеет квалификатор **идентификатора** .</span><span class="sxs-lookup"><span data-stu-id="5a1cc-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="5a1cc-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="5a1cc-131">0x80041034</span></span> | <span data-ttu-id="5a1cc-132">Предпринята попытка повторно использовать существующее имя метода из родительского класса, и подписи не совпали.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="5a1cc-133">0</span><span class="sxs-lookup"><span data-stu-id="5a1cc-133">0</span></span> | <span data-ttu-id="5a1cc-134">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="5a1cc-135">Заметки</span><span class="sxs-lookup"><span data-stu-id="5a1cc-135">Remarks</span></span>

<span data-ttu-id="5a1cc-136">Эта функция создает оболочку для вызова метода [ивбемклассобжект::P утмесод](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) .</span><span class="sxs-lookup"><span data-stu-id="5a1cc-136">This function wraps a call to the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

<span data-ttu-id="5a1cc-137">Этот вызов метода поддерживается, только если `ptr` является определением класса CIM.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="5a1cc-138">Управление методами недоступно из [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) указателей, указывающих на экземпляры CIM.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-138">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="5a1cc-139">Пользователи не могут создавать методы с именами, которые начинаются или заканчиваются символом подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="5a1cc-140">Он зарезервирован для системных классов и свойств.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="5a1cc-141">Для метода параметры `in` и `out` описаны как свойства в объектах [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="5a1cc-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objects.</span></span>

<span data-ttu-id="5a1cc-142">Параметр `[in/out]` можно определить, добавив одно и то же свойство в оба объекта, на которые указывают параметры `pInSignature` и `pOutSignature`.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="5a1cc-143">В этом случае свойства имеют одинаковое значение квалификатора **идентификатора** .</span><span class="sxs-lookup"><span data-stu-id="5a1cc-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="5a1cc-144">Каждое свойство в объекте класса [__Parameters](/windows/desktop/WmiSdk/--parameters) , отличном от `ReturnValue`, должно иметь квалификатор **ID** , числовое значение, начинающееся с нуля, которое определяет порядок, в котором отображаются параметры.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-144">Each property in a [__Parameters](/windows/desktop/WmiSdk/--parameters) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="5a1cc-145">Ни один из двух параметров не может иметь одинаковое значение **идентификатора** , и значение **идентификатора** не может быть пропущено.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="5a1cc-146">При возникновении любого из этих условий функция `PutMethod` возвращает `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span><span class="sxs-lookup"><span data-stu-id="5a1cc-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="5a1cc-147">Пример</span><span class="sxs-lookup"><span data-stu-id="5a1cc-147">Example</span></span>

<span data-ttu-id="5a1cc-148">Пример см. в описании метода [ивбемклассобжект::P утмесод](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) .</span><span class="sxs-lookup"><span data-stu-id="5a1cc-148">For an example, see the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="5a1cc-149">Требования</span><span class="sxs-lookup"><span data-stu-id="5a1cc-149">Requirements</span></span>  
 <span data-ttu-id="5a1cc-150">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a1cc-150">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a1cc-151">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="5a1cc-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="5a1cc-152">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5a1cc-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a1cc-153">См. также</span><span class="sxs-lookup"><span data-stu-id="5a1cc-153">See also</span></span>

- [<span data-ttu-id="5a1cc-154">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="5a1cc-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
