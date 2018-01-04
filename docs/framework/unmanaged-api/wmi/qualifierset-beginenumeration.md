---
title: "Функция QualifierSet_BeginEnumeration (Справочник по неуправляемым API)"
description: "Функция QualifierSet_BeginEnumeration Сбрасывает перечислитель квалификаторы объекта."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_BeginEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_BeginEnumeration
helpviewer_keywords: QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 440dde03f4ed138a33eb6f817723d7c5c74f6d46
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetbeginenumeration-function"></a><span data-ttu-id="91d65-103">Функция QualifierSet_BeginEnumeration</span><span class="sxs-lookup"><span data-stu-id="91d65-103">QualifierSet_BeginEnumeration function</span></span>
<span data-ttu-id="91d65-104">Возвращает перечислитель квалификаторы объект в начало перечисления.</span><span class="sxs-lookup"><span data-stu-id="91d65-104">Resets an enumerator of the qualifiers of an object to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="91d65-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="91d65-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="91d65-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="91d65-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="91d65-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="91d65-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="91d65-108">[in] Указатель на [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="91d65-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`lFlags`   
<span data-ttu-id="91d65-109">[in] Побитовое сочетание флагов или значений, описанных в [примечания](#remarks) раздел, который указывает квалификаторы для включения в перечислении.</span><span class="sxs-lookup"><span data-stu-id="91d65-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that specifies the qualifiers to include in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="91d65-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="91d65-110">Return value</span></span>

<span data-ttu-id="91d65-111">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="91d65-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="91d65-112">Константа</span><span class="sxs-lookup"><span data-stu-id="91d65-112">Constant</span></span>  |<span data-ttu-id="91d65-113">Значение</span><span class="sxs-lookup"><span data-stu-id="91d65-113">Value</span></span>  |<span data-ttu-id="91d65-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="91d65-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="91d65-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="91d65-115">0x80041008</span></span> | <span data-ttu-id="91d65-116">`lFlags` Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="91d65-116">The `lFlags` parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="91d65-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="91d65-117">0x8004101d</span></span> | <span data-ttu-id="91d65-118">Второй вызов `QualifierSet_BeginEnumeration` была произведена без промежуточных вызовов [ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="91d65-118">A second call to `QualifierSet_BeginEnumeration` was made without an intervening call to [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="91d65-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="91d65-119">0x80041006</span></span> | <span data-ttu-id="91d65-120">Чтобы начать новое перечисление доступен не хватает памяти.</span><span class="sxs-lookup"><span data-stu-id="91d65-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="91d65-121">0</span><span class="sxs-lookup"><span data-stu-id="91d65-121">0</span></span> | <span data-ttu-id="91d65-122">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="91d65-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="91d65-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="91d65-123">Remarks</span></span>

<span data-ttu-id="91d65-124">Эта функция создает оболочку для вызова [IWbemQualifierSet::BeginEnumeration](https://msdn.microsoft.com/library/aa391861(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="91d65-124">This function wraps a call to the [IWbemQualifierSet::BeginEnumeration](https://msdn.microsoft.com/library/aa391861(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="91d65-125">Для перечисления всех квалификаторов для объекта, этот метод должен вызываться до первого вызова [QualifierSet_Next](qualifierset-next.md).</span><span class="sxs-lookup"><span data-stu-id="91d65-125">To enumerate all of the qualifiers on an object, this method must be called before the first call to [QualifierSet_Next](qualifierset-next.md).</span></span> <span data-ttu-id="91d65-126">Гарантируется, что порядок, в котором перечислены квалификаторы является инвариантным для данного перечисления.</span><span class="sxs-lookup"><span data-stu-id="91d65-126">The order in which qualifiers are enumerated is guaranteed to be invariant for a given enumeration.</span></span>

<span data-ttu-id="91d65-127">Флаги, которые могут быть переданы как `lEnumFlags` аргумент определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде.</span><span class="sxs-lookup"><span data-stu-id="91d65-127">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>   

|<span data-ttu-id="91d65-128">Константа</span><span class="sxs-lookup"><span data-stu-id="91d65-128">Constant</span></span>  |<span data-ttu-id="91d65-129">Значение</span><span class="sxs-lookup"><span data-stu-id="91d65-129">Value</span></span>  |<span data-ttu-id="91d65-130">Описание</span><span class="sxs-lookup"><span data-stu-id="91d65-130">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="91d65-131">0</span><span class="sxs-lookup"><span data-stu-id="91d65-131">0</span></span> | <span data-ttu-id="91d65-132">Возвращает имена всех квалификаторов.</span><span class="sxs-lookup"><span data-stu-id="91d65-132">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="91d65-133">0x10</span><span class="sxs-lookup"><span data-stu-id="91d65-133">0x10</span></span> | <span data-ttu-id="91d65-134">Возврате только имена квалификаторов текущее свойство или объект.</span><span class="sxs-lookup"><span data-stu-id="91d65-134">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="91d65-135">Для свойства: вернуться только квалификаторами определенные свойства (включая переопределения), а не эти квалификаторы распространены из определения класса.</span><span class="sxs-lookup"><span data-stu-id="91d65-135">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="91d65-136">Для экземпляра: возвращают только имена квалификатор данного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="91d65-136">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="91d65-137">Для класса: вернуться только квалификаторами определенного класса beiong производным.</span><span class="sxs-lookup"><span data-stu-id="91d65-137">For a class: Return only qualifiers specific to the class beiong derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="91d65-138">0x20</span><span class="sxs-lookup"><span data-stu-id="91d65-138">0x20</span></span> | <span data-ttu-id="91d65-139">Возвращении только имена квалификаторов распространяются из другого объекта.</span><span class="sxs-lookup"><span data-stu-id="91d65-139">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="91d65-140">Для свойства: возврат распространяются только квалификаторами этому свойству из определения класса, а не из самого свойства.</span><span class="sxs-lookup"><span data-stu-id="91d65-140">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="91d65-141">Для экземпляра: возврат распространяются только те квалификаторы из определения класса.</span><span class="sxs-lookup"><span data-stu-id="91d65-141">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="91d65-142">Для класса: возвращают только те имена квалификатор, наследуемые от родительских классов.</span><span class="sxs-lookup"><span data-stu-id="91d65-142">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="91d65-143">Требования</span><span class="sxs-lookup"><span data-stu-id="91d65-143">Requirements</span></span>  
 <span data-ttu-id="91d65-144">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91d65-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91d65-145">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="91d65-145">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="91d65-146">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="91d65-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91d65-147">См. также</span><span class="sxs-lookup"><span data-stu-id="91d65-147">See also</span></span>  
[<span data-ttu-id="91d65-148">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="91d65-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
