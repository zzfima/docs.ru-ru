---
title: Получить функцию (Неуправляемая ссылка API)
description: Функция Get получает указанное значение свойства.
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 67fcfb301eebfcf4ed4fdcaa5c9ddf85c47a6073
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174983"
---
# <a name="get-function"></a><span data-ttu-id="96f57-103">Функция Get</span><span class="sxs-lookup"><span data-stu-id="96f57-103">Get function</span></span>

<span data-ttu-id="96f57-104">Извлекает указанное значение свойства, если оно существует.</span><span class="sxs-lookup"><span data-stu-id="96f57-104">Retrieves the specified property value if it exists.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="96f57-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="96f57-105">Syntax</span></span>

```cpp
HRESULT Get (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="96f57-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="96f57-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="96f57-107">(в) Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="96f57-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="96f57-108">(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="96f57-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="96f57-109">[in] Имя свойства.</span><span class="sxs-lookup"><span data-stu-id="96f57-109">[in] The name of the property.</span></span>

`lFlags`\
<span data-ttu-id="96f57-110">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="96f57-110">[in] Reserved.</span></span> <span data-ttu-id="96f57-111">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="96f57-111">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="96f57-112">(ваут) Если функция возвращается успешно, содержит `wszName` значение свойства.</span><span class="sxs-lookup"><span data-stu-id="96f57-112">[out] If the function returns successfully, contains the value of the `wszName` property.</span></span> <span data-ttu-id="96f57-113">Аргументу `pval` присваивается правильный тип и значение для квалификатора.</span><span class="sxs-lookup"><span data-stu-id="96f57-113">The `pval` argument is assigned the correct type and value for the qualifier.</span></span>

`pvtType`\
<span data-ttu-id="96f57-114">(ваут) Если функция возвращается успешно, содержит [константу типа CIM,](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) указывают тип свойства.</span><span class="sxs-lookup"><span data-stu-id="96f57-114">[out] If the function returns successfully, contains a [CIM-type constant](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) that indicates the property type.</span></span> <span data-ttu-id="96f57-115">Его значение также `null`может быть .</span><span class="sxs-lookup"><span data-stu-id="96f57-115">Its value can also be `null`.</span></span>

`plFlavor`\
<span data-ttu-id="96f57-116">(ваут) Если функция возвращается успешно, получает информацию о происхождении свойства.</span><span class="sxs-lookup"><span data-stu-id="96f57-116">[out] If the function returns successfully, receives information about the origin of the property.</span></span> <span data-ttu-id="96f57-117">Его значение `null`может быть, или один из следующих констант WBEM_FLAVOR_TYPE, определенных в файле *заголовка WbemCli.h:*</span><span class="sxs-lookup"><span data-stu-id="96f57-117">Its value can be `null`, or one of the following WBEM_FLAVOR_TYPE constants defined in the *WbemCli.h* header file:</span></span>

|<span data-ttu-id="96f57-118">Постоянно</span><span class="sxs-lookup"><span data-stu-id="96f57-118">Constant</span></span>  |<span data-ttu-id="96f57-119">Значение</span><span class="sxs-lookup"><span data-stu-id="96f57-119">Value</span></span>  |<span data-ttu-id="96f57-120">Описание</span><span class="sxs-lookup"><span data-stu-id="96f57-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="96f57-121">0x40</span><span class="sxs-lookup"><span data-stu-id="96f57-121">0x40</span></span> | <span data-ttu-id="96f57-122">Свойство является стандартным свойством системы.</span><span class="sxs-lookup"><span data-stu-id="96f57-122">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="96f57-123">0x20</span><span class="sxs-lookup"><span data-stu-id="96f57-123">0x20</span></span> | <span data-ttu-id="96f57-124">Для класса: Свойство наследуется от родительского класса.</span><span class="sxs-lookup"><span data-stu-id="96f57-124">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="96f57-125">Например: свойство, унаследованное от родительского класса, не было изменено экземпляром.</span><span class="sxs-lookup"><span data-stu-id="96f57-125">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="96f57-126">0</span><span class="sxs-lookup"><span data-stu-id="96f57-126">0</span></span> | <span data-ttu-id="96f57-127">Для класса: Свойство относится к производному классу.</span><span class="sxs-lookup"><span data-stu-id="96f57-127">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="96f57-128">Например: свойство изменяется экземпляром; т.е. значение было поставлено, или квалификатор был добавлен или изменен.</span><span class="sxs-lookup"><span data-stu-id="96f57-128">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="return-value"></a><span data-ttu-id="96f57-129">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="96f57-129">Return value</span></span>

<span data-ttu-id="96f57-130">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="96f57-130">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="96f57-131">Постоянно</span><span class="sxs-lookup"><span data-stu-id="96f57-131">Constant</span></span>  |<span data-ttu-id="96f57-132">Значение</span><span class="sxs-lookup"><span data-stu-id="96f57-132">Value</span></span>  |<span data-ttu-id="96f57-133">Описание</span><span class="sxs-lookup"><span data-stu-id="96f57-133">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="96f57-134">0x80041001</span><span class="sxs-lookup"><span data-stu-id="96f57-134">0x80041001</span></span> | <span data-ttu-id="96f57-135">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="96f57-135">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="96f57-136">0x80041008</span><span class="sxs-lookup"><span data-stu-id="96f57-136">0x80041008</span></span> | <span data-ttu-id="96f57-137">Один или несколько параметров недействительны.</span><span class="sxs-lookup"><span data-stu-id="96f57-137">One or more parameters are not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="96f57-138">0x80041002</span><span class="sxs-lookup"><span data-stu-id="96f57-138">0x80041002</span></span> | <span data-ttu-id="96f57-139">Указанное свойство не найдено.</span><span class="sxs-lookup"><span data-stu-id="96f57-139">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="96f57-140">0x80041006</span><span class="sxs-lookup"><span data-stu-id="96f57-140">0x80041006</span></span> | <span data-ttu-id="96f57-141">Недостаточно памяти для выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="96f57-141">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="96f57-142">0</span><span class="sxs-lookup"><span data-stu-id="96f57-142">0</span></span> | <span data-ttu-id="96f57-143">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="96f57-143">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="96f57-144">Remarks</span><span class="sxs-lookup"><span data-stu-id="96f57-144">Remarks</span></span>

<span data-ttu-id="96f57-145">Эта функция завершает вызов [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) метод.</span><span class="sxs-lookup"><span data-stu-id="96f57-145">This function wraps a call to the [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) method.</span></span>

<span data-ttu-id="96f57-146">Функция `Get` также может возвращать свойства системы.</span><span class="sxs-lookup"><span data-stu-id="96f57-146">The `Get` function can also return system properties.</span></span>

<span data-ttu-id="96f57-147">Аргументу `pVal` присваивается правильный тип и значение для квалификатора и функции COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit)</span><span class="sxs-lookup"><span data-stu-id="96f57-147">The `pVal` argument is assigned the correct type and value for the qualifier and the COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) function</span></span>

## <a name="requirements"></a><span data-ttu-id="96f57-148">Требования</span><span class="sxs-lookup"><span data-stu-id="96f57-148">Requirements</span></span>

 <span data-ttu-id="96f57-149">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96f57-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="96f57-150">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="96f57-150">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="96f57-151">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="96f57-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="96f57-152">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="96f57-152">See also</span></span>

- [<span data-ttu-id="96f57-153">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="96f57-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
