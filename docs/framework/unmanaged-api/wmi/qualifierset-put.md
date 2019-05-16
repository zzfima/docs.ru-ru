---
title: Функция QualifierSet_Put (Справочник по неуправляемым API)
description: Эта функция QualifierSet_Put записывает именованного квалификатора и его значение.
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
ms.openlocfilehash: 42bef9ab728af251b043e29af4cee9e5cb3f405d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636545"
---
# <a name="qualifiersetput-function"></a><span data-ttu-id="7d46a-103">Функция QualifierSet_Put</span><span class="sxs-lookup"><span data-stu-id="7d46a-103">QualifierSet_Put function</span></span>

<span data-ttu-id="7d46a-104">Записывает именованный квалификатор и значение.</span><span class="sxs-lookup"><span data-stu-id="7d46a-104">Writes the named qualifier and value.</span></span> <span data-ttu-id="7d46a-105">Новый квалификатор перезаписывает предыдущее значение с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="7d46a-105">The new qualifier overwrites the previous value of the same name.</span></span> <span data-ttu-id="7d46a-106">Если квалификатор не существует, он создается.</span><span class="sxs-lookup"><span data-stu-id="7d46a-106">If the qualifier does not exist, it is created.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="7d46a-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d46a-107">Syntax</span></span>

```cpp
HRESULT QualifierSet_Put (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="7d46a-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="7d46a-108">Parameters</span></span>

`vFunc`\
<span data-ttu-id="7d46a-109">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="7d46a-109">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="7d46a-110">[in] Указатель на [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="7d46a-110">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`\
<span data-ttu-id="7d46a-111">[in] Имя квалификатора для записи.</span><span class="sxs-lookup"><span data-stu-id="7d46a-111">[in] The name of the qualifier to write.</span></span>

`pVal`\
<span data-ttu-id="7d46a-112">[in] Указатель на допустимую `VARIANT` , содержащий квалификатор для записи.</span><span class="sxs-lookup"><span data-stu-id="7d46a-112">[in] A pointer to a valid `VARIANT` that contains the qualifier to write.</span></span> <span data-ttu-id="7d46a-113">Этот параметр не может быть `null`.</span><span class="sxs-lookup"><span data-stu-id="7d46a-113">This parameter cannot be `null`.</span></span>

`lFlavor`\
<span data-ttu-id="7d46a-114">[in] Одно из следующих констант, который определяет требуемый квалификаторов для этот квалификатор.</span><span class="sxs-lookup"><span data-stu-id="7d46a-114">[in] One of the following constants that defines the desired qualifier flavors for this qualifier.</span></span> <span data-ttu-id="7d46a-115">Значение по умолчанию — `WBEM_FLAVOR_OVERRIDABLE` (0).</span><span class="sxs-lookup"><span data-stu-id="7d46a-115">The default value is `WBEM_FLAVOR_OVERRIDABLE` (0).</span></span>

|<span data-ttu-id="7d46a-116">Константа</span><span class="sxs-lookup"><span data-stu-id="7d46a-116">Constant</span></span>  |<span data-ttu-id="7d46a-117">Значение</span><span class="sxs-lookup"><span data-stu-id="7d46a-117">Value</span></span>  |<span data-ttu-id="7d46a-118">Описание</span><span class="sxs-lookup"><span data-stu-id="7d46a-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | <span data-ttu-id="7d46a-119">0</span><span class="sxs-lookup"><span data-stu-id="7d46a-119">0</span></span> | <span data-ttu-id="7d46a-120">Квалификатор может переопределяться в производном классе или экземпляре.</span><span class="sxs-lookup"><span data-stu-id="7d46a-120">The qualifier can be overridden in a derived class or instance.</span></span> <span data-ttu-id="7d46a-121">**Это значение по умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="7d46a-121">**This is the default value.**</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | <span data-ttu-id="7d46a-122">1</span><span class="sxs-lookup"><span data-stu-id="7d46a-122">1</span></span> | <span data-ttu-id="7d46a-123">Квалификатор распространяется в экземпляры.</span><span class="sxs-lookup"><span data-stu-id="7d46a-123">The qualifier is propagated to instances.</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_DERIVED_CLASS` | <span data-ttu-id="7d46a-124">2</span><span class="sxs-lookup"><span data-stu-id="7d46a-124">2</span></span> | <span data-ttu-id="7d46a-125">Квалификатор распространяется в производные классы.</span><span class="sxs-lookup"><span data-stu-id="7d46a-125">The qualifier is propagated to derived classes.</span></span> |
| `WBEM_FLAVOR_NOT_OVERRIDABLE` | <span data-ttu-id="7d46a-126">0x10</span><span class="sxs-lookup"><span data-stu-id="7d46a-126">0x10</span></span> | <span data-ttu-id="7d46a-127">Квалификатор невозможно переопределить в производном классе или экземпляре.</span><span class="sxs-lookup"><span data-stu-id="7d46a-127">The qualifier cannot be overridden in a derived class or instance.</span></span> |
| `WBEM_FLAVOR_AMENDED` | <span data-ttu-id="7d46a-128">0x80</span><span class="sxs-lookup"><span data-stu-id="7d46a-128">0x80</span></span> | <span data-ttu-id="7d46a-129">Квалификатор локализуется.</span><span class="sxs-lookup"><span data-stu-id="7d46a-129">The qualifier is localized.</span></span> |

## <a name="return-value"></a><span data-ttu-id="7d46a-130">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7d46a-130">Return value</span></span>

<span data-ttu-id="7d46a-131">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="7d46a-131">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7d46a-132">Константа</span><span class="sxs-lookup"><span data-stu-id="7d46a-132">Constant</span></span>  |<span data-ttu-id="7d46a-133">Значение</span><span class="sxs-lookup"><span data-stu-id="7d46a-133">Value</span></span>  |<span data-ttu-id="7d46a-134">Описание</span><span class="sxs-lookup"><span data-stu-id="7d46a-134">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | <span data-ttu-id="7d46a-135">0x8004101f</span><span class="sxs-lookup"><span data-stu-id="7d46a-135">0x8004101f</span></span> | <span data-ttu-id="7d46a-136">Возникла Недопустимая попытка указать **ключ** квалификатор для свойства, которое не может быть ключом.</span><span class="sxs-lookup"><span data-stu-id="7d46a-136">There was an illegal attempt to specify the **Key** qualifier on a property that cannot be a key.</span></span> <span data-ttu-id="7d46a-137">Ключи указываются om c; в группах доступности определение объекта и не могут быть изменены для каждого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="7d46a-137">The keys are specified om tje c;ass definition for an object and cannot be altered on a per-instance basis.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7d46a-138">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7d46a-138">0x80041008</span></span> | <span data-ttu-id="7d46a-139">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="7d46a-139">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | <span data-ttu-id="7d46a-140">0x80041029</span><span class="sxs-lookup"><span data-stu-id="7d46a-140">0x80041029</span></span> | <span data-ttu-id="7d46a-141">`pVal` Параметр не является типом квалификатора.</span><span class="sxs-lookup"><span data-stu-id="7d46a-141">The `pVal` parameter is not of a legal qualifier type.</span></span> |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | <span data-ttu-id="7d46a-142">0x8004101a</span><span class="sxs-lookup"><span data-stu-id="7d46a-142">0x8004101a</span></span> | <span data-ttu-id="7d46a-143">Невозможно вызвать `QualifierSet_Put` метод квалификатор, так как объект-владелец не разрешает переопределения.</span><span class="sxs-lookup"><span data-stu-id="7d46a-143">It is not possible to call the `QualifierSet_Put` method on the qualifier because the owning object does not permit overrides.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="7d46a-144">0</span><span class="sxs-lookup"><span data-stu-id="7d46a-144">0</span></span> | <span data-ttu-id="7d46a-145">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="7d46a-145">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="7d46a-146">Примечания</span><span class="sxs-lookup"><span data-stu-id="7d46a-146">Remarks</span></span>

<span data-ttu-id="7d46a-147">Эта функция создает оболочку для вызова [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) метод.</span><span class="sxs-lookup"><span data-stu-id="7d46a-147">This function wraps a call to the [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="7d46a-148">Требования</span><span class="sxs-lookup"><span data-stu-id="7d46a-148">Requirements</span></span>

<span data-ttu-id="7d46a-149">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d46a-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="7d46a-150">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7d46a-150">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="7d46a-151">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7d46a-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7d46a-152">См. также</span><span class="sxs-lookup"><span data-stu-id="7d46a-152">See also</span></span>

- [<span data-ttu-id="7d46a-153">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="7d46a-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
