---
title: "Функция BeginEnumeration (Справочник по неуправляемым API)"
description: "Функция BeginEnumeration устанавливает перечислитель в начало перечисления"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: BeginEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: BeginEnumeration
helpviewer_keywords: BeginEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 90c3e8448a61145290ea4a75b1d38f7ae010cb9f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="beginenumeration-function"></a><span data-ttu-id="783f2-103">Функция BeginEnumeration</span><span class="sxs-lookup"><span data-stu-id="783f2-103">BeginEnumeration function</span></span>
<span data-ttu-id="783f2-104">Сбрасывает перечислитель в начало перечисления.</span><span class="sxs-lookup"><span data-stu-id="783f2-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="783f2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="783f2-105">Syntax</span></span>  
  
```  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="783f2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="783f2-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="783f2-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="783f2-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="783f2-108">`ptr`[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="783f2-108">`ptr` [in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="783f2-109">[in] Побитовое сочетание флагов или значений, описанных в [примечания](#remarks) раздел, который управляет свойствами, которые включены в перечисление.</span><span class="sxs-lookup"><span data-stu-id="783f2-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="783f2-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="783f2-110">Return value</span></span>

<span data-ttu-id="783f2-111">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="783f2-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="783f2-112">Константа</span><span class="sxs-lookup"><span data-stu-id="783f2-112">Constant</span></span>  |<span data-ttu-id="783f2-113">Значение</span><span class="sxs-lookup"><span data-stu-id="783f2-113">Value</span></span>  |<span data-ttu-id="783f2-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="783f2-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="783f2-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="783f2-115">0x80041008</span></span> | <span data-ttu-id="783f2-116">Сочетание флагов в `lEnumFlags` недопустим или недопустимый аргумент был указан.</span><span class="sxs-lookup"><span data-stu-id="783f2-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="783f2-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="783f2-117">0x8004101d</span></span> | <span data-ttu-id="783f2-118">Второй вызов `BeginEnumeration` была произведена без промежуточных вызовов [ `EndEnumeration` ](endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="783f2-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="783f2-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="783f2-119">0x80041006</span></span> | <span data-ttu-id="783f2-120">Чтобы начать новое перечисление доступен не хватает памяти.</span><span class="sxs-lookup"><span data-stu-id="783f2-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="783f2-121">0</span><span class="sxs-lookup"><span data-stu-id="783f2-121">0</span></span> | <span data-ttu-id="783f2-122">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="783f2-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="783f2-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="783f2-123">Remarks</span></span>

<span data-ttu-id="783f2-124">Эта функция создает оболочку для вызова [IWbemClassObject::BeginEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="783f2-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) method.</span></span>

<span data-ttu-id="783f2-125">Флаги, которые могут быть переданы как `lEnumFlags` аргумент определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде.</span><span class="sxs-lookup"><span data-stu-id="783f2-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="783f2-126">Можно объединить один флаг из каждой группы с любого флага из другой группы.</span><span class="sxs-lookup"><span data-stu-id="783f2-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="783f2-127">Однако флаги из той же группы являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="783f2-127">However, flags from the same group are mutually exclusive.</span></span> 

<span data-ttu-id="783f2-128">**Группа 1**</span><span class="sxs-lookup"><span data-stu-id="783f2-128">**Group 1**</span></span>

|<span data-ttu-id="783f2-129">Константа</span><span class="sxs-lookup"><span data-stu-id="783f2-129">Constant</span></span>  |<span data-ttu-id="783f2-130">Значение</span><span class="sxs-lookup"><span data-stu-id="783f2-130">Value</span></span>  |<span data-ttu-id="783f2-131">Описание:</span><span class="sxs-lookup"><span data-stu-id="783f2-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="783f2-132">0x4</span><span class="sxs-lookup"><span data-stu-id="783f2-132">0x4</span></span> | <span data-ttu-id="783f2-133">Включает свойства, составляющие только ключ.</span><span class="sxs-lookup"><span data-stu-id="783f2-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="783f2-134">0x8</span><span class="sxs-lookup"><span data-stu-id="783f2-134">0x8</span></span> | <span data-ttu-id="783f2-135">Включают свойства, которые являются только ссылки на объекты.</span><span class="sxs-lookup"><span data-stu-id="783f2-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="783f2-136">**Группа 2**</span><span class="sxs-lookup"><span data-stu-id="783f2-136">**Group 2**</span></span>

<span data-ttu-id="783f2-137">Константа</span><span class="sxs-lookup"><span data-stu-id="783f2-137">Constant</span></span>  |<span data-ttu-id="783f2-138">Значение</span><span class="sxs-lookup"><span data-stu-id="783f2-138">Value</span></span>  |<span data-ttu-id="783f2-139">Описание:</span><span class="sxs-lookup"><span data-stu-id="783f2-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="783f2-140">0x30</span><span class="sxs-lookup"><span data-stu-id="783f2-140">0x30</span></span> | <span data-ttu-id="783f2-141">Ограничьте к только системные свойства перечисления.</span><span class="sxs-lookup"><span data-stu-id="783f2-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="783f2-142">0x40</span><span class="sxs-lookup"><span data-stu-id="783f2-142">0x40</span></span> | <span data-ttu-id="783f2-143">Включает локальные и распространяемые свойства, но исключает системные свойства из перечисления.</span><span class="sxs-lookup"><span data-stu-id="783f2-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="783f2-144">Для классов:</span><span class="sxs-lookup"><span data-stu-id="783f2-144">For classes:</span></span>

<span data-ttu-id="783f2-145">Константа</span><span class="sxs-lookup"><span data-stu-id="783f2-145">Constant</span></span>  |<span data-ttu-id="783f2-146">Значение</span><span class="sxs-lookup"><span data-stu-id="783f2-146">Value</span></span>  |<span data-ttu-id="783f2-147">Описание:</span><span class="sxs-lookup"><span data-stu-id="783f2-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="783f2-148">0x100</span><span class="sxs-lookup"><span data-stu-id="783f2-148">0x100</span></span> | <span data-ttu-id="783f2-149">Ограничения перечисления для свойства при переопределении в определении класса.</span><span class="sxs-lookup"><span data-stu-id="783f2-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="783f2-150">0x100</span><span class="sxs-lookup"><span data-stu-id="783f2-150">0x100</span></span> | <span data-ttu-id="783f2-151">Ограничения перечисления для свойства при переопределении в текущем определении класса и новые свойства, определенные в классе.</span><span class="sxs-lookup"><span data-stu-id="783f2-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="783f2-152">0x300</span><span class="sxs-lookup"><span data-stu-id="783f2-152">0x300</span></span> | <span data-ttu-id="783f2-153">Значение маски (а не флаг) для применения к `lEnumFlags` значение для проверки, если параметр `WBEM_FLAG_CLASS_OVERRIDES_ONLY` или `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` имеет значение.</span><span class="sxs-lookup"><span data-stu-id="783f2-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="783f2-154">0x10</span><span class="sxs-lookup"><span data-stu-id="783f2-154">0x10</span></span> | <span data-ttu-id="783f2-155">Ограничения перечисления для свойства, которые были определены или изменены в самом классе.</span><span class="sxs-lookup"><span data-stu-id="783f2-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="783f2-156">0x20</span><span class="sxs-lookup"><span data-stu-id="783f2-156">0x20</span></span> | <span data-ttu-id="783f2-157">Ограничения перечисления для свойства, наследуемые из базовых классов.</span><span class="sxs-lookup"><span data-stu-id="783f2-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="783f2-158">Для экземпляров:</span><span class="sxs-lookup"><span data-stu-id="783f2-158">For instances:</span></span>

<span data-ttu-id="783f2-159">Константа</span><span class="sxs-lookup"><span data-stu-id="783f2-159">Constant</span></span>  |<span data-ttu-id="783f2-160">Значение</span><span class="sxs-lookup"><span data-stu-id="783f2-160">Value</span></span>  |<span data-ttu-id="783f2-161">Описание:</span><span class="sxs-lookup"><span data-stu-id="783f2-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="783f2-162">0x10</span><span class="sxs-lookup"><span data-stu-id="783f2-162">0x10</span></span> | <span data-ttu-id="783f2-163">Ограничения перечисления для свойства, которые были определены или изменены в самом классе.</span><span class="sxs-lookup"><span data-stu-id="783f2-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="783f2-164">0x20</span><span class="sxs-lookup"><span data-stu-id="783f2-164">0x20</span></span> | <span data-ttu-id="783f2-165">Ограничения перечисления для свойства, наследуемые из базовых классов.</span><span class="sxs-lookup"><span data-stu-id="783f2-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |


## <a name="requirements"></a><span data-ttu-id="783f2-166">Требования</span><span class="sxs-lookup"><span data-stu-id="783f2-166">Requirements</span></span>  
 <span data-ttu-id="783f2-167">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="783f2-167">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="783f2-168">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="783f2-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="783f2-169">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="783f2-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="783f2-170">См. также</span><span class="sxs-lookup"><span data-stu-id="783f2-170">See also</span></span>  
[<span data-ttu-id="783f2-171">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="783f2-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
