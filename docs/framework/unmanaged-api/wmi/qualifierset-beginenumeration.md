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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f663434d3e3d44dc0c406e71592651493bd8f8dc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375419"
---
# <a name="qualifiersetbeginenumeration-function"></a><span data-ttu-id="0aafc-103">Функция QualifierSet_BeginEnumeration</span><span class="sxs-lookup"><span data-stu-id="0aafc-103">QualifierSet_BeginEnumeration function</span></span>

<span data-ttu-id="0aafc-104">Сбрасывает перечислитель квалификаторов объекта в начало перечисления.</span><span class="sxs-lookup"><span data-stu-id="0aafc-104">Resets an enumerator of the qualifiers of an object to the beginning of the enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="0aafc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0aafc-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags
);
```

## <a name="parameters"></a><span data-ttu-id="0aafc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0aafc-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="0aafc-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="0aafc-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="0aafc-108">[in] Указатель на [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0aafc-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="0aafc-109">[in] Побитовое сочетание флагов или значения, описанные в ["Примечания"](#remarks) раздел, в котором указывает квалификаторы для включения в перечислении.</span><span class="sxs-lookup"><span data-stu-id="0aafc-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that specifies the qualifiers to include in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="0aafc-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0aafc-110">Return value</span></span>

<span data-ttu-id="0aafc-111">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="0aafc-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0aafc-112">Константа</span><span class="sxs-lookup"><span data-stu-id="0aafc-112">Constant</span></span>  |<span data-ttu-id="0aafc-113">Значение</span><span class="sxs-lookup"><span data-stu-id="0aafc-113">Value</span></span>  |<span data-ttu-id="0aafc-114">Описание</span><span class="sxs-lookup"><span data-stu-id="0aafc-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0aafc-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0aafc-115">0x80041008</span></span> | <span data-ttu-id="0aafc-116">Недопустимый параметр `lFlags`.</span><span class="sxs-lookup"><span data-stu-id="0aafc-116">The `lFlags` parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="0aafc-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="0aafc-117">0x8004101d</span></span> | <span data-ttu-id="0aafc-118">Второй вызов `QualifierSet_BeginEnumeration` была сделана без промежуточных вызовов к [ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="0aafc-118">A second call to `QualifierSet_BeginEnumeration` was made without an intervening call to [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0aafc-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0aafc-119">0x80041006</span></span> | <span data-ttu-id="0aafc-120">Не хватает памяти, позволяющих начать новое перечисление.</span><span class="sxs-lookup"><span data-stu-id="0aafc-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="0aafc-121">0</span><span class="sxs-lookup"><span data-stu-id="0aafc-121">0</span></span> | <span data-ttu-id="0aafc-122">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="0aafc-122">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="0aafc-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="0aafc-123">Remarks</span></span>

<span data-ttu-id="0aafc-124">Эта функция создает оболочку для вызова [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) метод.</span><span class="sxs-lookup"><span data-stu-id="0aafc-124">This function wraps a call to the [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) method.</span></span>

<span data-ttu-id="0aafc-125">Чтобы перечислить все квалификаторы для объекта, этот метод должен вызываться перед первым вызовом [QualifierSet_Next](qualifierset-next.md).</span><span class="sxs-lookup"><span data-stu-id="0aafc-125">To enumerate all of the qualifiers on an object, this method must be called before the first call to [QualifierSet_Next](qualifierset-next.md).</span></span> <span data-ttu-id="0aafc-126">Порядок, в котором перечислены квалификаторы гарантированно инвариантным для данного перечисления.</span><span class="sxs-lookup"><span data-stu-id="0aafc-126">The order in which qualifiers are enumerated is guaranteed to be invariant for a given enumeration.</span></span>

<span data-ttu-id="0aafc-127">Флаги, которые могут передаваться как `lEnumFlags` аргумент определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде.</span><span class="sxs-lookup"><span data-stu-id="0aafc-127">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

|<span data-ttu-id="0aafc-128">Константа</span><span class="sxs-lookup"><span data-stu-id="0aafc-128">Constant</span></span>  |<span data-ttu-id="0aafc-129">Значение</span><span class="sxs-lookup"><span data-stu-id="0aafc-129">Value</span></span>  |<span data-ttu-id="0aafc-130">Описание</span><span class="sxs-lookup"><span data-stu-id="0aafc-130">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="0aafc-131">0</span><span class="sxs-lookup"><span data-stu-id="0aafc-131">0</span></span> | <span data-ttu-id="0aafc-132">Возвращает имена всех квалификаторов.</span><span class="sxs-lookup"><span data-stu-id="0aafc-132">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="0aafc-133">0x10</span><span class="sxs-lookup"><span data-stu-id="0aafc-133">0x10</span></span> | <span data-ttu-id="0aafc-134">Возвращать только имена квалификаторы объекту или текущего свойства.</span><span class="sxs-lookup"><span data-stu-id="0aafc-134">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="0aafc-135">Для свойства: Возвращает только квалификаторов, определенных в свойстве (включая переопределения), а не квалификаторы, распространяются из определения класса.</span><span class="sxs-lookup"><span data-stu-id="0aafc-135">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="0aafc-136">Для экземпляра: Возвращает только квалификатор с определенным экземпляром имена.</span><span class="sxs-lookup"><span data-stu-id="0aafc-136">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="0aafc-137">Для класса: Возвращать только квалификаторы для производного класса.</span><span class="sxs-lookup"><span data-stu-id="0aafc-137">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="0aafc-138">0x20</span><span class="sxs-lookup"><span data-stu-id="0aafc-138">0x20</span></span> | <span data-ttu-id="0aafc-139">Возврат только имена квалификаторы распространяются из другого объекта.</span><span class="sxs-lookup"><span data-stu-id="0aafc-139">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="0aafc-140">Для свойства: Возврат распространяются только квалификаторы к этому свойству из определения класса, а не из самого свойства.</span><span class="sxs-lookup"><span data-stu-id="0aafc-140">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="0aafc-141">Для экземпляра: Возврат только эти квалификаторы распространяются из определения класса.</span><span class="sxs-lookup"><span data-stu-id="0aafc-141">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="0aafc-142">Для класса: Возвращаемое значение, только те имена квалификатор, наследуемые от родительских классов.</span><span class="sxs-lookup"><span data-stu-id="0aafc-142">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="0aafc-143">Требования</span><span class="sxs-lookup"><span data-stu-id="0aafc-143">Requirements</span></span>

<span data-ttu-id="0aafc-144">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0aafc-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="0aafc-145">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="0aafc-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="0aafc-146">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0aafc-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0aafc-147">См. также</span><span class="sxs-lookup"><span data-stu-id="0aafc-147">See also</span></span>

- [<span data-ttu-id="0aafc-148">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="0aafc-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)