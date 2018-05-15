---
title: Функция BeginEnumeration (Справочник по неуправляемым API)
description: Функция BeginEnumeration устанавливает перечислитель в начало перечисления
ms.date: 11/06/2017
api_name:
- BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginEnumeration
helpviewer_keywords:
- BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9699f0cfc4e9fdb989337681b164cc1e703c1e60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="beginenumeration-function"></a><span data-ttu-id="7639c-103">Функция BeginEnumeration</span><span class="sxs-lookup"><span data-stu-id="7639c-103">BeginEnumeration function</span></span>
<span data-ttu-id="7639c-104">Сбрасывает перечислитель в начало перечисления.</span><span class="sxs-lookup"><span data-stu-id="7639c-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="7639c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7639c-105">Syntax</span></span>  
  
```  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="7639c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7639c-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="7639c-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="7639c-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="7639c-108">`ptr` [in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="7639c-108">`ptr` [in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="7639c-109">[in] Побитовое сочетание флагов или значений, описанных в [примечания](#remarks) раздел, который управляет свойствами, которые включены в перечисление.</span><span class="sxs-lookup"><span data-stu-id="7639c-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="7639c-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7639c-110">Return value</span></span>

<span data-ttu-id="7639c-111">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="7639c-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7639c-112">Константа</span><span class="sxs-lookup"><span data-stu-id="7639c-112">Constant</span></span>  |<span data-ttu-id="7639c-113">Значение</span><span class="sxs-lookup"><span data-stu-id="7639c-113">Value</span></span>  |<span data-ttu-id="7639c-114">Описание</span><span class="sxs-lookup"><span data-stu-id="7639c-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7639c-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7639c-115">0x80041008</span></span> | <span data-ttu-id="7639c-116">Сочетание флагов в `lEnumFlags` недопустим или недопустимый аргумент был указан.</span><span class="sxs-lookup"><span data-stu-id="7639c-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="7639c-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="7639c-117">0x8004101d</span></span> | <span data-ttu-id="7639c-118">Второй вызов `BeginEnumeration` была произведена без промежуточных вызовов [ `EndEnumeration` ](endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="7639c-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7639c-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7639c-119">0x80041006</span></span> | <span data-ttu-id="7639c-120">Чтобы начать новое перечисление доступен не хватает памяти.</span><span class="sxs-lookup"><span data-stu-id="7639c-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="7639c-121">0</span><span class="sxs-lookup"><span data-stu-id="7639c-121">0</span></span> | <span data-ttu-id="7639c-122">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="7639c-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="7639c-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="7639c-123">Remarks</span></span>

<span data-ttu-id="7639c-124">Эта функция создает оболочку для вызова [IWbemClassObject::BeginEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="7639c-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) method.</span></span>

<span data-ttu-id="7639c-125">Флаги, которые могут быть переданы как `lEnumFlags` аргумент определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде.</span><span class="sxs-lookup"><span data-stu-id="7639c-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="7639c-126">Можно объединить один флаг из каждой группы с любого флага из другой группы.</span><span class="sxs-lookup"><span data-stu-id="7639c-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="7639c-127">Однако флаги из той же группы являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="7639c-127">However, flags from the same group are mutually exclusive.</span></span> 

<span data-ttu-id="7639c-128">**Группа 1**</span><span class="sxs-lookup"><span data-stu-id="7639c-128">**Group 1**</span></span>

|<span data-ttu-id="7639c-129">Константа</span><span class="sxs-lookup"><span data-stu-id="7639c-129">Constant</span></span>  |<span data-ttu-id="7639c-130">Значение</span><span class="sxs-lookup"><span data-stu-id="7639c-130">Value</span></span>  |<span data-ttu-id="7639c-131">Описание</span><span class="sxs-lookup"><span data-stu-id="7639c-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="7639c-132">0x4</span><span class="sxs-lookup"><span data-stu-id="7639c-132">0x4</span></span> | <span data-ttu-id="7639c-133">Включает свойства, составляющие только ключ.</span><span class="sxs-lookup"><span data-stu-id="7639c-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="7639c-134">0x8</span><span class="sxs-lookup"><span data-stu-id="7639c-134">0x8</span></span> | <span data-ttu-id="7639c-135">Включают свойства, которые являются только ссылки на объекты.</span><span class="sxs-lookup"><span data-stu-id="7639c-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="7639c-136">**Группа 2**</span><span class="sxs-lookup"><span data-stu-id="7639c-136">**Group 2**</span></span>

<span data-ttu-id="7639c-137">Константа</span><span class="sxs-lookup"><span data-stu-id="7639c-137">Constant</span></span>  |<span data-ttu-id="7639c-138">Значение</span><span class="sxs-lookup"><span data-stu-id="7639c-138">Value</span></span>  |<span data-ttu-id="7639c-139">Описание</span><span class="sxs-lookup"><span data-stu-id="7639c-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="7639c-140">0x30</span><span class="sxs-lookup"><span data-stu-id="7639c-140">0x30</span></span> | <span data-ttu-id="7639c-141">Ограничьте к только системные свойства перечисления.</span><span class="sxs-lookup"><span data-stu-id="7639c-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="7639c-142">0x40</span><span class="sxs-lookup"><span data-stu-id="7639c-142">0x40</span></span> | <span data-ttu-id="7639c-143">Включает локальные и распространяемые свойства, но исключает системные свойства из перечисления.</span><span class="sxs-lookup"><span data-stu-id="7639c-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="7639c-144">Для классов:</span><span class="sxs-lookup"><span data-stu-id="7639c-144">For classes:</span></span>

<span data-ttu-id="7639c-145">Константа</span><span class="sxs-lookup"><span data-stu-id="7639c-145">Constant</span></span>  |<span data-ttu-id="7639c-146">Значение</span><span class="sxs-lookup"><span data-stu-id="7639c-146">Value</span></span>  |<span data-ttu-id="7639c-147">Описание</span><span class="sxs-lookup"><span data-stu-id="7639c-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="7639c-148">0x100</span><span class="sxs-lookup"><span data-stu-id="7639c-148">0x100</span></span> | <span data-ttu-id="7639c-149">Ограничения перечисления для свойства при переопределении в определении класса.</span><span class="sxs-lookup"><span data-stu-id="7639c-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="7639c-150">0x100</span><span class="sxs-lookup"><span data-stu-id="7639c-150">0x100</span></span> | <span data-ttu-id="7639c-151">Ограничения перечисления для свойства при переопределении в текущем определении класса и новые свойства, определенные в классе.</span><span class="sxs-lookup"><span data-stu-id="7639c-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="7639c-152">0x300</span><span class="sxs-lookup"><span data-stu-id="7639c-152">0x300</span></span> | <span data-ttu-id="7639c-153">Значение маски (а не флаг) для применения к `lEnumFlags` значение для проверки, если параметр `WBEM_FLAG_CLASS_OVERRIDES_ONLY` или `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` имеет значение.</span><span class="sxs-lookup"><span data-stu-id="7639c-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="7639c-154">0x10</span><span class="sxs-lookup"><span data-stu-id="7639c-154">0x10</span></span> | <span data-ttu-id="7639c-155">Ограничения перечисления для свойства, которые были определены или изменены в самом классе.</span><span class="sxs-lookup"><span data-stu-id="7639c-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="7639c-156">0x20</span><span class="sxs-lookup"><span data-stu-id="7639c-156">0x20</span></span> | <span data-ttu-id="7639c-157">Ограничения перечисления для свойства, наследуемые из базовых классов.</span><span class="sxs-lookup"><span data-stu-id="7639c-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="7639c-158">Для экземпляров:</span><span class="sxs-lookup"><span data-stu-id="7639c-158">For instances:</span></span>

<span data-ttu-id="7639c-159">Константа</span><span class="sxs-lookup"><span data-stu-id="7639c-159">Constant</span></span>  |<span data-ttu-id="7639c-160">Значение</span><span class="sxs-lookup"><span data-stu-id="7639c-160">Value</span></span>  |<span data-ttu-id="7639c-161">Описание</span><span class="sxs-lookup"><span data-stu-id="7639c-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="7639c-162">0x10</span><span class="sxs-lookup"><span data-stu-id="7639c-162">0x10</span></span> | <span data-ttu-id="7639c-163">Ограничения перечисления для свойства, которые были определены или изменены в самом классе.</span><span class="sxs-lookup"><span data-stu-id="7639c-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="7639c-164">0x20</span><span class="sxs-lookup"><span data-stu-id="7639c-164">0x20</span></span> | <span data-ttu-id="7639c-165">Ограничения перечисления для свойства, наследуемые из базовых классов.</span><span class="sxs-lookup"><span data-stu-id="7639c-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |


## <a name="requirements"></a><span data-ttu-id="7639c-166">Требования</span><span class="sxs-lookup"><span data-stu-id="7639c-166">Requirements</span></span>  
 <span data-ttu-id="7639c-167">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7639c-167">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7639c-168">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7639c-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7639c-169">**Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7639c-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7639c-170">См. также</span><span class="sxs-lookup"><span data-stu-id="7639c-170">See also</span></span>  
[<span data-ttu-id="7639c-171">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="7639c-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
