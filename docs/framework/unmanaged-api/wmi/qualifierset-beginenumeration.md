---
title: Функция QualifierSet_BeginEnumeration (Справочник по неуправляемым API)
description: Функция QualifierSet_BeginEnumeration Сбрасывает перечислитель квалификаторов объекта.
ms.date: 11/06/2017
api_name:
- QualifierSet_BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_BeginEnumeration
helpviewer_keywords:
- QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 79edbd876fc9992f088b9adb159e005c735a72cb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127330"
---
# <a name="qualifierset_beginenumeration-function"></a><span data-ttu-id="bb922-103">Функция QualifierSet_BeginEnumeration</span><span class="sxs-lookup"><span data-stu-id="bb922-103">QualifierSet_BeginEnumeration function</span></span>

<span data-ttu-id="bb922-104">Сбрасывает перечислитель квалификаторов объекта в начало перечисления.</span><span class="sxs-lookup"><span data-stu-id="bb922-104">Resets an enumerator of the qualifiers of an object to the beginning of the enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="bb922-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb922-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags
);
```

## <a name="parameters"></a><span data-ttu-id="bb922-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="bb922-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="bb922-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="bb922-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="bb922-108">окне Указатель на экземпляр [ивбемкуалифиерсет](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="bb922-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="bb922-109">окне Побитовое сочетание флагов или значений, описанных в разделе « [Примечания](#remarks) », в котором указываются квалификаторы, включаемые в перечисление.</span><span class="sxs-lookup"><span data-stu-id="bb922-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that specifies the qualifiers to include in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="bb922-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bb922-110">Return value</span></span>

<span data-ttu-id="bb922-111">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="bb922-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="bb922-112">Константа</span><span class="sxs-lookup"><span data-stu-id="bb922-112">Constant</span></span>  |<span data-ttu-id="bb922-113">значения</span><span class="sxs-lookup"><span data-stu-id="bb922-113">Value</span></span>  |<span data-ttu-id="bb922-114">Описание</span><span class="sxs-lookup"><span data-stu-id="bb922-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="bb922-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="bb922-115">0x80041008</span></span> | <span data-ttu-id="bb922-116">Недопустимый параметр `lFlags`.</span><span class="sxs-lookup"><span data-stu-id="bb922-116">The `lFlags` parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="bb922-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="bb922-117">0x8004101d</span></span> | <span data-ttu-id="bb922-118">Второй вызов `QualifierSet_BeginEnumeration` был выполнен без промежуточного вызова [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="bb922-118">A second call to `QualifierSet_BeginEnumeration` was made without an intervening call to [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="bb922-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="bb922-119">0x80041006</span></span> | <span data-ttu-id="bb922-120">Недостаточно памяти для начала нового перечисления.</span><span class="sxs-lookup"><span data-stu-id="bb922-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="bb922-121">0</span><span class="sxs-lookup"><span data-stu-id="bb922-121">0</span></span> | <span data-ttu-id="bb922-122">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="bb922-122">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="bb922-123">Заметки</span><span class="sxs-lookup"><span data-stu-id="bb922-123">Remarks</span></span>

<span data-ttu-id="bb922-124">Эта функция заключает в оболочку вызов метода [ивбемкуалифиерсет:: BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) .</span><span class="sxs-lookup"><span data-stu-id="bb922-124">This function wraps a call to the [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) method.</span></span>

<span data-ttu-id="bb922-125">Чтобы перечислить все квалификаторы объекта, этот метод должен вызываться перед первым вызовом [QualifierSet_Next](qualifierset-next.md).</span><span class="sxs-lookup"><span data-stu-id="bb922-125">To enumerate all of the qualifiers on an object, this method must be called before the first call to [QualifierSet_Next](qualifierset-next.md).</span></span> <span data-ttu-id="bb922-126">Порядок перечисления квалификаторов гарантированно является инвариантным для данного перечисления.</span><span class="sxs-lookup"><span data-stu-id="bb922-126">The order in which qualifiers are enumerated is guaranteed to be invariant for a given enumeration.</span></span>

<span data-ttu-id="bb922-127">Флаги, которые могут быть переданы в качестве аргумента `lEnumFlags`, определяются в файле заголовка *вбемкли. h* , или их можно определить как константы в коде.</span><span class="sxs-lookup"><span data-stu-id="bb922-127">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

|<span data-ttu-id="bb922-128">Константа</span><span class="sxs-lookup"><span data-stu-id="bb922-128">Constant</span></span>  |<span data-ttu-id="bb922-129">значения</span><span class="sxs-lookup"><span data-stu-id="bb922-129">Value</span></span>  |<span data-ttu-id="bb922-130">Описание</span><span class="sxs-lookup"><span data-stu-id="bb922-130">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="bb922-131">0</span><span class="sxs-lookup"><span data-stu-id="bb922-131">0</span></span> | <span data-ttu-id="bb922-132">Возвращает имена всех квалификаторов.</span><span class="sxs-lookup"><span data-stu-id="bb922-132">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="bb922-133">0x10</span><span class="sxs-lookup"><span data-stu-id="bb922-133">0x10</span></span> | <span data-ttu-id="bb922-134">Возврат только имен квалификаторов, относящихся к текущему свойству или объекту.</span><span class="sxs-lookup"><span data-stu-id="bb922-134">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="bb922-135">Для свойства: возвращают только квалификаторы, относящиеся к свойству (включая переопределения), а не эти квалификаторы, распространенные из определения класса.</span><span class="sxs-lookup"><span data-stu-id="bb922-135">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="bb922-136">Для экземпляра: возвращать только имена квалификаторов, относящиеся только к экземпляру.</span><span class="sxs-lookup"><span data-stu-id="bb922-136">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="bb922-137">Для класса: возвращать только квалификаторы, относящиеся к производному классу.</span><span class="sxs-lookup"><span data-stu-id="bb922-137">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="bb922-138">0x20</span><span class="sxs-lookup"><span data-stu-id="bb922-138">0x20</span></span> | <span data-ttu-id="bb922-139">Возвращать только имена квалификаторов, распространяемых из другого объекта.</span><span class="sxs-lookup"><span data-stu-id="bb922-139">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="bb922-140">Для свойства: возвращают только те квалификаторы, которые распространяются на это свойство из определения класса, а не из самого свойства.</span><span class="sxs-lookup"><span data-stu-id="bb922-140">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="bb922-141">Для экземпляра: возврат только тех квалификаторов, которые распространяются из определения класса.</span><span class="sxs-lookup"><span data-stu-id="bb922-141">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="bb922-142">Для класса: возвращают только имена квалификаторов, унаследованные от родительских классов.</span><span class="sxs-lookup"><span data-stu-id="bb922-142">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="bb922-143">Требования</span><span class="sxs-lookup"><span data-stu-id="bb922-143">Requirements</span></span>

<span data-ttu-id="bb922-144">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb922-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="bb922-145">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="bb922-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="bb922-146">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bb922-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="bb922-147">См. также</span><span class="sxs-lookup"><span data-stu-id="bb922-147">See also</span></span>

- [<span data-ttu-id="bb922-148">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="bb922-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
