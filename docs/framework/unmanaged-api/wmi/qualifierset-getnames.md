---
title: "Функция QualifierSet_GetNames (Справочник по неуправляемым API)"
description: "Функция QualifierSet_GetNames извлекает имена квалификаторов из объекта или свойства."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
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
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6077b448c2644f68d12679cf208ee921c2af119a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetgetnames-function"></a><span data-ttu-id="41662-103">Функция QualifierSet_GetNames</span><span class="sxs-lookup"><span data-stu-id="41662-103">QualifierSet_GetNames function</span></span>
<span data-ttu-id="41662-104">Получает имена всех квалификаторов или определенных квалификаторов, которые доступны из текущего объекта или свойства.</span><span class="sxs-lookup"><span data-stu-id="41662-104">Retrieves the names of all the qualifiers or of certain qualifiers that are available from the current object or property.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="41662-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41662-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
); 
```  

## <a name="parameters"></a><span data-ttu-id="41662-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="41662-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="41662-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="41662-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="41662-108">[in] Указатель на [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="41662-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`lFlags`   
<span data-ttu-id="41662-109">[in] Одно из следующих флагов или значений, определяющее, какие имена включаемых в перечислении.</span><span class="sxs-lookup"><span data-stu-id="41662-109">[in] One of the following flags or values that specifies which names to include in the enumeration.</span></span>

|<span data-ttu-id="41662-110">Константа</span><span class="sxs-lookup"><span data-stu-id="41662-110">Constant</span></span>  |<span data-ttu-id="41662-111">Значение</span><span class="sxs-lookup"><span data-stu-id="41662-111">Value</span></span>  |<span data-ttu-id="41662-112">Описание</span><span class="sxs-lookup"><span data-stu-id="41662-112">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="41662-113">0</span><span class="sxs-lookup"><span data-stu-id="41662-113">0</span></span> | <span data-ttu-id="41662-114">Возвращает имена всех квалификаторов.</span><span class="sxs-lookup"><span data-stu-id="41662-114">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="41662-115">0x10</span><span class="sxs-lookup"><span data-stu-id="41662-115">0x10</span></span> | <span data-ttu-id="41662-116">Возврате только имена квалификаторов текущее свойство или объект.</span><span class="sxs-lookup"><span data-stu-id="41662-116">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="41662-117">Для свойства: вернуться только квалификаторами определенные свойства (включая переопределения), а не эти квалификаторы распространены из определения класса.</span><span class="sxs-lookup"><span data-stu-id="41662-117">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="41662-118">Для экземпляра: возвращают только имена квалификатор данного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="41662-118">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="41662-119">Для класса: вернуться только квалификаторами определенного класса beiong производным.</span><span class="sxs-lookup"><span data-stu-id="41662-119">For a class: Return only qualifiers specific to the class beiong derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="41662-120">0x20</span><span class="sxs-lookup"><span data-stu-id="41662-120">0x20</span></span> | <span data-ttu-id="41662-121">Возвращении только имена квалификаторов распространяются из другого объекта.</span><span class="sxs-lookup"><span data-stu-id="41662-121">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="41662-122">Для свойства: возврат распространяются только квалификаторами этому свойству из определения класса, а не из самого свойства.</span><span class="sxs-lookup"><span data-stu-id="41662-122">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="41662-123">Для экземпляра: возврат распространяются только те квалификаторы из определения класса.</span><span class="sxs-lookup"><span data-stu-id="41662-123">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="41662-124">Для класса: возвращают только те имена квалификатор, наследуемые от родительских классов.</span><span class="sxs-lookup"><span data-stu-id="41662-124">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

<span data-ttu-id="41662-125">`pstrNames`[out] Новый `SAFEARRAY` , содержащий запрошенную имена.</span><span class="sxs-lookup"><span data-stu-id="41662-125">`pstrNames` [out] A new `SAFEARRAY` that contains the requested names.</span></span> <span data-ttu-id="41662-126">Массив может иметь 0 элементов.</span><span class="sxs-lookup"><span data-stu-id="41662-126">The array can have 0 elements.</span></span> <span data-ttu-id="41662-127">Если возникает ошибка, новый `SAFEARRAY` не возвращается.</span><span class="sxs-lookup"><span data-stu-id="41662-127">If an error occurs, a new `SAFEARRAY` is not returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="41662-128">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="41662-128">Return value</span></span>

<span data-ttu-id="41662-129">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="41662-129">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="41662-130">Константа</span><span class="sxs-lookup"><span data-stu-id="41662-130">Constant</span></span>  |<span data-ttu-id="41662-131">Значение</span><span class="sxs-lookup"><span data-stu-id="41662-131">Value</span></span>  |<span data-ttu-id="41662-132">Описание:</span><span class="sxs-lookup"><span data-stu-id="41662-132">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="41662-133">0x80041008</span><span class="sxs-lookup"><span data-stu-id="41662-133">0x80041008</span></span> | <span data-ttu-id="41662-134">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="41662-134">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="41662-135">0x80041006</span><span class="sxs-lookup"><span data-stu-id="41662-135">0x80041006</span></span> | <span data-ttu-id="41662-136">Чтобы начать новое перечисление доступен не хватает памяти.</span><span class="sxs-lookup"><span data-stu-id="41662-136">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="41662-137">0</span><span class="sxs-lookup"><span data-stu-id="41662-137">0</span></span> | <span data-ttu-id="41662-138">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="41662-138">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="41662-139">Примечания</span><span class="sxs-lookup"><span data-stu-id="41662-139">Remarks</span></span>

<span data-ttu-id="41662-140">Эта функция создает оболочку для вызова [IWbemQualifierSet::GetNames](https://msdn.microsoft.com/library/aa391868(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="41662-140">This function wraps a call to the [IWbemQualifierSet::GetNames](https://msdn.microsoft.com/library/aa391868(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="41662-141">После получения имена квалификаторов, к каждой квалификатор по имени путем вызова [QualifierSet_Get](qualifierset-get.md) функции.</span><span class="sxs-lookup"><span data-stu-id="41662-141">Once you've retrieved the qualifier names, you can access each qualifier by name by calling the [QualifierSet_Get](qualifierset-get.md) function.</span></span> 

<span data-ttu-id="41662-142">Он не является ошибкой для данного объекта иметь ноль квалификаторы, поэтому число строк в `pstrNames` при возвращении может быть 0, несмотря на то, что функция возвращает `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="41662-142">It is not an error for a given object to have zero qualifiers, so the number of strings in `pstrNames` on return can be 0, even though the function returns `WBEM_S_NO_ERROR`.</span></span>

## <a name="requirements"></a><span data-ttu-id="41662-143">Требования</span><span class="sxs-lookup"><span data-stu-id="41662-143">Requirements</span></span>  
 <span data-ttu-id="41662-144">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41662-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41662-145">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="41662-145">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="41662-146">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="41662-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41662-147">См. также</span><span class="sxs-lookup"><span data-stu-id="41662-147">See also</span></span>  
[<span data-ttu-id="41662-148">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="41662-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
