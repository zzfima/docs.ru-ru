---
title: Функция QualifierSet_Put (Справочник по неуправляемым API)
description: Функция QualifierSet_Put записывает именованный квалификатор и его значение.
ms.date: 11/06/2017
api_name:
- QualifierSet_Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Put
helpviewer_keywords:
- QualifierSet_Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 40688a0e4273233245d00fcd927f95945a43f712
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798274"
---
# <a name="qualifierset_put-function"></a><span data-ttu-id="d3608-103">Функция QualifierSet_Put</span><span class="sxs-lookup"><span data-stu-id="d3608-103">QualifierSet_Put function</span></span>

<span data-ttu-id="d3608-104">Записывает именованный квалификатор и значение.</span><span class="sxs-lookup"><span data-stu-id="d3608-104">Writes the named qualifier and value.</span></span> <span data-ttu-id="d3608-105">Новый квалификатор перезаписывает предыдущее значение с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="d3608-105">The new qualifier overwrites the previous value of the same name.</span></span> <span data-ttu-id="d3608-106">Если квалификатор не существует, он создается.</span><span class="sxs-lookup"><span data-stu-id="d3608-106">If the qualifier does not exist, it is created.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="d3608-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3608-107">Syntax</span></span>

```cpp
HRESULT QualifierSet_Put (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="d3608-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="d3608-108">Parameters</span></span>

`vFunc`\
<span data-ttu-id="d3608-109">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="d3608-109">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="d3608-110">окне Указатель на экземпляр [ивбемкуалифиерсет](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="d3608-110">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`\
<span data-ttu-id="d3608-111">окне Имя записываемого описателя.</span><span class="sxs-lookup"><span data-stu-id="d3608-111">[in] The name of the qualifier to write.</span></span>

`pVal`\
<span data-ttu-id="d3608-112">окне Указатель на допустимое `VARIANT` значение, содержащее квалификатор для записи.</span><span class="sxs-lookup"><span data-stu-id="d3608-112">[in] A pointer to a valid `VARIANT` that contains the qualifier to write.</span></span> <span data-ttu-id="d3608-113">Этот параметр не может `null`быть.</span><span class="sxs-lookup"><span data-stu-id="d3608-113">This parameter cannot be `null`.</span></span>

`lFlavor`\
<span data-ttu-id="d3608-114">окне Одна из следующих констант, определяющая нужные флаги квалификаторов для этого квалификатора.</span><span class="sxs-lookup"><span data-stu-id="d3608-114">[in] One of the following constants that defines the desired qualifier flavors for this qualifier.</span></span> <span data-ttu-id="d3608-115">Значение по умолчанию `WBEM_FLAVOR_OVERRIDABLE` — (0).</span><span class="sxs-lookup"><span data-stu-id="d3608-115">The default value is `WBEM_FLAVOR_OVERRIDABLE` (0).</span></span>

|<span data-ttu-id="d3608-116">Константа</span><span class="sxs-lookup"><span data-stu-id="d3608-116">Constant</span></span>  |<span data-ttu-id="d3608-117">Значение</span><span class="sxs-lookup"><span data-stu-id="d3608-117">Value</span></span>  |<span data-ttu-id="d3608-118">Описание</span><span class="sxs-lookup"><span data-stu-id="d3608-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | <span data-ttu-id="d3608-119">0</span><span class="sxs-lookup"><span data-stu-id="d3608-119">0</span></span> | <span data-ttu-id="d3608-120">Квалификатор можно переопределить в производном классе или экземпляре.</span><span class="sxs-lookup"><span data-stu-id="d3608-120">The qualifier can be overridden in a derived class or instance.</span></span> <span data-ttu-id="d3608-121">**Это значение по умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="d3608-121">**This is the default value.**</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | <span data-ttu-id="d3608-122">1</span><span class="sxs-lookup"><span data-stu-id="d3608-122">1</span></span> | <span data-ttu-id="d3608-123">Квалификатор распространяется в экземпляры.</span><span class="sxs-lookup"><span data-stu-id="d3608-123">The qualifier is propagated to instances.</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_DERIVED_CLASS` | <span data-ttu-id="d3608-124">2</span><span class="sxs-lookup"><span data-stu-id="d3608-124">2</span></span> | <span data-ttu-id="d3608-125">Квалификатор распространяется на производные классы.</span><span class="sxs-lookup"><span data-stu-id="d3608-125">The qualifier is propagated to derived classes.</span></span> |
| `WBEM_FLAVOR_NOT_OVERRIDABLE` | <span data-ttu-id="d3608-126">0x10</span><span class="sxs-lookup"><span data-stu-id="d3608-126">0x10</span></span> | <span data-ttu-id="d3608-127">Квалификатор невозможно переопределить в производном классе или экземпляре.</span><span class="sxs-lookup"><span data-stu-id="d3608-127">The qualifier cannot be overridden in a derived class or instance.</span></span> |
| `WBEM_FLAVOR_AMENDED` | <span data-ttu-id="d3608-128">0x80</span><span class="sxs-lookup"><span data-stu-id="d3608-128">0x80</span></span> | <span data-ttu-id="d3608-129">Квалификатор локализован.</span><span class="sxs-lookup"><span data-stu-id="d3608-129">The qualifier is localized.</span></span> |

## <a name="return-value"></a><span data-ttu-id="d3608-130">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d3608-130">Return value</span></span>

<span data-ttu-id="d3608-131">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="d3608-131">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d3608-132">Константа</span><span class="sxs-lookup"><span data-stu-id="d3608-132">Constant</span></span>  |<span data-ttu-id="d3608-133">Значение</span><span class="sxs-lookup"><span data-stu-id="d3608-133">Value</span></span>  |<span data-ttu-id="d3608-134">Описание</span><span class="sxs-lookup"><span data-stu-id="d3608-134">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | <span data-ttu-id="d3608-135">0x8004101f</span><span class="sxs-lookup"><span data-stu-id="d3608-135">0x8004101f</span></span> | <span data-ttu-id="d3608-136">Недопустимая попытка указать квалификатор **ключа** для свойства, которое не может быть ключом.</span><span class="sxs-lookup"><span data-stu-id="d3608-136">There was an illegal attempt to specify the **Key** qualifier on a property that cannot be a key.</span></span> <span data-ttu-id="d3608-137">Ключи задаются в определении класса для объекта и не могут быть изменены отдельно для каждого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d3608-137">The keys are specified in the class definition for an object and cannot be altered on a per-instance basis.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="d3608-138">0x80041008</span><span class="sxs-lookup"><span data-stu-id="d3608-138">0x80041008</span></span> | <span data-ttu-id="d3608-139">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="d3608-139">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | <span data-ttu-id="d3608-140">0x80041029</span><span class="sxs-lookup"><span data-stu-id="d3608-140">0x80041029</span></span> | <span data-ttu-id="d3608-141">`pVal` Параметр не является допустимым типом квалификатора.</span><span class="sxs-lookup"><span data-stu-id="d3608-141">The `pVal` parameter is not of a legal qualifier type.</span></span> |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | <span data-ttu-id="d3608-142">0x8004101a</span><span class="sxs-lookup"><span data-stu-id="d3608-142">0x8004101a</span></span> | <span data-ttu-id="d3608-143">Невозможно вызвать `QualifierSet_Put` метод квалификатора, так как объект-владелец не допускает переопределения.</span><span class="sxs-lookup"><span data-stu-id="d3608-143">It is not possible to call the `QualifierSet_Put` method on the qualifier because the owning object does not permit overrides.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="d3608-144">0</span><span class="sxs-lookup"><span data-stu-id="d3608-144">0</span></span> | <span data-ttu-id="d3608-145">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="d3608-145">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="d3608-146">Примечания</span><span class="sxs-lookup"><span data-stu-id="d3608-146">Remarks</span></span>

<span data-ttu-id="d3608-147">Эта функция заключает вызов метода [ивбемкуалифиерсет::P UT](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) .</span><span class="sxs-lookup"><span data-stu-id="d3608-147">This function wraps a call to the [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="d3608-148">Требования</span><span class="sxs-lookup"><span data-stu-id="d3608-148">Requirements</span></span>

<span data-ttu-id="d3608-149">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3608-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="d3608-150">**Заголовок.** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="d3608-150">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="d3608-151">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d3608-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d3608-152">См. также</span><span class="sxs-lookup"><span data-stu-id="d3608-152">See also</span></span>

- [<span data-ttu-id="d3608-153">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="d3608-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
