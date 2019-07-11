---
title: Функция GetNames (Справочник по неуправляемым API)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e75bf9aab820216373f2f33fe8aa567f10befcb1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746518"
---
# <a name="getnames-function"></a><span data-ttu-id="6db0c-103">Функция GetNames</span><span class="sxs-lookup"><span data-stu-id="6db0c-103">GetNames function</span></span>
<span data-ttu-id="6db0c-104">Получает подмножество имен или все имена свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="6db0c-104">Retrieves either a subset or all of the names of the properties of an object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="6db0c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6db0c-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="6db0c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6db0c-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="6db0c-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="6db0c-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="6db0c-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="6db0c-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="6db0c-109">[in] Указатель на допустимую `LPCWSTR` , задающий имя квалификатора, которое работает как часть фильтра.</span><span class="sxs-lookup"><span data-stu-id="6db0c-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="6db0c-110">Дополнительные сведения см. в разделе ["Примечания"](#remarks) раздел.</span><span class="sxs-lookup"><span data-stu-id="6db0c-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="6db0c-111">Этот параметр может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="6db0c-111">This parameter can be `null`.</span></span> 

`lFlags`  
<span data-ttu-id="6db0c-112">[in] Сочетание битовых полей.</span><span class="sxs-lookup"><span data-stu-id="6db0c-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="6db0c-113">Дополнительные сведения см. в разделе ["Примечания"](#remarks) раздел.</span><span class="sxs-lookup"><span data-stu-id="6db0c-113">For more information, see the [Remarks](#remarks) section.</span></span>

`pQualifierValue`   
<span data-ttu-id="6db0c-114">[in] Указатель на допустимую `VARIANT` структуру, инициализированную со значением фильтра.</span><span class="sxs-lookup"><span data-stu-id="6db0c-114">[in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="6db0c-115">Этот параметр может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="6db0c-115">This parameter can be `null`.</span></span> 

`pstrNames`  
<span data-ttu-id="6db0c-116">[out] Объект `SAFEARRAY` структуру, которая содержит имена свойств.</span><span class="sxs-lookup"><span data-stu-id="6db0c-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="6db0c-117">На запись в этот параметр всегда должен быть указателем на `null`.</span><span class="sxs-lookup"><span data-stu-id="6db0c-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="6db0c-118">См. в разделе ["Примечания"](#remarks) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="6db0c-118">See the [Remarks](#remarks) section for more information.</span></span> 

## <a name="return-value"></a><span data-ttu-id="6db0c-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6db0c-119">Return value</span></span>

<span data-ttu-id="6db0c-120">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="6db0c-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="6db0c-121">Константа</span><span class="sxs-lookup"><span data-stu-id="6db0c-121">Constant</span></span>  |<span data-ttu-id="6db0c-122">Значение</span><span class="sxs-lookup"><span data-stu-id="6db0c-122">Value</span></span>  |<span data-ttu-id="6db0c-123">Описание</span><span class="sxs-lookup"><span data-stu-id="6db0c-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="6db0c-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="6db0c-124">0x80041001</span></span> | <span data-ttu-id="6db0c-125">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="6db0c-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="6db0c-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="6db0c-126">0x80041008</span></span> | <span data-ttu-id="6db0c-127">Один или несколько параметров недопустимы, или указано неверное сочетание флагов и параметры.</span><span class="sxs-lookup"><span data-stu-id="6db0c-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="6db0c-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="6db0c-128">0x80041006</span></span> | <span data-ttu-id="6db0c-129">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="6db0c-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="6db0c-130">0</span><span class="sxs-lookup"><span data-stu-id="6db0c-130">0</span></span> | <span data-ttu-id="6db0c-131">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="6db0c-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="6db0c-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="6db0c-132">Remarks</span></span>

<span data-ttu-id="6db0c-133">Эта функция создает оболочку для вызова [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) метод.</span><span class="sxs-lookup"><span data-stu-id="6db0c-133">This function wraps a call to the [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) method.</span></span>

<span data-ttu-id="6db0c-134">Именованных возвращаемых контролируются с помощью сочетания флагов и параметры.</span><span class="sxs-lookup"><span data-stu-id="6db0c-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="6db0c-135">Например функция может вернуть имена всех свойств или только имена ключевых свойств.</span><span class="sxs-lookup"><span data-stu-id="6db0c-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="6db0c-136">Основным фильтром указывается в `lFlags` параметра и другие параметры зависят от его.</span><span class="sxs-lookup"><span data-stu-id="6db0c-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="6db0c-137">Флаг значения в `lFlags` являются битовые поля</span><span class="sxs-lookup"><span data-stu-id="6db0c-137">The flag values in `lFlags` are bit fields</span></span>

<span data-ttu-id="6db0c-138">Флаги, которые могут передаваться как `lEnumFlags` аргумента находятся в битовых полей, которые определены в *WbemCli.h* файл заголовка, или их можно определить как константы в коде.</span><span class="sxs-lookup"><span data-stu-id="6db0c-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="6db0c-139">Вы можете объединить один флаг из каждой группы с любой флаг из другой группы.</span><span class="sxs-lookup"><span data-stu-id="6db0c-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="6db0c-140">Однако флаги из одной группы являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="6db0c-140">However, flags from the same group are mutually exclusive.</span></span> 

| <span data-ttu-id="6db0c-141">Флаги группы 1</span><span class="sxs-lookup"><span data-stu-id="6db0c-141">Group 1 flags</span></span> |<span data-ttu-id="6db0c-142">Значение</span><span class="sxs-lookup"><span data-stu-id="6db0c-142">Value</span></span>  |<span data-ttu-id="6db0c-143">Описание</span><span class="sxs-lookup"><span data-stu-id="6db0c-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="6db0c-144">0</span><span class="sxs-lookup"><span data-stu-id="6db0c-144">0</span></span> | <span data-ttu-id="6db0c-145">Возвращает имена всех свойств.</span><span class="sxs-lookup"><span data-stu-id="6db0c-145">Return all property names.</span></span> <span data-ttu-id="6db0c-146">`strQualifierName` и `pQualifierVal` не используются.</span><span class="sxs-lookup"><span data-stu-id="6db0c-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="6db0c-147">1</span><span class="sxs-lookup"><span data-stu-id="6db0c-147">1</span></span> | <span data-ttu-id="6db0c-148">Возвращать только свойства, которые имеют квалификатор именем, указанным `strQualifierName` параметра.</span><span class="sxs-lookup"><span data-stu-id="6db0c-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="6db0c-149">Если этот флаг используется, необходимо указать `strQualifierName`.</span><span class="sxs-lookup"><span data-stu-id="6db0c-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="6db0c-150">2</span><span class="sxs-lookup"><span data-stu-id="6db0c-150">2</span></span> |  <span data-ttu-id="6db0c-151">Возвращать только свойства, которые не имеют квалификатор именем, указанным `strQualifierName` параметра.</span><span class="sxs-lookup"><span data-stu-id="6db0c-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="6db0c-152">Если этот флаг используется, необходимо указать `strQualifierName`.</span><span class="sxs-lookup"><span data-stu-id="6db0c-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="6db0c-153">3</span><span class="sxs-lookup"><span data-stu-id="6db0c-153">3</span></span> | <span data-ttu-id="6db0c-154">Возвращать только те свойства, которые имеют квалификатор именем, указанным `wszQualifierName` параметр и также имеют значения, идентичны данным, определяемое `pQualifierVal` структуры.</span><span class="sxs-lookup"><span data-stu-id="6db0c-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="6db0c-155">Если этот флаг используется, необходимо указать и `wszQualifierName` и `pQualifierValue`.</span><span class="sxs-lookup"><span data-stu-id="6db0c-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="6db0c-156">Флаги группы 2</span><span class="sxs-lookup"><span data-stu-id="6db0c-156">Group 2 flags</span></span> |<span data-ttu-id="6db0c-157">Значение</span><span class="sxs-lookup"><span data-stu-id="6db0c-157">Value</span></span>  |<span data-ttu-id="6db0c-158">Описание</span><span class="sxs-lookup"><span data-stu-id="6db0c-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="6db0c-159">0x4</span><span class="sxs-lookup"><span data-stu-id="6db0c-159">0x4</span></span> | <span data-ttu-id="6db0c-160">Возвращать только имена свойств, определяющих ключи.</span><span class="sxs-lookup"><span data-stu-id="6db0c-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="6db0c-161">0x8</span><span class="sxs-lookup"><span data-stu-id="6db0c-161">0x8</span></span> | <span data-ttu-id="6db0c-162">Возвращаемое только имена свойств, которые являются ссылками на объект.</span><span class="sxs-lookup"><span data-stu-id="6db0c-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="6db0c-163">Группа 3 флаги</span><span class="sxs-lookup"><span data-stu-id="6db0c-163">Group 3 flags</span></span> |<span data-ttu-id="6db0c-164">Значение</span><span class="sxs-lookup"><span data-stu-id="6db0c-164">Value</span></span>  |<span data-ttu-id="6db0c-165">Описание</span><span class="sxs-lookup"><span data-stu-id="6db0c-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="6db0c-166">0x10</span><span class="sxs-lookup"><span data-stu-id="6db0c-166">0x10</span></span> | <span data-ttu-id="6db0c-167">Возвращать только имена свойств, которые принадлежат к наиболее производный класс.</span><span class="sxs-lookup"><span data-stu-id="6db0c-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="6db0c-168">Исключите свойства родительского класса.</span><span class="sxs-lookup"><span data-stu-id="6db0c-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="6db0c-169">0x20</span><span class="sxs-lookup"><span data-stu-id="6db0c-169">0x20</span></span> | <span data-ttu-id="6db0c-170">Возвращать только имена свойств, принадлежащих родительских классов.</span><span class="sxs-lookup"><span data-stu-id="6db0c-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="6db0c-171">0x30</span><span class="sxs-lookup"><span data-stu-id="6db0c-171">0x30</span></span> | <span data-ttu-id="6db0c-172">Возвращать только имена системных свойств.</span><span class="sxs-lookup"><span data-stu-id="6db0c-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="6db0c-173">0x40</span><span class="sxs-lookup"><span data-stu-id="6db0c-173">0x40</span></span> | <span data-ttu-id="6db0c-174">Возвращать только имена несистемных свойств.</span><span class="sxs-lookup"><span data-stu-id="6db0c-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="6db0c-175">Функция всегда выделяет новый `SAFEARRAY` при его использовании возвращается `WBEM_S_NO_ERROR`, и `pstrNames` всегда имеет значение указывать на него.</span><span class="sxs-lookup"><span data-stu-id="6db0c-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="6db0c-176">Возвращаемый массив может иметь 0 элементов, если нет свойств, соответствующих заданным фильтрам.</span><span class="sxs-lookup"><span data-stu-id="6db0c-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="6db0c-177">Если функция возвращает значение, отличное от `WBM_S_NO_ERROR`, новый `SAFEARRAY` структуры не возвращается.</span><span class="sxs-lookup"><span data-stu-id="6db0c-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>
 
## <a name="requirements"></a><span data-ttu-id="6db0c-178">Требования</span><span class="sxs-lookup"><span data-stu-id="6db0c-178">Requirements</span></span>  
 <span data-ttu-id="6db0c-179">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6db0c-179">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6db0c-180">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="6db0c-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="6db0c-181">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6db0c-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6db0c-182">См. также</span><span class="sxs-lookup"><span data-stu-id="6db0c-182">See also</span></span>

- [<span data-ttu-id="6db0c-183">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="6db0c-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
