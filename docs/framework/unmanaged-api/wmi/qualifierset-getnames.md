---
title: Функция QualifierSet_GetNames (Справочник по неуправляемым API)
description: Функция QualifierSet_GetNames извлекает имена квалификаторы из объекта или свойства.
ms.date: 11/06/2017
api_name:
- QualifierSet_GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_GetNames
helpviewer_keywords:
- QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2da6bc87a175851aa7b23b67075ce61e39f0b937
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555106"
---
# <a name="qualifiersetgetnames-function"></a><span data-ttu-id="e5684-103">Функция QualifierSet_GetNames</span><span class="sxs-lookup"><span data-stu-id="e5684-103">QualifierSet_GetNames function</span></span>
<span data-ttu-id="e5684-104">Возвращает имена всех квалификаторов или определенных квалификаторов, доступные из текущего объекта или свойства.</span><span class="sxs-lookup"><span data-stu-id="e5684-104">Retrieves the names of all the qualifiers or of certain qualifiers that are available from the current object or property.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="e5684-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5684-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
); 
```  

## <a name="parameters"></a><span data-ttu-id="e5684-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e5684-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="e5684-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="e5684-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="e5684-108">[in] Указатель на [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="e5684-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`   
<span data-ttu-id="e5684-109">[in] Одно из следующих значений, определяющих, какие имена, чтобы включить в перечисление или флаги.</span><span class="sxs-lookup"><span data-stu-id="e5684-109">[in] One of the following flags or values that specifies which names to include in the enumeration.</span></span>

|<span data-ttu-id="e5684-110">Константа</span><span class="sxs-lookup"><span data-stu-id="e5684-110">Constant</span></span>  |<span data-ttu-id="e5684-111">Значение</span><span class="sxs-lookup"><span data-stu-id="e5684-111">Value</span></span>  |<span data-ttu-id="e5684-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e5684-112">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="e5684-113">0</span><span class="sxs-lookup"><span data-stu-id="e5684-113">0</span></span> | <span data-ttu-id="e5684-114">Возвращает имена всех квалификаторов.</span><span class="sxs-lookup"><span data-stu-id="e5684-114">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="e5684-115">0x10</span><span class="sxs-lookup"><span data-stu-id="e5684-115">0x10</span></span> | <span data-ttu-id="e5684-116">Возвращать только имена квалификаторы объекту или текущего свойства.</span><span class="sxs-lookup"><span data-stu-id="e5684-116">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="e5684-117">Для свойства: Возвращает только квалификаторов, определенных в свойстве (включая переопределения), а не квалификаторы, распространяются из определения класса.</span><span class="sxs-lookup"><span data-stu-id="e5684-117">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="e5684-118">Для экземпляра: Возвращает только квалификатор с определенным экземпляром имена.</span><span class="sxs-lookup"><span data-stu-id="e5684-118">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="e5684-119">Для класса: Возвращать только квалификаторы для класса beiong производным.</span><span class="sxs-lookup"><span data-stu-id="e5684-119">For a class: Return only qualifiers specific to the class beiong derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="e5684-120">0x20</span><span class="sxs-lookup"><span data-stu-id="e5684-120">0x20</span></span> | <span data-ttu-id="e5684-121">Возврат только имена квалификаторы распространяются из другого объекта.</span><span class="sxs-lookup"><span data-stu-id="e5684-121">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="e5684-122">Для свойства: Возврат распространяются только квалификаторы к этому свойству из определения класса, а не из самого свойства.</span><span class="sxs-lookup"><span data-stu-id="e5684-122">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="e5684-123">Для экземпляра: Возврат только эти квалификаторы распространяются из определения класса.</span><span class="sxs-lookup"><span data-stu-id="e5684-123">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="e5684-124">Для класса: Возвращаемое значение, только те имена квалификатор, наследуемые от родительских классов.</span><span class="sxs-lookup"><span data-stu-id="e5684-124">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

<span data-ttu-id="e5684-125">`pstrNames` [out] Новый `SAFEARRAY` , содержащий запрошенную имена.</span><span class="sxs-lookup"><span data-stu-id="e5684-125">`pstrNames` [out] A new `SAFEARRAY` that contains the requested names.</span></span> <span data-ttu-id="e5684-126">Массив может иметь 0 элементов.</span><span class="sxs-lookup"><span data-stu-id="e5684-126">The array can have 0 elements.</span></span> <span data-ttu-id="e5684-127">Если возникает ошибка, новый `SAFEARRAY` не возвращается.</span><span class="sxs-lookup"><span data-stu-id="e5684-127">If an error occurs, a new `SAFEARRAY` is not returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="e5684-128">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e5684-128">Return value</span></span>

<span data-ttu-id="e5684-129">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="e5684-129">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e5684-130">Константа</span><span class="sxs-lookup"><span data-stu-id="e5684-130">Constant</span></span>  |<span data-ttu-id="e5684-131">Значение</span><span class="sxs-lookup"><span data-stu-id="e5684-131">Value</span></span>  |<span data-ttu-id="e5684-132">Описание:</span><span class="sxs-lookup"><span data-stu-id="e5684-132">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e5684-133">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e5684-133">0x80041008</span></span> | <span data-ttu-id="e5684-134">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="e5684-134">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e5684-135">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e5684-135">0x80041006</span></span> | <span data-ttu-id="e5684-136">Не хватает памяти, позволяющих начать новое перечисление.</span><span class="sxs-lookup"><span data-stu-id="e5684-136">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e5684-137">0</span><span class="sxs-lookup"><span data-stu-id="e5684-137">0</span></span> | <span data-ttu-id="e5684-138">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="e5684-138">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e5684-139">Примечания</span><span class="sxs-lookup"><span data-stu-id="e5684-139">Remarks</span></span>

<span data-ttu-id="e5684-140">Эта функция создает оболочку для вызова [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) метод.</span><span class="sxs-lookup"><span data-stu-id="e5684-140">This function wraps a call to the [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) method.</span></span>

<span data-ttu-id="e5684-141">После получения имена квалификатор, каждый префикс доступен по имени путем вызова [QualifierSet_Get](qualifierset-get.md) функции.</span><span class="sxs-lookup"><span data-stu-id="e5684-141">Once you've retrieved the qualifier names, you can access each qualifier by name by calling the [QualifierSet_Get](qualifierset-get.md) function.</span></span> 

<span data-ttu-id="e5684-142">Это не ошибка для данного объекта иметь нуль квалификаторы, поэтому число строк в `pstrNames` при возврате может быть равен 0, несмотря на то, что функция возвращает `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="e5684-142">It is not an error for a given object to have zero qualifiers, so the number of strings in `pstrNames` on return can be 0, even though the function returns `WBEM_S_NO_ERROR`.</span></span>

## <a name="requirements"></a><span data-ttu-id="e5684-143">Требования</span><span class="sxs-lookup"><span data-stu-id="e5684-143">Requirements</span></span>  
 <span data-ttu-id="e5684-144">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5684-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5684-145">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e5684-145">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e5684-146">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e5684-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5684-147">См. также</span><span class="sxs-lookup"><span data-stu-id="e5684-147">See also</span></span>
- [<span data-ttu-id="e5684-148">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="e5684-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
