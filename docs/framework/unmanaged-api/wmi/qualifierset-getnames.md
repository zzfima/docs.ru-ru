---
title: Функция QualifierSet_GetNames (Справочник по неуправляемым API)
description: Функция QualifierSet_GetNames извлекает имена квалификаторов из объекта или свойства.
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
ms.openlocfilehash: bd0a67987dd8ffa825114726d066249aed40cf05
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141691"
---
# <a name="qualifierset_getnames-function"></a><span data-ttu-id="c0a4b-103">Функция QualifierSet_GetNames</span><span class="sxs-lookup"><span data-stu-id="c0a4b-103">QualifierSet_GetNames function</span></span>

<span data-ttu-id="c0a4b-104">Извлекает имена всех квалификаторов или определенных квалификаторов, доступных из текущего объекта или свойства.</span><span class="sxs-lookup"><span data-stu-id="c0a4b-104">Retrieves the names of all the qualifiers or of certain qualifiers that are available from the current object or property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="c0a4b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0a4b-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
);
```

## <a name="parameters"></a><span data-ttu-id="c0a4b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c0a4b-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="c0a4b-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="c0a4b-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="c0a4b-108">окне Указатель на экземпляр [ивбемкуалифиерсет](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="c0a4b-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="c0a4b-109">окне Один из следующих флагов или значений, указывающих, какие имена следует включить в перечисление.</span><span class="sxs-lookup"><span data-stu-id="c0a4b-109">[in] One of the following flags or values that specifies which names to include in the enumeration.</span></span>

|<span data-ttu-id="c0a4b-110">Константа</span><span class="sxs-lookup"><span data-stu-id="c0a4b-110">Constant</span></span>  |<span data-ttu-id="c0a4b-111">значения</span><span class="sxs-lookup"><span data-stu-id="c0a4b-111">Value</span></span>  |<span data-ttu-id="c0a4b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c0a4b-112">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="c0a4b-113">0</span><span class="sxs-lookup"><span data-stu-id="c0a4b-113">0</span></span> | <span data-ttu-id="c0a4b-114">Возвращает имена всех квалификаторов.</span><span class="sxs-lookup"><span data-stu-id="c0a4b-114">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="c0a4b-115">0x10</span><span class="sxs-lookup"><span data-stu-id="c0a4b-115">0x10</span></span> | <span data-ttu-id="c0a4b-116">Возврат только имен квалификаторов, относящихся к текущему свойству или объекту.</span><span class="sxs-lookup"><span data-stu-id="c0a4b-116">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="c0a4b-117">Для свойства: возвращают только квалификаторы, относящиеся к свойству (включая переопределения), а не эти квалификаторы, распространенные из определения класса.</span><span class="sxs-lookup"><span data-stu-id="c0a4b-117">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="c0a4b-118">Для экземпляра: возвращать только имена квалификаторов, относящиеся только к экземпляру.</span><span class="sxs-lookup"><span data-stu-id="c0a4b-118">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="c0a4b-119">Для класса: возвращать только квалификаторы, относящиеся к производному классу.</span><span class="sxs-lookup"><span data-stu-id="c0a4b-119">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="c0a4b-120">0x20</span><span class="sxs-lookup"><span data-stu-id="c0a4b-120">0x20</span></span> | <span data-ttu-id="c0a4b-121">Возвращать только имена квалификаторов, распространяемых из другого объекта.</span><span class="sxs-lookup"><span data-stu-id="c0a4b-121">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="c0a4b-122">Для свойства: возвращают только те квалификаторы, которые распространяются на это свойство из определения класса, а не из самого свойства.</span><span class="sxs-lookup"><span data-stu-id="c0a4b-122">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="c0a4b-123">Для экземпляра: возврат только тех квалификаторов, которые распространяются из определения класса.</span><span class="sxs-lookup"><span data-stu-id="c0a4b-123">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="c0a4b-124">Для класса: возвращают только имена квалификаторов, унаследованные от родительских классов.</span><span class="sxs-lookup"><span data-stu-id="c0a4b-124">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

`pstrNames`\
<span data-ttu-id="c0a4b-125">заполняет Новый `SAFEARRAY`, содержащий запрошенные имена.</span><span class="sxs-lookup"><span data-stu-id="c0a4b-125">[out] A new `SAFEARRAY` that contains the requested names.</span></span> <span data-ttu-id="c0a4b-126">Массив может иметь 0 элементов.</span><span class="sxs-lookup"><span data-stu-id="c0a4b-126">The array can have 0 elements.</span></span> <span data-ttu-id="c0a4b-127">При возникновении ошибки новый `SAFEARRAY` не возвращается.</span><span class="sxs-lookup"><span data-stu-id="c0a4b-127">If an error occurs, a new `SAFEARRAY` is not returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="c0a4b-128">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c0a4b-128">Return value</span></span>

<span data-ttu-id="c0a4b-129">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="c0a4b-129">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c0a4b-130">Константа</span><span class="sxs-lookup"><span data-stu-id="c0a4b-130">Constant</span></span>  |<span data-ttu-id="c0a4b-131">значения</span><span class="sxs-lookup"><span data-stu-id="c0a4b-131">Value</span></span>  |<span data-ttu-id="c0a4b-132">Описание</span><span class="sxs-lookup"><span data-stu-id="c0a4b-132">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c0a4b-133">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c0a4b-133">0x80041008</span></span> | <span data-ttu-id="c0a4b-134">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="c0a4b-134">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="c0a4b-135">0x80041006</span><span class="sxs-lookup"><span data-stu-id="c0a4b-135">0x80041006</span></span> | <span data-ttu-id="c0a4b-136">Недостаточно памяти для начала нового перечисления.</span><span class="sxs-lookup"><span data-stu-id="c0a4b-136">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="c0a4b-137">0</span><span class="sxs-lookup"><span data-stu-id="c0a4b-137">0</span></span> | <span data-ttu-id="c0a4b-138">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="c0a4b-138">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="c0a4b-139">Заметки</span><span class="sxs-lookup"><span data-stu-id="c0a4b-139">Remarks</span></span>

<span data-ttu-id="c0a4b-140">Эта функция заключает в оболочку вызов метода [ивбемкуалифиерсет:: Names](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) .</span><span class="sxs-lookup"><span data-stu-id="c0a4b-140">This function wraps a call to the [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) method.</span></span>

<span data-ttu-id="c0a4b-141">После получения имен квалификаторов можно получить доступ к каждому квалификатору по имени, вызвав функцию [QualifierSet_Get](qualifierset-get.md) .</span><span class="sxs-lookup"><span data-stu-id="c0a4b-141">Once you've retrieved the qualifier names, you can access each qualifier by name by calling the [QualifierSet_Get](qualifierset-get.md) function.</span></span>

<span data-ttu-id="c0a4b-142">Не является ошибкой, чтобы заданный объект имел нулевые квалификаторы, так что число строк в `pstrNames` возвращаемого значения может равняться 0, даже если функция возвращает `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="c0a4b-142">It is not an error for a given object to have zero qualifiers, so the number of strings in `pstrNames` on return can be 0, even though the function returns `WBEM_S_NO_ERROR`.</span></span>

## <a name="requirements"></a><span data-ttu-id="c0a4b-143">Требования</span><span class="sxs-lookup"><span data-stu-id="c0a4b-143">Requirements</span></span>

<span data-ttu-id="c0a4b-144">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0a4b-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="c0a4b-145">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="c0a4b-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="c0a4b-146">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c0a4b-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c0a4b-147">См. также</span><span class="sxs-lookup"><span data-stu-id="c0a4b-147">See also</span></span>

- [<span data-ttu-id="c0a4b-148">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="c0a4b-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
