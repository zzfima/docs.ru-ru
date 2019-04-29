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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597248"
---
# <a name="qualifiersetbeginenumeration-function"></a><span data-ttu-id="4eeff-103">Функция QualifierSet_BeginEnumeration</span><span class="sxs-lookup"><span data-stu-id="4eeff-103">QualifierSet_BeginEnumeration function</span></span>

<span data-ttu-id="4eeff-104">Сбрасывает перечислитель квалификаторов объекта в начало перечисления.</span><span class="sxs-lookup"><span data-stu-id="4eeff-104">Resets an enumerator of the qualifiers of an object to the beginning of the enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="4eeff-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4eeff-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags
);
```

## <a name="parameters"></a><span data-ttu-id="4eeff-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4eeff-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="4eeff-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="4eeff-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="4eeff-108">[in] Указатель на [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="4eeff-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="4eeff-109">[in] Побитовое сочетание флагов или значения, описанные в ["Примечания"](#remarks) раздел, в котором указывает квалификаторы для включения в перечислении.</span><span class="sxs-lookup"><span data-stu-id="4eeff-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that specifies the qualifiers to include in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="4eeff-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4eeff-110">Return value</span></span>

<span data-ttu-id="4eeff-111">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="4eeff-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4eeff-112">Константа</span><span class="sxs-lookup"><span data-stu-id="4eeff-112">Constant</span></span>  |<span data-ttu-id="4eeff-113">Значение</span><span class="sxs-lookup"><span data-stu-id="4eeff-113">Value</span></span>  |<span data-ttu-id="4eeff-114">Описание</span><span class="sxs-lookup"><span data-stu-id="4eeff-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="4eeff-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="4eeff-115">0x80041008</span></span> | <span data-ttu-id="4eeff-116">Недопустимый параметр `lFlags`.</span><span class="sxs-lookup"><span data-stu-id="4eeff-116">The `lFlags` parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="4eeff-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="4eeff-117">0x8004101d</span></span> | <span data-ttu-id="4eeff-118">Второй вызов `QualifierSet_BeginEnumeration` была сделана без промежуточных вызовов к [ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="4eeff-118">A second call to `QualifierSet_BeginEnumeration` was made without an intervening call to [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="4eeff-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="4eeff-119">0x80041006</span></span> | <span data-ttu-id="4eeff-120">Не хватает памяти, позволяющих начать новое перечисление.</span><span class="sxs-lookup"><span data-stu-id="4eeff-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="4eeff-121">0</span><span class="sxs-lookup"><span data-stu-id="4eeff-121">0</span></span> | <span data-ttu-id="4eeff-122">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="4eeff-122">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="4eeff-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="4eeff-123">Remarks</span></span>

<span data-ttu-id="4eeff-124">Эта функция создает оболочку для вызова [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) метод.</span><span class="sxs-lookup"><span data-stu-id="4eeff-124">This function wraps a call to the [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) method.</span></span>

<span data-ttu-id="4eeff-125">Чтобы перечислить все квалификаторы для объекта, этот метод должен вызываться перед первым вызовом [QualifierSet_Next](qualifierset-next.md).</span><span class="sxs-lookup"><span data-stu-id="4eeff-125">To enumerate all of the qualifiers on an object, this method must be called before the first call to [QualifierSet_Next](qualifierset-next.md).</span></span> <span data-ttu-id="4eeff-126">Порядок, в котором перечислены квалификаторы гарантированно инвариантным для данного перечисления.</span><span class="sxs-lookup"><span data-stu-id="4eeff-126">The order in which qualifiers are enumerated is guaranteed to be invariant for a given enumeration.</span></span>

<span data-ttu-id="4eeff-127">Флаги, которые могут передаваться как `lEnumFlags` аргумент определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде.</span><span class="sxs-lookup"><span data-stu-id="4eeff-127">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

|<span data-ttu-id="4eeff-128">Константа</span><span class="sxs-lookup"><span data-stu-id="4eeff-128">Constant</span></span>  |<span data-ttu-id="4eeff-129">Значение</span><span class="sxs-lookup"><span data-stu-id="4eeff-129">Value</span></span>  |<span data-ttu-id="4eeff-130">Описание</span><span class="sxs-lookup"><span data-stu-id="4eeff-130">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="4eeff-131">0</span><span class="sxs-lookup"><span data-stu-id="4eeff-131">0</span></span> | <span data-ttu-id="4eeff-132">Возвращает имена всех квалификаторов.</span><span class="sxs-lookup"><span data-stu-id="4eeff-132">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="4eeff-133">0x10</span><span class="sxs-lookup"><span data-stu-id="4eeff-133">0x10</span></span> | <span data-ttu-id="4eeff-134">Возвращать только имена квалификаторы объекту или текущего свойства.</span><span class="sxs-lookup"><span data-stu-id="4eeff-134">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="4eeff-135">Для свойства: Возвращает только квалификаторов, определенных в свойстве (включая переопределения), а не квалификаторы, распространяются из определения класса.</span><span class="sxs-lookup"><span data-stu-id="4eeff-135">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="4eeff-136">Для экземпляра: Возвращает только квалификатор с определенным экземпляром имена.</span><span class="sxs-lookup"><span data-stu-id="4eeff-136">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="4eeff-137">Для класса: Возвращать только квалификаторы для производного класса.</span><span class="sxs-lookup"><span data-stu-id="4eeff-137">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="4eeff-138">0x20</span><span class="sxs-lookup"><span data-stu-id="4eeff-138">0x20</span></span> | <span data-ttu-id="4eeff-139">Возврат только имена квалификаторы распространяются из другого объекта.</span><span class="sxs-lookup"><span data-stu-id="4eeff-139">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="4eeff-140">Для свойства: Возврат распространяются только квалификаторы к этому свойству из определения класса, а не из самого свойства.</span><span class="sxs-lookup"><span data-stu-id="4eeff-140">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="4eeff-141">Для экземпляра: Возврат только эти квалификаторы распространяются из определения класса.</span><span class="sxs-lookup"><span data-stu-id="4eeff-141">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="4eeff-142">Для класса: Возвращаемое значение, только те имена квалификатор, наследуемые от родительских классов.</span><span class="sxs-lookup"><span data-stu-id="4eeff-142">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="4eeff-143">Требования</span><span class="sxs-lookup"><span data-stu-id="4eeff-143">Requirements</span></span>

<span data-ttu-id="4eeff-144">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4eeff-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="4eeff-145">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4eeff-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="4eeff-146">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4eeff-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4eeff-147">См. также</span><span class="sxs-lookup"><span data-stu-id="4eeff-147">See also</span></span>

- [<span data-ttu-id="4eeff-148">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="4eeff-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)