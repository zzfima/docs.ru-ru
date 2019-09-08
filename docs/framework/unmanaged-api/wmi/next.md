---
title: Функция Next (Справочник по неуправляемым интерфейсам API)
description: Следующая функция извлекает свойство Next в перечислении.
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
ms.openlocfilehash: 95cea4cb3e7e7df2b6b52256a440b9a8d544f2db
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798409"
---
# <a name="next-function"></a><span data-ttu-id="a0886-103">Функция Next</span><span class="sxs-lookup"><span data-stu-id="a0886-103">Next function</span></span>
<span data-ttu-id="a0886-104">Извлекает свойство Next в перечислении, которое начинается с вызова [BeginEnumeration](beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="a0886-104">Retrieves the next property in an enumeration that begins with a call to [BeginEnumeration](beginenumeration.md).</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="a0886-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0886-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="a0886-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0886-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="a0886-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="a0886-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="a0886-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="a0886-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`\
<span data-ttu-id="a0886-109">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="a0886-109">[in] Reserved.</span></span> <span data-ttu-id="a0886-110">Этот параметр должен иметь значение 0.</span><span class="sxs-lookup"><span data-stu-id="a0886-110">This parameter must be 0.</span></span>

`pstrName`\
<span data-ttu-id="a0886-111">заполняет Новый `BSTR` объект, содержащий имя свойства.</span><span class="sxs-lookup"><span data-stu-id="a0886-111">[out] A new `BSTR` that contains the property name.</span></span> <span data-ttu-id="a0886-112">Этот параметр можно установить в `null` значение, если имя не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="a0886-112">You can set this parameter to `null` if the name is not required.</span></span>

`pVal`\
<span data-ttu-id="a0886-113">заполняет `VARIANT` Заполняется значением свойства.</span><span class="sxs-lookup"><span data-stu-id="a0886-113">[out] A `VARIANT` filled with the value of the property.</span></span> <span data-ttu-id="a0886-114">Этот параметр можно задать равным `null` , если значение не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="a0886-114">You can set this parameter to `null` if the value is not required.</span></span> <span data-ttu-id="a0886-115">Если функция возвращает код ошибки, `VARIANT` `pVal` переданный метод остается неизменным.</span><span class="sxs-lookup"><span data-stu-id="a0886-115">If the function returns an error code, the `VARIANT` passed to `pVal` is left unmodified.</span></span>

`pvtType`\
<span data-ttu-id="a0886-116">заполняет Указатель на `CIMTYPE` переменную `LONG` (в которой размещается тип свойства).</span><span class="sxs-lookup"><span data-stu-id="a0886-116">[out] A pointer to a `CIMTYPE` variable (a `LONG` into which the type of the property is placed).</span></span> <span data-ttu-id="a0886-117">Значением этого свойства может быть `VT_NULL_VARIANT`, в этом случае необходимо определить фактический тип свойства.</span><span class="sxs-lookup"><span data-stu-id="a0886-117">The value of this property can be a `VT_NULL_VARIANT`, in which case it is necessary to determine the actual type of the property.</span></span> <span data-ttu-id="a0886-118">Этот параметр также может иметь `null`следующий аргумент:.</span><span class="sxs-lookup"><span data-stu-id="a0886-118">This parameter can also be `null`.</span></span>

`plFlavor`\
<span data-ttu-id="a0886-119">заполняет `null`или значение, получающее сведения об источнике свойства.</span><span class="sxs-lookup"><span data-stu-id="a0886-119">[out] `null`, or a value that receives information on the origin of the property.</span></span> <span data-ttu-id="a0886-120">Возможные значения см. в разделе [примечания].</span><span class="sxs-lookup"><span data-stu-id="a0886-120">See the [Remarks] section for possible values.</span></span>

## <a name="return-value"></a><span data-ttu-id="a0886-121">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a0886-121">Return value</span></span>

<span data-ttu-id="a0886-122">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="a0886-122">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a0886-123">Константа</span><span class="sxs-lookup"><span data-stu-id="a0886-123">Constant</span></span>  |<span data-ttu-id="a0886-124">Значение</span><span class="sxs-lookup"><span data-stu-id="a0886-124">Value</span></span>  |<span data-ttu-id="a0886-125">Описание</span><span class="sxs-lookup"><span data-stu-id="a0886-125">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="a0886-126">0x80041001</span><span class="sxs-lookup"><span data-stu-id="a0886-126">0x80041001</span></span> | <span data-ttu-id="a0886-127">Общий сбой.</span><span class="sxs-lookup"><span data-stu-id="a0886-127">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="a0886-128">0x80041008</span><span class="sxs-lookup"><span data-stu-id="a0886-128">0x80041008</span></span> | <span data-ttu-id="a0886-129">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="a0886-129">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="a0886-130">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="a0886-130">0x8004101d</span></span> | <span data-ttu-id="a0886-131">Нет вызова [`BeginEnumeration`](beginenumeration.md) функции.</span><span class="sxs-lookup"><span data-stu-id="a0886-131">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="a0886-132">0x80041006</span><span class="sxs-lookup"><span data-stu-id="a0886-132">0x80041006</span></span> | <span data-ttu-id="a0886-133">Недостаточно памяти для начала нового перечисления.</span><span class="sxs-lookup"><span data-stu-id="a0886-133">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="a0886-134">0x80041015</span><span class="sxs-lookup"><span data-stu-id="a0886-134">0x80041015</span></span> | <span data-ttu-id="a0886-135">Сбой удаленного вызова процедур между текущим процессом и управлением Windows.</span><span class="sxs-lookup"><span data-stu-id="a0886-135">The remote procedure call between the current process and Windows Management failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="a0886-136">0</span><span class="sxs-lookup"><span data-stu-id="a0886-136">0</span></span> | <span data-ttu-id="a0886-137">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="a0886-137">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="a0886-138">0x40005</span><span class="sxs-lookup"><span data-stu-id="a0886-138">0x40005</span></span> | <span data-ttu-id="a0886-139">В перечислении больше нет свойств.</span><span class="sxs-lookup"><span data-stu-id="a0886-139">There are no more properties in the enumeration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="a0886-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0886-140">Remarks</span></span>

<span data-ttu-id="a0886-141">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) .</span><span class="sxs-lookup"><span data-stu-id="a0886-141">This function wraps a call to the [IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) method.</span></span>

<span data-ttu-id="a0886-142">Этот метод также возвращает системные свойства.</span><span class="sxs-lookup"><span data-stu-id="a0886-142">This method also returns system properties.</span></span>

<span data-ttu-id="a0886-143">Если базовым типом свойства является путь к объекту, дата или время или другой специальный тип, возвращаемый тип не содержит достаточной информации.</span><span class="sxs-lookup"><span data-stu-id="a0886-143">If the underlying type of the property is an object path, a date or time, or another special type, then the returned type does not contain enough information.</span></span> <span data-ttu-id="a0886-144">Вызывающий объект должен проверить `CIMTYPE` для указанного свойства, чтобы определить, является ли свойство ссылкой на объект, датой или временем или другим специальным типом.</span><span class="sxs-lookup"><span data-stu-id="a0886-144">The caller must examine the `CIMTYPE` for the specified property to determine if the property is an object reference, a date or time, or another special type.</span></span>

<span data-ttu-id="a0886-145">Если `plFlavor` параметр не `null`равен, `LONG` значение получает сведения о происхождении свойства, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="a0886-145">If `plFlavor` is not `null`, the `LONG` value receives information about the origin of the property, as follows:</span></span>

|<span data-ttu-id="a0886-146">Константа</span><span class="sxs-lookup"><span data-stu-id="a0886-146">Constant</span></span>  |<span data-ttu-id="a0886-147">Значение</span><span class="sxs-lookup"><span data-stu-id="a0886-147">Value</span></span>  |<span data-ttu-id="a0886-148">Описание</span><span class="sxs-lookup"><span data-stu-id="a0886-148">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="a0886-149">0x40</span><span class="sxs-lookup"><span data-stu-id="a0886-149">0x40</span></span> | <span data-ttu-id="a0886-150">Свойство является стандартным системным свойством.</span><span class="sxs-lookup"><span data-stu-id="a0886-150">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="a0886-151">0x20</span><span class="sxs-lookup"><span data-stu-id="a0886-151">0x20</span></span> | <span data-ttu-id="a0886-152">Для класса: Свойство наследуется от родительского класса.</span><span class="sxs-lookup"><span data-stu-id="a0886-152">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="a0886-153">Для экземпляра: Свойство, наследуемое от родительского класса, не было изменено экземпляром.</span><span class="sxs-lookup"><span data-stu-id="a0886-153">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="a0886-154">0</span><span class="sxs-lookup"><span data-stu-id="a0886-154">0</span></span> | <span data-ttu-id="a0886-155">Для класса: Свойство принадлежит производному классу.</span><span class="sxs-lookup"><span data-stu-id="a0886-155">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="a0886-156">Для экземпляра: Свойство изменяется экземпляром; Это значит, что было предоставлено значение или был добавлен или изменен квалификатор.</span><span class="sxs-lookup"><span data-stu-id="a0886-156">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="requirements"></a><span data-ttu-id="a0886-157">Требования</span><span class="sxs-lookup"><span data-stu-id="a0886-157">Requirements</span></span>

<span data-ttu-id="a0886-158">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0886-158">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="a0886-159">**Заголовок.** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="a0886-159">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="a0886-160">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a0886-160">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a0886-161">См. также</span><span class="sxs-lookup"><span data-stu-id="a0886-161">See also</span></span>

- [<span data-ttu-id="a0886-162">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="a0886-162">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
