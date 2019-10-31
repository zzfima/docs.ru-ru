---
title: Функция BeginEnumeration (Справочник по неуправляемым API)
description: Функция BeginEnumeration Сбрасывает перечислитель до начала перечисления
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
ms.openlocfilehash: 9e467234a45ae702a5b77a5f0fa8b75d4ff03c52
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124134"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="64cbf-103">Функция BeginEnumeration</span><span class="sxs-lookup"><span data-stu-id="64cbf-103">BeginEnumeration function</span></span>
<span data-ttu-id="64cbf-104">Сбрасывает перечислитель обратно в начало перечисления.</span><span class="sxs-lookup"><span data-stu-id="64cbf-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="64cbf-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64cbf-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="64cbf-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="64cbf-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="64cbf-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="64cbf-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="64cbf-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="64cbf-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`\
<span data-ttu-id="64cbf-109">окне Побитовое сочетание флагов или значений, описанных в разделе « [Примечания](#remarks) », которое управляет свойствами, входящими в перечисление.</span><span class="sxs-lookup"><span data-stu-id="64cbf-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="64cbf-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="64cbf-110">Return value</span></span>

<span data-ttu-id="64cbf-111">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="64cbf-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="64cbf-112">Константа</span><span class="sxs-lookup"><span data-stu-id="64cbf-112">Constant</span></span>  |<span data-ttu-id="64cbf-113">значения</span><span class="sxs-lookup"><span data-stu-id="64cbf-113">Value</span></span>  |<span data-ttu-id="64cbf-114">Описание</span><span class="sxs-lookup"><span data-stu-id="64cbf-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="64cbf-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="64cbf-115">0x80041008</span></span> | <span data-ttu-id="64cbf-116">Недопустимое сочетание флагов в `lEnumFlags` или указан недопустимый аргумент.</span><span class="sxs-lookup"><span data-stu-id="64cbf-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="64cbf-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="64cbf-117">0x8004101d</span></span> | <span data-ttu-id="64cbf-118">Второй вызов `BeginEnumeration` был выполнен без промежуточного вызова [`EndEnumeration`](endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="64cbf-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="64cbf-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="64cbf-119">0x80041006</span></span> | <span data-ttu-id="64cbf-120">Недостаточно памяти для начала нового перечисления.</span><span class="sxs-lookup"><span data-stu-id="64cbf-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="64cbf-121">0</span><span class="sxs-lookup"><span data-stu-id="64cbf-121">0</span></span> | <span data-ttu-id="64cbf-122">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="64cbf-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="64cbf-123">Заметки</span><span class="sxs-lookup"><span data-stu-id="64cbf-123">Remarks</span></span>

<span data-ttu-id="64cbf-124">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="64cbf-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="64cbf-125">Флаги, которые могут быть переданы в качестве аргумента `lEnumFlags`, определяются в файле заголовка *вбемкли. h* , или их можно определить как константы в коде.</span><span class="sxs-lookup"><span data-stu-id="64cbf-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="64cbf-126">Можно объединить один флаг из каждой группы с любым флагом из любой другой группы.</span><span class="sxs-lookup"><span data-stu-id="64cbf-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="64cbf-127">Однако флаги из одной и той же группы являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="64cbf-127">However, flags from the same group are mutually exclusive.</span></span> 

<span data-ttu-id="64cbf-128">**Группа 1**</span><span class="sxs-lookup"><span data-stu-id="64cbf-128">**Group 1**</span></span>

|<span data-ttu-id="64cbf-129">Константа</span><span class="sxs-lookup"><span data-stu-id="64cbf-129">Constant</span></span>  |<span data-ttu-id="64cbf-130">значения</span><span class="sxs-lookup"><span data-stu-id="64cbf-130">Value</span></span>  |<span data-ttu-id="64cbf-131">Описание</span><span class="sxs-lookup"><span data-stu-id="64cbf-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="64cbf-132">0x4</span><span class="sxs-lookup"><span data-stu-id="64cbf-132">0x4</span></span> | <span data-ttu-id="64cbf-133">Включить свойства, которые составляют только ключ.</span><span class="sxs-lookup"><span data-stu-id="64cbf-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="64cbf-134">0x8</span><span class="sxs-lookup"><span data-stu-id="64cbf-134">0x8</span></span> | <span data-ttu-id="64cbf-135">Включить свойства, которые являются только ссылками на объекты.</span><span class="sxs-lookup"><span data-stu-id="64cbf-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="64cbf-136">**Группа 2**</span><span class="sxs-lookup"><span data-stu-id="64cbf-136">**Group 2**</span></span>

<span data-ttu-id="64cbf-137">Константа</span><span class="sxs-lookup"><span data-stu-id="64cbf-137">Constant</span></span>  |<span data-ttu-id="64cbf-138">значения</span><span class="sxs-lookup"><span data-stu-id="64cbf-138">Value</span></span>  |<span data-ttu-id="64cbf-139">Описание</span><span class="sxs-lookup"><span data-stu-id="64cbf-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="64cbf-140">0x30</span><span class="sxs-lookup"><span data-stu-id="64cbf-140">0x30</span></span> | <span data-ttu-id="64cbf-141">Ограничьте перечисление только системными свойствами.</span><span class="sxs-lookup"><span data-stu-id="64cbf-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="64cbf-142">0x40</span><span class="sxs-lookup"><span data-stu-id="64cbf-142">0x40</span></span> | <span data-ttu-id="64cbf-143">Включить локальные и распространенные свойства, но исключить системные свойства из перечисления.</span><span class="sxs-lookup"><span data-stu-id="64cbf-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="64cbf-144">Для классов:</span><span class="sxs-lookup"><span data-stu-id="64cbf-144">For classes:</span></span>

<span data-ttu-id="64cbf-145">Константа</span><span class="sxs-lookup"><span data-stu-id="64cbf-145">Constant</span></span>  |<span data-ttu-id="64cbf-146">значения</span><span class="sxs-lookup"><span data-stu-id="64cbf-146">Value</span></span>  |<span data-ttu-id="64cbf-147">Описание</span><span class="sxs-lookup"><span data-stu-id="64cbf-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="64cbf-148">0x100</span><span class="sxs-lookup"><span data-stu-id="64cbf-148">0x100</span></span> | <span data-ttu-id="64cbf-149">Ограничьте перечисление свойствами, переопределенными в определении класса.</span><span class="sxs-lookup"><span data-stu-id="64cbf-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="64cbf-150">0x100</span><span class="sxs-lookup"><span data-stu-id="64cbf-150">0x100</span></span> | <span data-ttu-id="64cbf-151">Ограничьте перечисление свойствами, переопределенными в текущем определении класса, и новыми свойствами, определенными в классе.</span><span class="sxs-lookup"><span data-stu-id="64cbf-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="64cbf-152">0x300</span><span class="sxs-lookup"><span data-stu-id="64cbf-152">0x300</span></span> | <span data-ttu-id="64cbf-153">Маска (а не флаг), применяемая к `lEnumFlags`ному значению для проверки того, задан ли параметр `WBEM_FLAG_CLASS_OVERRIDES_ONLY` или `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES`.</span><span class="sxs-lookup"><span data-stu-id="64cbf-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="64cbf-154">0x10</span><span class="sxs-lookup"><span data-stu-id="64cbf-154">0x10</span></span> | <span data-ttu-id="64cbf-155">Ограничьте перечисление свойствами, которые определены или изменены в самом классе.</span><span class="sxs-lookup"><span data-stu-id="64cbf-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="64cbf-156">0x20</span><span class="sxs-lookup"><span data-stu-id="64cbf-156">0x20</span></span> | <span data-ttu-id="64cbf-157">Ограничьте перечисление свойствами, унаследованными от базовых классов.</span><span class="sxs-lookup"><span data-stu-id="64cbf-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="64cbf-158">Для экземпляров:</span><span class="sxs-lookup"><span data-stu-id="64cbf-158">For instances:</span></span>

<span data-ttu-id="64cbf-159">Константа</span><span class="sxs-lookup"><span data-stu-id="64cbf-159">Constant</span></span>  |<span data-ttu-id="64cbf-160">значения</span><span class="sxs-lookup"><span data-stu-id="64cbf-160">Value</span></span>  |<span data-ttu-id="64cbf-161">Описание</span><span class="sxs-lookup"><span data-stu-id="64cbf-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="64cbf-162">0x10</span><span class="sxs-lookup"><span data-stu-id="64cbf-162">0x10</span></span> | <span data-ttu-id="64cbf-163">Ограничьте перечисление свойствами, которые определены или изменены в самом классе.</span><span class="sxs-lookup"><span data-stu-id="64cbf-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="64cbf-164">0x20</span><span class="sxs-lookup"><span data-stu-id="64cbf-164">0x20</span></span> | <span data-ttu-id="64cbf-165">Ограничьте перечисление свойствами, унаследованными от базовых классов.</span><span class="sxs-lookup"><span data-stu-id="64cbf-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="64cbf-166">Требования</span><span class="sxs-lookup"><span data-stu-id="64cbf-166">Requirements</span></span>  
 <span data-ttu-id="64cbf-167">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64cbf-167">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64cbf-168">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="64cbf-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="64cbf-169">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="64cbf-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64cbf-170">См. также</span><span class="sxs-lookup"><span data-stu-id="64cbf-170">See also</span></span>

- [<span data-ttu-id="64cbf-171">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="64cbf-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
