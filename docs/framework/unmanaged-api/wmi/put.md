---
title: Функция перевода (Справочник по неуправляемым API)
description: Функция размещения присваивает новое значение именованному свойству.
ms.date: 11/06/2017
api_name:
- Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Put
helpviewer_keywords:
- Put function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f1bb8aa09a269e3b8fd23f393d63a275d308a77c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127401"
---
# <a name="put-function"></a><span data-ttu-id="e5d57-103">Функция размещения</span><span class="sxs-lookup"><span data-stu-id="e5d57-103">Put function</span></span>

<span data-ttu-id="e5d57-104">Задает новое значение для именованного свойства.</span><span class="sxs-lookup"><span data-stu-id="e5d57-104">Sets a named property to a new value.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="e5d57-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5d57-105">Syntax</span></span>

```cpp
HRESULT Put (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
);
```

## <a name="parameters"></a><span data-ttu-id="e5d57-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e5d57-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="e5d57-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="e5d57-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="e5d57-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="e5d57-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="e5d57-109">окне Имя свойства.</span><span class="sxs-lookup"><span data-stu-id="e5d57-109">[in] The name of the property.</span></span> <span data-ttu-id="e5d57-110">Этот параметр не может быть `null`.</span><span class="sxs-lookup"><span data-stu-id="e5d57-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="e5d57-111">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="e5d57-111">[in] Reserved.</span></span> <span data-ttu-id="e5d57-112">Этот параметр должен иметь значение 0.</span><span class="sxs-lookup"><span data-stu-id="e5d57-112">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="e5d57-113">окне Указатель на допустимое `VARIANT`, которое станет новым значением свойства.</span><span class="sxs-lookup"><span data-stu-id="e5d57-113">[in] A pointer to a valid `VARIANT` that becomes the new property value.</span></span> <span data-ttu-id="e5d57-114">Если `pVal` является `null` или указывает на `VARIANT` типа `VT_NULL`, свойству присваивается значение `null`.</span><span class="sxs-lookup"><span data-stu-id="e5d57-114">If `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`, the property is set to `null`.</span></span>

`vtType`\
<span data-ttu-id="e5d57-115">окне Тип `VARIANT` на который указывает `pVal`.</span><span class="sxs-lookup"><span data-stu-id="e5d57-115">[in] The type of `VARIANT` pointed to by `pVal`.</span></span> <span data-ttu-id="e5d57-116">Дополнительные сведения см. в разделе ["Примечания"](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="e5d57-116">See the [Remarks](#remarks) section for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="e5d57-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e5d57-117">Return value</span></span>

<span data-ttu-id="e5d57-118">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="e5d57-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e5d57-119">Константа</span><span class="sxs-lookup"><span data-stu-id="e5d57-119">Constant</span></span>  |<span data-ttu-id="e5d57-120">значения</span><span class="sxs-lookup"><span data-stu-id="e5d57-120">Value</span></span>  |<span data-ttu-id="e5d57-121">Описание</span><span class="sxs-lookup"><span data-stu-id="e5d57-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="e5d57-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="e5d57-122">0x80041001</span></span> | <span data-ttu-id="e5d57-123">Общий сбой.</span><span class="sxs-lookup"><span data-stu-id="e5d57-123">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e5d57-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e5d57-124">0x80041008</span></span> | <span data-ttu-id="e5d57-125">Один или несколько параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="e5d57-125">One or more parameters are not valid.</span></span> |
|`WBEM_E_INVALID_PROPERTY_TYPE` | <span data-ttu-id="e5d57-126">0x8004102a</span><span class="sxs-lookup"><span data-stu-id="e5d57-126">0x8004102a</span></span> | <span data-ttu-id="e5d57-127">Тип свойства не распознан.</span><span class="sxs-lookup"><span data-stu-id="e5d57-127">The property type is not recognized.</span></span> <span data-ttu-id="e5d57-128">Это значение возвращается при создании экземпляров класса, если класс уже существует.</span><span class="sxs-lookup"><span data-stu-id="e5d57-128">This value is returned when creating class instances if the class already exists.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e5d57-129">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e5d57-129">0x80041006</span></span> | <span data-ttu-id="e5d57-130">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="e5d57-130">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="e5d57-131">0x80041005</span><span class="sxs-lookup"><span data-stu-id="e5d57-131">0x80041005</span></span> | <span data-ttu-id="e5d57-132">Для экземпляров: указывает, что `pVal` указывает на `VARIANT` неверного типа для свойства.</span><span class="sxs-lookup"><span data-stu-id="e5d57-132">For instances: Indicates that `pVal` points to a `VARIANT` of an incorrect type for the property.</span></span> <br/> <span data-ttu-id="e5d57-133">Для определений классов: свойство уже существует в родительском классе, а новый COM-тип отличается от старого типа COM.</span><span class="sxs-lookup"><span data-stu-id="e5d57-133">For class definitions: The property already exists in the parent class, and the new COM type is different from the old COM type.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e5d57-134">0</span><span class="sxs-lookup"><span data-stu-id="e5d57-134">0</span></span> | <span data-ttu-id="e5d57-135">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="e5d57-135">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="e5d57-136">Заметки</span><span class="sxs-lookup"><span data-stu-id="e5d57-136">Remarks</span></span>

<span data-ttu-id="e5d57-137">Эта функция заключает вызов метода [ивбемклассобжект::P UT](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) .</span><span class="sxs-lookup"><span data-stu-id="e5d57-137">This function wraps a call to the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

<span data-ttu-id="e5d57-138">Эта функция всегда перезаписывает текущее значение свойства новым.</span><span class="sxs-lookup"><span data-stu-id="e5d57-138">This function always overwrites the current property value with a new one.</span></span> <span data-ttu-id="e5d57-139">Если [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) указывает на определение класса, `Put` создает или обновляет значение свойства.</span><span class="sxs-lookup"><span data-stu-id="e5d57-139">If the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a class definition, `Put` creates or updates the property value.</span></span> <span data-ttu-id="e5d57-140">Если [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) указывает на экземпляр CIM, `Put` обновляет только значение свойства; `Put` не может создать значение свойства.</span><span class="sxs-lookup"><span data-stu-id="e5d57-140">When [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a CIM instance, `Put` updates the property value only; `Put` cannot create a property value.</span></span>

<span data-ttu-id="e5d57-141">Системное свойство `__CLASS` доступно для записи только во время создания класса, если оно не может быть пустым.</span><span class="sxs-lookup"><span data-stu-id="e5d57-141">The `__CLASS` system property is only writable during class creation, when it may not be left blank.</span></span> <span data-ttu-id="e5d57-142">Все остальные системные свойства доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="e5d57-142">All other system properties are read-only.</span></span>

<span data-ttu-id="e5d57-143">Пользователь не может создавать свойства с именами, которые начинаются или заканчиваются символом подчеркивания ("_").</span><span class="sxs-lookup"><span data-stu-id="e5d57-143">A user cannot create properties with names that begin or end with an underscore ("_").</span></span> <span data-ttu-id="e5d57-144">Он зарезервирован для системных классов и свойств.</span><span class="sxs-lookup"><span data-stu-id="e5d57-144">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="e5d57-145">Если свойство, заданное `Put`ной функцией, существует в родительском классе, значение свойства по умолчанию изменяется, если тип свойства не совпадает с типом родительского класса.</span><span class="sxs-lookup"><span data-stu-id="e5d57-145">If the property set by the `Put` function exists in the parent class, the default value of the property is changed unless the property type does not match the parent class type.</span></span> <span data-ttu-id="e5d57-146">Если свойство не существует и не является несоответствием типов, создается свойство.</span><span class="sxs-lookup"><span data-stu-id="e5d57-146">If the property does not exist and it is not a type mismatch, the property is created.</span></span>

<span data-ttu-id="e5d57-147">Параметр `vtType` используется только при создании новых свойств в определении класса CIM, а `pVal` — `null` или указывает на `VARIANT` типа `VT_NULL`.</span><span class="sxs-lookup"><span data-stu-id="e5d57-147">Use the `vtType` parameter only when creating new properties in a CIM class definition and `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`.</span></span> <span data-ttu-id="e5d57-148">В этом случае параметр `vType` указывает тип CIM для свойства.</span><span class="sxs-lookup"><span data-stu-id="e5d57-148">In this case, the `vType` parameter specifies the CIM type of the property.</span></span> <span data-ttu-id="e5d57-149">Во всех остальных случаях `vtType` должны быть равны 0.</span><span class="sxs-lookup"><span data-stu-id="e5d57-149">In every other case, `vtType` must be 0.</span></span> <span data-ttu-id="e5d57-150">`vtType` также должен быть равен 0, если базовый объект является экземпляром (даже если `Val` `null`), так как тип свойства является фиксированным и не может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="e5d57-150">`vtType` must also be 0 if the underlying object is an instance (even if `Val` is `null`) because the type of the property is fixed and cannot be changed.</span></span>

## <a name="example"></a><span data-ttu-id="e5d57-151">Пример</span><span class="sxs-lookup"><span data-stu-id="e5d57-151">Example</span></span>

<span data-ttu-id="e5d57-152">Пример см. в описании метода [ивбемклассобжект::P UT](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) .</span><span class="sxs-lookup"><span data-stu-id="e5d57-152">For an example, see the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="e5d57-153">Требования</span><span class="sxs-lookup"><span data-stu-id="e5d57-153">Requirements</span></span>

<span data-ttu-id="e5d57-154">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5d57-154">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="e5d57-155">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="e5d57-155">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="e5d57-156">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e5d57-156">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e5d57-157">См. также</span><span class="sxs-lookup"><span data-stu-id="e5d57-157">See also</span></span>

- [<span data-ttu-id="e5d57-158">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="e5d57-158">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
