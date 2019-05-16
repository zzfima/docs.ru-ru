---
title: Функция Next (Справочник по неуправляемым API)
description: Далее функция получает следующее свойство в перечисление.
ms.date: 11/06/2017
api_name:
- Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Next
helpviewer_keywords:
- Next function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5b456feeb1cb09e4957e470344146cf4358d8c7
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636161"
---
# <a name="next-function"></a><span data-ttu-id="d1a39-103">Функция Next</span><span class="sxs-lookup"><span data-stu-id="d1a39-103">Next function</span></span>
<span data-ttu-id="d1a39-104">Извлекает следующее свойство в перечисление, которое начинается с вызова [BeginEnumeration](beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="d1a39-104">Retrieves the next property in an enumeration that begins with a call to [BeginEnumeration](beginenumeration.md).</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="d1a39-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1a39-105">Syntax</span></span>

```cpp
HRESULT Next (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lFlags,
   [out] BSTR*            pstrName,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="d1a39-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d1a39-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="d1a39-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="d1a39-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="d1a39-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d1a39-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`\
<span data-ttu-id="d1a39-109">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="d1a39-109">[in] Reserved.</span></span> <span data-ttu-id="d1a39-110">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="d1a39-110">This parameter must be 0.</span></span>

`pstrName`\
<span data-ttu-id="d1a39-111">[out] Новый `BSTR` , содержащий имя свойства.</span><span class="sxs-lookup"><span data-stu-id="d1a39-111">[out] A new `BSTR` that contains the property name.</span></span> <span data-ttu-id="d1a39-112">Этот параметр можно задавать `null` Если имя не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="d1a39-112">You can set this parameter to `null` if the name is not required.</span></span>

`pVal`\
<span data-ttu-id="d1a39-113">[out] Объект `VARIANT` подставлено значение свойства.</span><span class="sxs-lookup"><span data-stu-id="d1a39-113">[out] A `VARIANT` filled with the value of the property.</span></span> <span data-ttu-id="d1a39-114">Этот параметр можно задавать `null` Если значение не требуется.</span><span class="sxs-lookup"><span data-stu-id="d1a39-114">You can set this parameter to `null` if the value is not required.</span></span> <span data-ttu-id="d1a39-115">Если функция возвращает код ошибки `VARIANT` передается `pVal` слева без изменений.</span><span class="sxs-lookup"><span data-stu-id="d1a39-115">If the function returns an error code, the `VARIANT` passed to `pVal` is left unmodified.</span></span>

`pvtType`\
<span data-ttu-id="d1a39-116">[out] Указатель на `CIMTYPE` переменной ( `LONG` в который помещается тип свойства).</span><span class="sxs-lookup"><span data-stu-id="d1a39-116">[out] A pointer to a `CIMTYPE` variable (a `LONG` into which the type of the property is placed).</span></span> <span data-ttu-id="d1a39-117">Значение этого свойства может быть `VT_NULL_VARIANT`, в этом случае это необходимо определить фактический тип свойства.</span><span class="sxs-lookup"><span data-stu-id="d1a39-117">The value of this property can be a `VT_NULL_VARIANT`, in which case it is necessary to determine the actual type of the property.</span></span> <span data-ttu-id="d1a39-118">Этот параметр также может быть `null`.</span><span class="sxs-lookup"><span data-stu-id="d1a39-118">This parameter can also be `null`.</span></span>

`plFlavor`\
<span data-ttu-id="d1a39-119">[out] `null`, или значение, которое получает данные на сервере-источнике свойства.</span><span class="sxs-lookup"><span data-stu-id="d1a39-119">[out] `null`, or a value that receives information on the origin of the property.</span></span> <span data-ttu-id="d1a39-120">См. в разделе [Примечание] возможные значения.</span><span class="sxs-lookup"><span data-stu-id="d1a39-120">See the [Remarks] section for possible values.</span></span>

## <a name="return-value"></a><span data-ttu-id="d1a39-121">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d1a39-121">Return value</span></span>

<span data-ttu-id="d1a39-122">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="d1a39-122">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d1a39-123">Константа</span><span class="sxs-lookup"><span data-stu-id="d1a39-123">Constant</span></span>  |<span data-ttu-id="d1a39-124">Значение</span><span class="sxs-lookup"><span data-stu-id="d1a39-124">Value</span></span>  |<span data-ttu-id="d1a39-125">Описание</span><span class="sxs-lookup"><span data-stu-id="d1a39-125">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="d1a39-126">0x80041001</span><span class="sxs-lookup"><span data-stu-id="d1a39-126">0x80041001</span></span> | <span data-ttu-id="d1a39-127">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="d1a39-127">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="d1a39-128">0x80041008</span><span class="sxs-lookup"><span data-stu-id="d1a39-128">0x80041008</span></span> | <span data-ttu-id="d1a39-129">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="d1a39-129">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="d1a39-130">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="d1a39-130">0x8004101d</span></span> | <span data-ttu-id="d1a39-131">Возникла не вызывался метод [ `BeginEnumeration` ](beginenumeration.md) функции.</span><span class="sxs-lookup"><span data-stu-id="d1a39-131">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="d1a39-132">0x80041006</span><span class="sxs-lookup"><span data-stu-id="d1a39-132">0x80041006</span></span> | <span data-ttu-id="d1a39-133">Не хватает памяти, позволяющих начать новое перечисление.</span><span class="sxs-lookup"><span data-stu-id="d1a39-133">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="d1a39-134">0x80041015</span><span class="sxs-lookup"><span data-stu-id="d1a39-134">0x80041015</span></span> | <span data-ttu-id="d1a39-135">Удаленный вызов процедур между текущего процесса и управления Windows не удалось.</span><span class="sxs-lookup"><span data-stu-id="d1a39-135">The remote procedure call between the current process and Windows Management failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="d1a39-136">0</span><span class="sxs-lookup"><span data-stu-id="d1a39-136">0</span></span> | <span data-ttu-id="d1a39-137">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="d1a39-137">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="d1a39-138">0x40005</span><span class="sxs-lookup"><span data-stu-id="d1a39-138">0x40005</span></span> | <span data-ttu-id="d1a39-139">Нет дополнительных свойств в перечислении.</span><span class="sxs-lookup"><span data-stu-id="d1a39-139">There are no more properties in the enumeration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d1a39-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="d1a39-140">Remarks</span></span>

<span data-ttu-id="d1a39-141">Эта функция создает оболочку для вызова [IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) метод.</span><span class="sxs-lookup"><span data-stu-id="d1a39-141">This function wraps a call to the [IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) method.</span></span>

<span data-ttu-id="d1a39-142">Этот метод также возвращает системные свойства.</span><span class="sxs-lookup"><span data-stu-id="d1a39-142">This method also returns system properties.</span></span>

<span data-ttu-id="d1a39-143">Если базовый тип свойства объекта пути, даты или времени или другой специальный тип, возвращаемый тип не содержит достаточно информации.</span><span class="sxs-lookup"><span data-stu-id="d1a39-143">If the underlying type of the property is an object path, a date or time, or another special type, then the returned type does not contain enough information.</span></span> <span data-ttu-id="d1a39-144">Вызывающий объект должен проверить `CIMTYPE` для указанного свойства определить, является ли свойство ссылку на объект, даты или времени или другой специальный тип.</span><span class="sxs-lookup"><span data-stu-id="d1a39-144">The caller must examine the `CIMTYPE` for the specified property to determine if the property is an object reference, a date or time, or another special type.</span></span>

<span data-ttu-id="d1a39-145">Если `plFlavor` не `null`, `LONG` значение получает сведения о происхождении свойства, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d1a39-145">If `plFlavor` is not `null`, the `LONG` value receives information about the origin of the property, as follows:</span></span>

|<span data-ttu-id="d1a39-146">Константа</span><span class="sxs-lookup"><span data-stu-id="d1a39-146">Constant</span></span>  |<span data-ttu-id="d1a39-147">Значение</span><span class="sxs-lookup"><span data-stu-id="d1a39-147">Value</span></span>  |<span data-ttu-id="d1a39-148">Описание</span><span class="sxs-lookup"><span data-stu-id="d1a39-148">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="d1a39-149">0x40</span><span class="sxs-lookup"><span data-stu-id="d1a39-149">0x40</span></span> | <span data-ttu-id="d1a39-150">Свойство является свойством стандартной системы.</span><span class="sxs-lookup"><span data-stu-id="d1a39-150">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="d1a39-151">0x20</span><span class="sxs-lookup"><span data-stu-id="d1a39-151">0x20</span></span> | <span data-ttu-id="d1a39-152">Для класса: Свойство наследуется от родительского класса.</span><span class="sxs-lookup"><span data-stu-id="d1a39-152">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="d1a39-153">Для экземпляра: Свойство, хотя наследуется от родительского класса, не был изменен в экземпляре.</span><span class="sxs-lookup"><span data-stu-id="d1a39-153">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="d1a39-154">0</span><span class="sxs-lookup"><span data-stu-id="d1a39-154">0</span></span> | <span data-ttu-id="d1a39-155">Для класса: Свойство принадлежит к производному классу.</span><span class="sxs-lookup"><span data-stu-id="d1a39-155">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="d1a39-156">Для экземпляра: Свойство изменяется в экземпляре; то есть значение было предоставлено или квалификатор был добавлен или изменен.</span><span class="sxs-lookup"><span data-stu-id="d1a39-156">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="requirements"></a><span data-ttu-id="d1a39-157">Требования</span><span class="sxs-lookup"><span data-stu-id="d1a39-157">Requirements</span></span>

<span data-ttu-id="d1a39-158">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1a39-158">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="d1a39-159">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d1a39-159">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="d1a39-160">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d1a39-160">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d1a39-161">См. также</span><span class="sxs-lookup"><span data-stu-id="d1a39-161">See also</span></span>

- [<span data-ttu-id="d1a39-162">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="d1a39-162">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
