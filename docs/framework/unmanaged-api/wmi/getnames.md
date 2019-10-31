---
title: Функция Names (Справочник по неуправляемым интерфейсам API)
description: Функция Names извлекает имена свойств объекта.
ms.date: 11/06/2017
api_name:
- GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetNames
helpviewer_keywords:
- GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 5b03ed6a68fbe288e93dedb4f425f1511563dfeb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102526"
---
# <a name="getnames-function"></a><span data-ttu-id="eff20-103">Функция GetNames</span><span class="sxs-lookup"><span data-stu-id="eff20-103">GetNames function</span></span>
<span data-ttu-id="eff20-104">Получает подмножество имен или все имена свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="eff20-104">Retrieves either a subset or all of the names of the properties of an object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="eff20-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eff20-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNames (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
); 
```  

## <a name="parameters"></a><span data-ttu-id="eff20-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="eff20-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="eff20-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="eff20-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="eff20-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="eff20-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="eff20-109">окне Указатель на допустимое `LPCWSTR`, указывающий имя квалификатора, которое действует как часть фильтра.</span><span class="sxs-lookup"><span data-stu-id="eff20-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="eff20-110">Дополнительные сведения см. в разделе ["Примечания](#remarks) ".</span><span class="sxs-lookup"><span data-stu-id="eff20-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="eff20-111">Этот параметр может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="eff20-111">This parameter can be `null`.</span></span> 

`lFlags`  
<span data-ttu-id="eff20-112">окне Сочетание битовых полей.</span><span class="sxs-lookup"><span data-stu-id="eff20-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="eff20-113">Дополнительные сведения см. в разделе ["Примечания](#remarks) ".</span><span class="sxs-lookup"><span data-stu-id="eff20-113">For more information, see the [Remarks](#remarks) section.</span></span>

`pQualifierValue`   
<span data-ttu-id="eff20-114">окне Указатель на допустимую структуру `VARIANT`, инициализированную значением фильтра.</span><span class="sxs-lookup"><span data-stu-id="eff20-114">[in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="eff20-115">Этот параметр может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="eff20-115">This parameter can be `null`.</span></span> 

`pstrNames`  
<span data-ttu-id="eff20-116">заполняет Структура `SAFEARRAY`, содержащая имена свойств.</span><span class="sxs-lookup"><span data-stu-id="eff20-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="eff20-117">При входе этот параметр всегда должен быть указателем на `null`.</span><span class="sxs-lookup"><span data-stu-id="eff20-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="eff20-118">Дополнительные сведения см. в разделе ["Примечания"](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="eff20-118">See the [Remarks](#remarks) section for more information.</span></span> 

## <a name="return-value"></a><span data-ttu-id="eff20-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="eff20-119">Return value</span></span>

<span data-ttu-id="eff20-120">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="eff20-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="eff20-121">Константа</span><span class="sxs-lookup"><span data-stu-id="eff20-121">Constant</span></span>  |<span data-ttu-id="eff20-122">значения</span><span class="sxs-lookup"><span data-stu-id="eff20-122">Value</span></span>  |<span data-ttu-id="eff20-123">Описание</span><span class="sxs-lookup"><span data-stu-id="eff20-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="eff20-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="eff20-124">0x80041001</span></span> | <span data-ttu-id="eff20-125">Общий сбой.</span><span class="sxs-lookup"><span data-stu-id="eff20-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="eff20-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="eff20-126">0x80041008</span></span> | <span data-ttu-id="eff20-127">Один или несколько параметров недопустимы или указаны неверное сочетание флагов и параметров.</span><span class="sxs-lookup"><span data-stu-id="eff20-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="eff20-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="eff20-128">0x80041006</span></span> | <span data-ttu-id="eff20-129">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="eff20-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="eff20-130">0</span><span class="sxs-lookup"><span data-stu-id="eff20-130">0</span></span> | <span data-ttu-id="eff20-131">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="eff20-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="eff20-132">Заметки</span><span class="sxs-lookup"><span data-stu-id="eff20-132">Remarks</span></span>

<span data-ttu-id="eff20-133">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: Names](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) .</span><span class="sxs-lookup"><span data-stu-id="eff20-133">This function wraps a call to the [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) method.</span></span>

<span data-ttu-id="eff20-134">Возвращаемые именованные параметры управляются сочетанием флагов и параметров.</span><span class="sxs-lookup"><span data-stu-id="eff20-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="eff20-135">Например, функция может возвращать имена всех свойств или только имена ключевых свойств.</span><span class="sxs-lookup"><span data-stu-id="eff20-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="eff20-136">Основной фильтр указывается в параметре `lFlags`, а другие параметры зависят от него.</span><span class="sxs-lookup"><span data-stu-id="eff20-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="eff20-137">Значения флагов в `lFlags` являются битовыми полями</span><span class="sxs-lookup"><span data-stu-id="eff20-137">The flag values in `lFlags` are bit fields</span></span>

<span data-ttu-id="eff20-138">Флаги, которые можно передать в качестве аргумента `lEnumFlags`, являются битовыми полями, определенными в файле заголовка *вбемкли. h* , или их можно определить как константы в коде.</span><span class="sxs-lookup"><span data-stu-id="eff20-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="eff20-139">Можно объединить один флаг из каждой группы с любым флагом из любой другой группы.</span><span class="sxs-lookup"><span data-stu-id="eff20-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="eff20-140">Однако флаги из одной и той же группы являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="eff20-140">However, flags from the same group are mutually exclusive.</span></span> 

| <span data-ttu-id="eff20-141">Флаги группы 1</span><span class="sxs-lookup"><span data-stu-id="eff20-141">Group 1 flags</span></span> |<span data-ttu-id="eff20-142">значения</span><span class="sxs-lookup"><span data-stu-id="eff20-142">Value</span></span>  |<span data-ttu-id="eff20-143">Описание</span><span class="sxs-lookup"><span data-stu-id="eff20-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="eff20-144">0</span><span class="sxs-lookup"><span data-stu-id="eff20-144">0</span></span> | <span data-ttu-id="eff20-145">Возвращает все имена свойств.</span><span class="sxs-lookup"><span data-stu-id="eff20-145">Return all property names.</span></span> <span data-ttu-id="eff20-146">`strQualifierName` и `pQualifierVal` не используются.</span><span class="sxs-lookup"><span data-stu-id="eff20-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="eff20-147">1</span><span class="sxs-lookup"><span data-stu-id="eff20-147">1</span></span> | <span data-ttu-id="eff20-148">Возвращать только те свойства, которые имеют квалификатор имени, указанного параметром `strQualifierName`.</span><span class="sxs-lookup"><span data-stu-id="eff20-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="eff20-149">Если используется этот флаг, необходимо указать `strQualifierName`.</span><span class="sxs-lookup"><span data-stu-id="eff20-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="eff20-150">2</span><span class="sxs-lookup"><span data-stu-id="eff20-150">2</span></span> |  <span data-ttu-id="eff20-151">Возвращать только те свойства, которые не имеют квалификатора имени, указанного параметром `strQualifierName`.</span><span class="sxs-lookup"><span data-stu-id="eff20-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="eff20-152">Если используется этот флаг, необходимо указать `strQualifierName`.</span><span class="sxs-lookup"><span data-stu-id="eff20-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="eff20-153">3</span><span class="sxs-lookup"><span data-stu-id="eff20-153">3</span></span> | <span data-ttu-id="eff20-154">Возвращать только те свойства, которые имеют квалификатор имени, заданного параметром `wszQualifierName`, а также значение, идентичное значению, заданному структурой `pQualifierVal`.</span><span class="sxs-lookup"><span data-stu-id="eff20-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="eff20-155">Если используется этот флаг, необходимо указать и `wszQualifierName`, и `pQualifierValue`.</span><span class="sxs-lookup"><span data-stu-id="eff20-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="eff20-156">Флаги группы 2</span><span class="sxs-lookup"><span data-stu-id="eff20-156">Group 2 flags</span></span> |<span data-ttu-id="eff20-157">значения</span><span class="sxs-lookup"><span data-stu-id="eff20-157">Value</span></span>  |<span data-ttu-id="eff20-158">Описание</span><span class="sxs-lookup"><span data-stu-id="eff20-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="eff20-159">0x4</span><span class="sxs-lookup"><span data-stu-id="eff20-159">0x4</span></span> | <span data-ttu-id="eff20-160">Возвращать только имена свойств, которые определяют ключи.</span><span class="sxs-lookup"><span data-stu-id="eff20-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="eff20-161">0x8</span><span class="sxs-lookup"><span data-stu-id="eff20-161">0x8</span></span> | <span data-ttu-id="eff20-162">Возвращать только имена свойств, которые являются ссылками на объекты.</span><span class="sxs-lookup"><span data-stu-id="eff20-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="eff20-163">Флаги группы 3</span><span class="sxs-lookup"><span data-stu-id="eff20-163">Group 3 flags</span></span> |<span data-ttu-id="eff20-164">значения</span><span class="sxs-lookup"><span data-stu-id="eff20-164">Value</span></span>  |<span data-ttu-id="eff20-165">Описание</span><span class="sxs-lookup"><span data-stu-id="eff20-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="eff20-166">0x10</span><span class="sxs-lookup"><span data-stu-id="eff20-166">0x10</span></span> | <span data-ttu-id="eff20-167">Возвращать только имена свойств, принадлежащих наиболее производному классу.</span><span class="sxs-lookup"><span data-stu-id="eff20-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="eff20-168">Исключите свойства из родительских классов.</span><span class="sxs-lookup"><span data-stu-id="eff20-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="eff20-169">0x20</span><span class="sxs-lookup"><span data-stu-id="eff20-169">0x20</span></span> | <span data-ttu-id="eff20-170">Возвращать только имена свойств, принадлежащих родительским классам.</span><span class="sxs-lookup"><span data-stu-id="eff20-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="eff20-171">0x30</span><span class="sxs-lookup"><span data-stu-id="eff20-171">0x30</span></span> | <span data-ttu-id="eff20-172">Возвращать только имена системных свойств.</span><span class="sxs-lookup"><span data-stu-id="eff20-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="eff20-173">0x40</span><span class="sxs-lookup"><span data-stu-id="eff20-173">0x40</span></span> | <span data-ttu-id="eff20-174">Возвращать только имена свойств, не являющихся системными.</span><span class="sxs-lookup"><span data-stu-id="eff20-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="eff20-175">Функция всегда выделяет новую `SAFEARRAY`, если она возвращает `WBEM_S_NO_ERROR`, а `pstrNames` всегда устанавливается в значение Point.</span><span class="sxs-lookup"><span data-stu-id="eff20-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="eff20-176">Возвращаемый массив может иметь 0 элементов, если свойства не соответствуют указанным фильтрам.</span><span class="sxs-lookup"><span data-stu-id="eff20-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="eff20-177">Если функция возвращает значение, отличное от `WBM_S_NO_ERROR`, Новая структура `SAFEARRAY` не возвращается.</span><span class="sxs-lookup"><span data-stu-id="eff20-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>
 
## <a name="requirements"></a><span data-ttu-id="eff20-178">Требования</span><span class="sxs-lookup"><span data-stu-id="eff20-178">Requirements</span></span>  
 <span data-ttu-id="eff20-179">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eff20-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eff20-180">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="eff20-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="eff20-181">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="eff20-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eff20-182">См. также</span><span class="sxs-lookup"><span data-stu-id="eff20-182">See also</span></span>

- [<span data-ttu-id="eff20-183">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="eff20-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
