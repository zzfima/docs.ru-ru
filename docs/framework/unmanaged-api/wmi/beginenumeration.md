---
title: Функция startEnumeration (Неуправляемая справка API)
description: Функция BeginEnumeration сбрасывает регистратор к началу перечисления
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
ms.openlocfilehash: eac23916bd78ec3970a87566e2d2f4d79b379824
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176881"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="85734-103">Функция BeginEnumeration</span><span class="sxs-lookup"><span data-stu-id="85734-103">BeginEnumeration function</span></span>
<span data-ttu-id="85734-104">Сброс исчисляется пересчетом обратно в начало перечисления.</span><span class="sxs-lookup"><span data-stu-id="85734-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="85734-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85734-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lEnumFlags
);
```  

## <a name="parameters"></a><span data-ttu-id="85734-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="85734-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="85734-107">(в) Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="85734-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="85734-108">(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="85734-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`\
<span data-ttu-id="85734-109">(в) Биттаевая комбинация флагов или значений, описанных в разделе [Замечания,](#remarks) который контролирует свойства, включенные в перечисление.</span><span class="sxs-lookup"><span data-stu-id="85734-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="85734-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="85734-110">Return value</span></span>

<span data-ttu-id="85734-111">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="85734-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="85734-112">Постоянно</span><span class="sxs-lookup"><span data-stu-id="85734-112">Constant</span></span>  |<span data-ttu-id="85734-113">Значение</span><span class="sxs-lookup"><span data-stu-id="85734-113">Value</span></span>  |<span data-ttu-id="85734-114">Описание</span><span class="sxs-lookup"><span data-stu-id="85734-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="85734-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="85734-115">0x80041008</span></span> | <span data-ttu-id="85734-116">Комбинация флагов `lEnumFlags` в является недействительным, или недействительный аргумент был указан.</span><span class="sxs-lookup"><span data-stu-id="85734-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="85734-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="85734-117">0x8004101d</span></span> | <span data-ttu-id="85734-118">Второй звонок `BeginEnumeration` был сделан без вмешательства вызова [`EndEnumeration`](endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="85734-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="85734-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="85734-119">0x80041006</span></span> | <span data-ttu-id="85734-120">Недостаточно памяти доступно для начала нового перечисления.</span><span class="sxs-lookup"><span data-stu-id="85734-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="85734-121">0</span><span class="sxs-lookup"><span data-stu-id="85734-121">0</span></span> | <span data-ttu-id="85734-122">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="85734-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="85734-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="85734-123">Remarks</span></span>

<span data-ttu-id="85734-124">Эта функция завершает вызов [iWbemClassObject::BeginEnumeration.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="85734-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="85734-125">Флаги, которые могут `lEnumFlags` быть переданы в качестве аргумента, определяются в файле заголовка *WbemCli.h,* или вы можете определить их как константы в коде.</span><span class="sxs-lookup"><span data-stu-id="85734-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="85734-126">Вы можете объединить один флаг из каждой группы с любым флагом из любой другой группы.</span><span class="sxs-lookup"><span data-stu-id="85734-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="85734-127">Тем не менее, флаги из той же группы являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="85734-127">However, flags from the same group are mutually exclusive.</span></span>

<span data-ttu-id="85734-128">**Группа 1**</span><span class="sxs-lookup"><span data-stu-id="85734-128">**Group 1**</span></span>

|<span data-ttu-id="85734-129">Постоянно</span><span class="sxs-lookup"><span data-stu-id="85734-129">Constant</span></span>  |<span data-ttu-id="85734-130">Значение</span><span class="sxs-lookup"><span data-stu-id="85734-130">Value</span></span>  |<span data-ttu-id="85734-131">Описание</span><span class="sxs-lookup"><span data-stu-id="85734-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="85734-132">0x4</span><span class="sxs-lookup"><span data-stu-id="85734-132">0x4</span></span> | <span data-ttu-id="85734-133">Включите свойства, которые составляют только ключ.</span><span class="sxs-lookup"><span data-stu-id="85734-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="85734-134">0x8</span><span class="sxs-lookup"><span data-stu-id="85734-134">0x8</span></span> | <span data-ttu-id="85734-135">Включите свойства, которые являются только ссылками на объекты.</span><span class="sxs-lookup"><span data-stu-id="85734-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="85734-136">**Группа 2**</span><span class="sxs-lookup"><span data-stu-id="85734-136">**Group 2**</span></span>

<span data-ttu-id="85734-137">Постоянно</span><span class="sxs-lookup"><span data-stu-id="85734-137">Constant</span></span>  |<span data-ttu-id="85734-138">Значение</span><span class="sxs-lookup"><span data-stu-id="85734-138">Value</span></span>  |<span data-ttu-id="85734-139">Описание</span><span class="sxs-lookup"><span data-stu-id="85734-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="85734-140">0x30</span><span class="sxs-lookup"><span data-stu-id="85734-140">0x30</span></span> | <span data-ttu-id="85734-141">Ограничьте перечисление только системными свойствами.</span><span class="sxs-lookup"><span data-stu-id="85734-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="85734-142">0x40</span><span class="sxs-lookup"><span data-stu-id="85734-142">0x40</span></span> | <span data-ttu-id="85734-143">Включите локальные и распространяемые свойства, но исключите свойства системы из перечисления.</span><span class="sxs-lookup"><span data-stu-id="85734-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="85734-144">Для занятий:</span><span class="sxs-lookup"><span data-stu-id="85734-144">For classes:</span></span>

<span data-ttu-id="85734-145">Постоянно</span><span class="sxs-lookup"><span data-stu-id="85734-145">Constant</span></span>  |<span data-ttu-id="85734-146">Значение</span><span class="sxs-lookup"><span data-stu-id="85734-146">Value</span></span>  |<span data-ttu-id="85734-147">Описание</span><span class="sxs-lookup"><span data-stu-id="85734-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="85734-148">0x100</span><span class="sxs-lookup"><span data-stu-id="85734-148">0x100</span></span> | <span data-ttu-id="85734-149">Ограничьте перечисление свойствами, переопределенными в определении класса.</span><span class="sxs-lookup"><span data-stu-id="85734-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="85734-150">0x100</span><span class="sxs-lookup"><span data-stu-id="85734-150">0x100</span></span> | <span data-ttu-id="85734-151">Ограничьте перечисление свойствами, переопределенными в определении текущего класса, и новыми свойствами, определенными в классе.</span><span class="sxs-lookup"><span data-stu-id="85734-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="85734-152">0x300</span><span class="sxs-lookup"><span data-stu-id="85734-152">0x300</span></span> | <span data-ttu-id="85734-153">Маска (а не флаг), чтобы `lEnumFlags` применить против значения, чтобы проверить, если либо `WBEM_FLAG_CLASS_OVERRIDES_ONLY` или `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` установлен.</span><span class="sxs-lookup"><span data-stu-id="85734-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="85734-154">0x10</span><span class="sxs-lookup"><span data-stu-id="85734-154">0x10</span></span> | <span data-ttu-id="85734-155">Ограничьте перечисление свойствами, которые определены или изменены в самом классе.</span><span class="sxs-lookup"><span data-stu-id="85734-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="85734-156">0x20</span><span class="sxs-lookup"><span data-stu-id="85734-156">0x20</span></span> | <span data-ttu-id="85734-157">Ограничьте перечисление свойствами, унаследованными от базовых классов.</span><span class="sxs-lookup"><span data-stu-id="85734-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="85734-158">В случаях:</span><span class="sxs-lookup"><span data-stu-id="85734-158">For instances:</span></span>

<span data-ttu-id="85734-159">Постоянно</span><span class="sxs-lookup"><span data-stu-id="85734-159">Constant</span></span>  |<span data-ttu-id="85734-160">Значение</span><span class="sxs-lookup"><span data-stu-id="85734-160">Value</span></span>  |<span data-ttu-id="85734-161">Описание</span><span class="sxs-lookup"><span data-stu-id="85734-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="85734-162">0x10</span><span class="sxs-lookup"><span data-stu-id="85734-162">0x10</span></span> | <span data-ttu-id="85734-163">Ограничьте перечисление свойствами, которые определены или изменены в самом классе.</span><span class="sxs-lookup"><span data-stu-id="85734-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="85734-164">0x20</span><span class="sxs-lookup"><span data-stu-id="85734-164">0x20</span></span> | <span data-ttu-id="85734-165">Ограничьте перечисление свойствами, унаследованными от базовых классов.</span><span class="sxs-lookup"><span data-stu-id="85734-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="85734-166">Требования</span><span class="sxs-lookup"><span data-stu-id="85734-166">Requirements</span></span>  
 <span data-ttu-id="85734-167">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85734-167">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85734-168">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="85734-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="85734-169">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="85734-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85734-170">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="85734-170">See also</span></span>

- [<span data-ttu-id="85734-171">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="85734-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
