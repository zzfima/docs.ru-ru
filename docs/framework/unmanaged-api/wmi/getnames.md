---
title: Функция GetNames (неуправляемая ссылка API)
description: Функция GetNames получает имена свойств объекта.
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
ms.openlocfilehash: 449f0ce9c291d4bbcad4947214e56ff46f55beed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174957"
---
# <a name="getnames-function"></a><span data-ttu-id="0f12e-103">Функция GetNames</span><span class="sxs-lookup"><span data-stu-id="0f12e-103">GetNames function</span></span>
<span data-ttu-id="0f12e-104">Получает подмножество имен или все имена свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="0f12e-104">Retrieves either a subset or all of the names of the properties of an object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="0f12e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f12e-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="0f12e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0f12e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="0f12e-107">(в) Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="0f12e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="0f12e-108">(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="0f12e-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="0f12e-109">(в) Указатель на действительное, `LPCWSTR` которое определяет имя квалификатора, работающего как часть фильтра.</span><span class="sxs-lookup"><span data-stu-id="0f12e-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="0f12e-110">Для получения дополнительной информации смотрите раздел [Замечания.](#remarks)</span><span class="sxs-lookup"><span data-stu-id="0f12e-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="0f12e-111">Этот параметр может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="0f12e-111">This parameter can be `null`.</span></span>

`lFlags`  
<span data-ttu-id="0f12e-112">(в) Комбинация битовых полей.</span><span class="sxs-lookup"><span data-stu-id="0f12e-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="0f12e-113">Для получения дополнительной информации смотрите раздел [Замечания.](#remarks)</span><span class="sxs-lookup"><span data-stu-id="0f12e-113">For more information, see the [Remarks](#remarks) section.</span></span>

<span data-ttu-id="0f12e-114">`pQualifierValue`(в) Указатель на действительную `VARIANT` структуру, инициализированную к значению фильтра.</span><span class="sxs-lookup"><span data-stu-id="0f12e-114">`pQualifierValue` [in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="0f12e-115">Этот параметр может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="0f12e-115">This parameter can be `null`.</span></span>

`pstrNames`  
<span data-ttu-id="0f12e-116">(ваут) Структура, `SAFEARRAY` содержащая имена свойств.</span><span class="sxs-lookup"><span data-stu-id="0f12e-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="0f12e-117">При входе этот параметр всегда `null`должен быть указателем на .</span><span class="sxs-lookup"><span data-stu-id="0f12e-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="0f12e-118">Дополнительную информацию можно узнать в разделе [«Замечания».](#remarks)</span><span class="sxs-lookup"><span data-stu-id="0f12e-118">See the [Remarks](#remarks) section for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="0f12e-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0f12e-119">Return value</span></span>

<span data-ttu-id="0f12e-120">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="0f12e-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0f12e-121">Постоянно</span><span class="sxs-lookup"><span data-stu-id="0f12e-121">Constant</span></span>  |<span data-ttu-id="0f12e-122">Значение</span><span class="sxs-lookup"><span data-stu-id="0f12e-122">Value</span></span>  |<span data-ttu-id="0f12e-123">Описание</span><span class="sxs-lookup"><span data-stu-id="0f12e-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="0f12e-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="0f12e-124">0x80041001</span></span> | <span data-ttu-id="0f12e-125">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="0f12e-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0f12e-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0f12e-126">0x80041008</span></span> | <span data-ttu-id="0f12e-127">Один или несколько параметров недействительны, или было указано неправильное сочетание флагов и параметров.</span><span class="sxs-lookup"><span data-stu-id="0f12e-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0f12e-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0f12e-128">0x80041006</span></span> | <span data-ttu-id="0f12e-129">Недостаточно памяти для выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="0f12e-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="0f12e-130">0</span><span class="sxs-lookup"><span data-stu-id="0f12e-130">0</span></span> | <span data-ttu-id="0f12e-131">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="0f12e-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="0f12e-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="0f12e-132">Remarks</span></span>

<span data-ttu-id="0f12e-133">Эта функция завершает вызов методом [IWbemClassObject::GetNames.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames)</span><span class="sxs-lookup"><span data-stu-id="0f12e-133">This function wraps a call to the [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) method.</span></span>

<span data-ttu-id="0f12e-134">Имя возвращается контролируется сочетанием флагов и параметров.</span><span class="sxs-lookup"><span data-stu-id="0f12e-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="0f12e-135">Например, функция может возвращать имена всех свойств или только имена ключевых свойств.</span><span class="sxs-lookup"><span data-stu-id="0f12e-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="0f12e-136">Первичный фильтр указан `lFlags` в параметре, а остальные параметры варьируются в зависимости от него.</span><span class="sxs-lookup"><span data-stu-id="0f12e-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="0f12e-137">Значения флага `lFlags` в битовых полях</span><span class="sxs-lookup"><span data-stu-id="0f12e-137">The flag values in `lFlags` are bit fields</span></span>

<span data-ttu-id="0f12e-138">Флаги, которые могут `lEnumFlags` быть переданы как аргумент, являются битовыми полями, которые определяются в файле заголовка *WbemCli.h,* или вы можете определить их как константы в коде.</span><span class="sxs-lookup"><span data-stu-id="0f12e-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="0f12e-139">Вы можете объединить один флаг из каждой группы с любым флагом из любой другой группы.</span><span class="sxs-lookup"><span data-stu-id="0f12e-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="0f12e-140">Тем не менее, флаги из той же группы являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="0f12e-140">However, flags from the same group are mutually exclusive.</span></span>

| <span data-ttu-id="0f12e-141">Флаги группы 1</span><span class="sxs-lookup"><span data-stu-id="0f12e-141">Group 1 flags</span></span> |<span data-ttu-id="0f12e-142">Значение</span><span class="sxs-lookup"><span data-stu-id="0f12e-142">Value</span></span>  |<span data-ttu-id="0f12e-143">Описание</span><span class="sxs-lookup"><span data-stu-id="0f12e-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="0f12e-144">0</span><span class="sxs-lookup"><span data-stu-id="0f12e-144">0</span></span> | <span data-ttu-id="0f12e-145">Верните все имена недвижимости.</span><span class="sxs-lookup"><span data-stu-id="0f12e-145">Return all property names.</span></span> <span data-ttu-id="0f12e-146">`strQualifierName`и `pQualifierVal` не используются.</span><span class="sxs-lookup"><span data-stu-id="0f12e-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="0f12e-147">1</span><span class="sxs-lookup"><span data-stu-id="0f12e-147">1</span></span> | <span data-ttu-id="0f12e-148">Возврат только свойств, которые имеют квалификатор имени, указанного параметром. `strQualifierName`</span><span class="sxs-lookup"><span data-stu-id="0f12e-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="0f12e-149">Если этот флаг используется, `strQualifierName`необходимо указать.</span><span class="sxs-lookup"><span data-stu-id="0f12e-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="0f12e-150">2</span><span class="sxs-lookup"><span data-stu-id="0f12e-150">2</span></span> |  <span data-ttu-id="0f12e-151">Возврат только свойств, не имеющие квалификатора имени, указанного параметром. `strQualifierName`</span><span class="sxs-lookup"><span data-stu-id="0f12e-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="0f12e-152">Если этот флаг используется, `strQualifierName`необходимо указать.</span><span class="sxs-lookup"><span data-stu-id="0f12e-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="0f12e-153">3</span><span class="sxs-lookup"><span data-stu-id="0f12e-153">3</span></span> | <span data-ttu-id="0f12e-154">Возврат только свойств, которые имеют квалификатор имени, указанного `wszQualifierName` параметром, `pQualifierVal` а также имеют значение, идентичное тому, которое указывает структура.</span><span class="sxs-lookup"><span data-stu-id="0f12e-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="0f12e-155">Если используется этот флаг, необходимо `wszQualifierName` указать `pQualifierValue`как a, так и a.</span><span class="sxs-lookup"><span data-stu-id="0f12e-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="0f12e-156">Флаги группы 2</span><span class="sxs-lookup"><span data-stu-id="0f12e-156">Group 2 flags</span></span> |<span data-ttu-id="0f12e-157">Значение</span><span class="sxs-lookup"><span data-stu-id="0f12e-157">Value</span></span>  |<span data-ttu-id="0f12e-158">Описание</span><span class="sxs-lookup"><span data-stu-id="0f12e-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="0f12e-159">0x4</span><span class="sxs-lookup"><span data-stu-id="0f12e-159">0x4</span></span> | <span data-ttu-id="0f12e-160">Верните только имена свойств, определяющих ключи.</span><span class="sxs-lookup"><span data-stu-id="0f12e-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="0f12e-161">0x8</span><span class="sxs-lookup"><span data-stu-id="0f12e-161">0x8</span></span> | <span data-ttu-id="0f12e-162">Верните только имена свойств, которые являются ссылками объектов.</span><span class="sxs-lookup"><span data-stu-id="0f12e-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="0f12e-163">Флаги группы 3</span><span class="sxs-lookup"><span data-stu-id="0f12e-163">Group 3 flags</span></span> |<span data-ttu-id="0f12e-164">Значение</span><span class="sxs-lookup"><span data-stu-id="0f12e-164">Value</span></span>  |<span data-ttu-id="0f12e-165">Описание</span><span class="sxs-lookup"><span data-stu-id="0f12e-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="0f12e-166">0x10</span><span class="sxs-lookup"><span data-stu-id="0f12e-166">0x10</span></span> | <span data-ttu-id="0f12e-167">Верните только имена свойств, которые принадлежат к наиболее производным классам.</span><span class="sxs-lookup"><span data-stu-id="0f12e-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="0f12e-168">Исключить свойства из родительских классов.</span><span class="sxs-lookup"><span data-stu-id="0f12e-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="0f12e-169">0x20</span><span class="sxs-lookup"><span data-stu-id="0f12e-169">0x20</span></span> | <span data-ttu-id="0f12e-170">Верните только имена свойств, которые принадлежат к родительским классам.</span><span class="sxs-lookup"><span data-stu-id="0f12e-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="0f12e-171">0x30</span><span class="sxs-lookup"><span data-stu-id="0f12e-171">0x30</span></span> | <span data-ttu-id="0f12e-172">Верните только названия системных свойств.</span><span class="sxs-lookup"><span data-stu-id="0f12e-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="0f12e-173">0x40</span><span class="sxs-lookup"><span data-stu-id="0f12e-173">0x40</span></span> | <span data-ttu-id="0f12e-174">Верните только названия несистемных свойств.</span><span class="sxs-lookup"><span data-stu-id="0f12e-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="0f12e-175">Функция всегда выделяет новый, `SAFEARRAY` `WBEM_S_NO_ERROR`если `pstrNames` он возвращается, и всегда настроен ателье на него.</span><span class="sxs-lookup"><span data-stu-id="0f12e-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="0f12e-176">Возвращаемый массив может иметь 0 элементов, если свойства не соответствуют указанным фильтрам.</span><span class="sxs-lookup"><span data-stu-id="0f12e-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="0f12e-177">Если функция возвращает значение, `WBM_S_NO_ERROR`кроме, `SAFEARRAY` новая структура не возвращается.</span><span class="sxs-lookup"><span data-stu-id="0f12e-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="0f12e-178">Требования</span><span class="sxs-lookup"><span data-stu-id="0f12e-178">Requirements</span></span>  
 <span data-ttu-id="0f12e-179">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f12e-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f12e-180">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="0f12e-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="0f12e-181">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0f12e-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f12e-182">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0f12e-182">See also</span></span>

- [<span data-ttu-id="0f12e-183">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="0f12e-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
