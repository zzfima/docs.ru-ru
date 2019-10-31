---
title: Функция CompareTo (Справочник по неуправляемым API)
description: Функция CompareTo сравнивает объект с другим объектом WMI.
ms.date: 11/06/2017
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 0d210795016cd2e0179b902a224ca0c62f4ac01f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128701"
---
# <a name="compareto-function"></a><span data-ttu-id="8631c-103">Функция CompareTo</span><span class="sxs-lookup"><span data-stu-id="8631c-103">CompareTo function</span></span>

<span data-ttu-id="8631c-104">Сравнивает объект с другим объектом управления Windows.</span><span class="sxs-lookup"><span data-stu-id="8631c-104">Compares an object to another Windows management object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="8631c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8631c-105">Syntax</span></span>

```cpp
HRESULT CompareTo (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo
);
```

## <a name="parameters"></a><span data-ttu-id="8631c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8631c-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="8631c-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="8631c-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="8631c-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="8631c-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`flags`\
<span data-ttu-id="8631c-109">окне Побитовое сочетание флагов, задающих характеристики объекта, которые следует учитывать при сравнении.</span><span class="sxs-lookup"><span data-stu-id="8631c-109">[in] A bitwise combination of the flags that specify the object characteristics to consider for the comparison.</span></span> <span data-ttu-id="8631c-110">Дополнительные сведения см. в разделе ["Примечания"](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="8631c-110">See the [Remarks](#remarks) section for more information.</span></span>

`pCompareTo`\
<span data-ttu-id="8631c-111">окне Объект для сравнения.</span><span class="sxs-lookup"><span data-stu-id="8631c-111">[in] The object for comparison.</span></span> <span data-ttu-id="8631c-112">`pCompareTo` должен быть допустимым экземпляром [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) ; его невозможно `null`.</span><span class="sxs-lookup"><span data-stu-id="8631c-112">`pCompareTo` must be a valid [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance; it cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="8631c-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8631c-113">Return value</span></span>

<span data-ttu-id="8631c-114">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="8631c-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8631c-115">Константа</span><span class="sxs-lookup"><span data-stu-id="8631c-115">Constant</span></span>  |<span data-ttu-id="8631c-116">значения</span><span class="sxs-lookup"><span data-stu-id="8631c-116">Value</span></span>  |<span data-ttu-id="8631c-117">Описание</span><span class="sxs-lookup"><span data-stu-id="8631c-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="8631c-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="8631c-118">0x80041001</span></span> | <span data-ttu-id="8631c-119">Произошла неопределенная ошибка.</span><span class="sxs-lookup"><span data-stu-id="8631c-119">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8631c-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="8631c-120">0x80041008</span></span> | <span data-ttu-id="8631c-121">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="8631c-121">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="8631c-122">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="8631c-122">0x8004101d</span></span> | <span data-ttu-id="8631c-123">Второй вызов `BeginEnumeration` был выполнен без промежуточного вызова [`EndEnumeration`](endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="8631c-123">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="8631c-124">0</span><span class="sxs-lookup"><span data-stu-id="8631c-124">0</span></span> | <span data-ttu-id="8631c-125">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="8631c-125">The function call was successful.</span></span>  |
| `WBEM_S_DIFFERENT` | <span data-ttu-id="8631c-126">0x40003</span><span class="sxs-lookup"><span data-stu-id="8631c-126">0x40003</span></span> | <span data-ttu-id="8631c-127">Объекты различаются.</span><span class="sxs-lookup"><span data-stu-id="8631c-127">The objects are different.</span></span> |
| `WBEM_S_SAME` | <span data-ttu-id="8631c-128">0</span><span class="sxs-lookup"><span data-stu-id="8631c-128">0</span></span> | <span data-ttu-id="8631c-129">Объекты одинаковы на основе флагов сравнения.</span><span class="sxs-lookup"><span data-stu-id="8631c-129">The objects are the same based on the comparison flags.</span></span> |

## <a name="remarks"></a><span data-ttu-id="8631c-130">Заметки</span><span class="sxs-lookup"><span data-stu-id="8631c-130">Remarks</span></span>

<span data-ttu-id="8631c-131">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) .</span><span class="sxs-lookup"><span data-stu-id="8631c-131">This function wraps a call to the [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) method.</span></span>

<span data-ttu-id="8631c-132">Флаги, которые могут быть переданы в качестве аргумента `lEnumFlags`, определяются в файле заголовка *вбемкли. h* , или их можно определить как константы в коде.</span><span class="sxs-lookup"><span data-stu-id="8631c-132">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> <span data-ttu-id="8631c-133">Можно указать отдельные характеристики, участвующие в сравнении, указав побитовое сочетание следующих флагов:</span><span class="sxs-lookup"><span data-stu-id="8631c-133">You can specify the individual characteristics involved in the comparison by specifying a bitwise combination of the following flags:</span></span>

|<span data-ttu-id="8631c-134">Константа</span><span class="sxs-lookup"><span data-stu-id="8631c-134">Constant</span></span>  |<span data-ttu-id="8631c-135">значения</span><span class="sxs-lookup"><span data-stu-id="8631c-135">Value</span></span>  |<span data-ttu-id="8631c-136">Описание</span><span class="sxs-lookup"><span data-stu-id="8631c-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | <span data-ttu-id="8631c-137">2</span><span class="sxs-lookup"><span data-stu-id="8631c-137">2</span></span> | <span data-ttu-id="8631c-138">Игнорируйте источник (сервер и пространство имен, из которого они поступили).</span><span class="sxs-lookup"><span data-stu-id="8631c-138">Ignore the source (the server and the namespace they came from).</span></span> |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | <span data-ttu-id="8631c-139">1</span><span class="sxs-lookup"><span data-stu-id="8631c-139">1</span></span> | <span data-ttu-id="8631c-140">Игнорировать все квалификаторы (включая **ключ** и **динамический**)</span><span class="sxs-lookup"><span data-stu-id="8631c-140">Ignore all qualifiers (including **Key** and **Dynamic**)</span></span> |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | <span data-ttu-id="8631c-141">4</span><span class="sxs-lookup"><span data-stu-id="8631c-141">4</span></span> | <span data-ttu-id="8631c-142">Игнорировать значения свойств по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8631c-142">Ignore default values of properties.</span></span> <span data-ttu-id="8631c-143">Этот флаг применяется только к сравнению классов.</span><span class="sxs-lookup"><span data-stu-id="8631c-143">This flag only applies to comparison of classes.</span></span> |
| `WBEM_FLAG_IGNORE_FLAVOR` | <span data-ttu-id="8631c-144">0x20</span><span class="sxs-lookup"><span data-stu-id="8631c-144">0x20</span></span> | <span data-ttu-id="8631c-145">Не учитывать разновидности квалификаторов.</span><span class="sxs-lookup"><span data-stu-id="8631c-145">Ignore qualifier flavors.</span></span> <span data-ttu-id="8631c-146">Этот флаг по-прежнему учитывает квалификаторы, но не учитывает различия разновидностей, например правила распространения и ограничения переопределения.</span><span class="sxs-lookup"><span data-stu-id="8631c-146">This flag still takes qualifiers into account, but ignores flavor distinctions such as propagation rules and override restrictions.</span></span> |
| `WBEM_FLAG_IGNORE_CASE` | <span data-ttu-id="8631c-147">0x10</span><span class="sxs-lookup"><span data-stu-id="8631c-147">0x10</span></span> | <span data-ttu-id="8631c-148">Не учитывать регистр при сравнении строковых значений.</span><span class="sxs-lookup"><span data-stu-id="8631c-148">Ignore case in comparing string values.</span></span> <span data-ttu-id="8631c-149">Это применимо как к строкам, так и к значениям квалификаторов.</span><span class="sxs-lookup"><span data-stu-id="8631c-149">This applies both to strings and qualifier values.</span></span> <span data-ttu-id="8631c-150">При сравнении имен свойств и квалификаторов всегда учитывается регистр, независимо от того, установлен ли этот флаг.</span><span class="sxs-lookup"><span data-stu-id="8631c-150">The comparison of property and qualifier names is always case-sensitive regardless of whether this flag is set.</span></span> |
| `WBEM_FLAG_IGNORE_CLASS` | <span data-ttu-id="8631c-151">0x8</span><span class="sxs-lookup"><span data-stu-id="8631c-151">0x8</span></span> | <span data-ttu-id="8631c-152">Предположим, что сравниваемые объекты являются экземплярами одного и того же класса.</span><span class="sxs-lookup"><span data-stu-id="8631c-152">Assume that the objects being compared are instances of the same class.</span></span> <span data-ttu-id="8631c-153">Следовательно, этот флаг сравнивает только сведения, относящиеся к экземпляру.</span><span class="sxs-lookup"><span data-stu-id="8631c-153">Consequently, this flag compares instance-related information only.</span></span> <span data-ttu-id="8631c-154">Используйте эти флаги для оптимизации производительности.</span><span class="sxs-lookup"><span data-stu-id="8631c-154">Use this flags to optimize performance.</span></span> <span data-ttu-id="8631c-155">Если объекты не относятся к одному и тому же классу, результаты не определены.</span><span class="sxs-lookup"><span data-stu-id="8631c-155">If the objects are not of the same class, the results are undefined.</span></span> |

<span data-ttu-id="8631c-156">Или можно указать один составной флаг следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8631c-156">Or you can specify a single composite flag as follows:</span></span>

|<span data-ttu-id="8631c-157">Константа</span><span class="sxs-lookup"><span data-stu-id="8631c-157">Constant</span></span>  |<span data-ttu-id="8631c-158">значения</span><span class="sxs-lookup"><span data-stu-id="8631c-158">Value</span></span>  |<span data-ttu-id="8631c-159">Описание</span><span class="sxs-lookup"><span data-stu-id="8631c-159">Description</span></span>  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | <span data-ttu-id="8631c-160">0</span><span class="sxs-lookup"><span data-stu-id="8631c-160">0</span></span> | <span data-ttu-id="8631c-161">Рассмотрите все функции в сравнении.</span><span class="sxs-lookup"><span data-stu-id="8631c-161">Consider all features in the comparison.</span></span> |

## <a name="requirements"></a><span data-ttu-id="8631c-162">Требования</span><span class="sxs-lookup"><span data-stu-id="8631c-162">Requirements</span></span>

<span data-ttu-id="8631c-163">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8631c-163">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="8631c-164">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="8631c-164">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="8631c-165">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8631c-165">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8631c-166">См. также</span><span class="sxs-lookup"><span data-stu-id="8631c-166">See also</span></span>

- [<span data-ttu-id="8631c-167">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="8631c-167">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
