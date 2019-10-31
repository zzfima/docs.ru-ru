---
title: Функция Get (Справочник по неуправляемым API)
description: Функция Get извлекает указанное значение свойства.
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
ms.openlocfilehash: 60f29b91000fd3c07efea88dcc319eb283a4af78
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120327"
---
# <a name="get-function"></a><span data-ttu-id="51f82-103">Функция Get</span><span class="sxs-lookup"><span data-stu-id="51f82-103">Get function</span></span>

<span data-ttu-id="51f82-104">Возвращает указанное значение свойства, если оно существует.</span><span class="sxs-lookup"><span data-stu-id="51f82-104">Retrieves the specified property value if it exists.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="51f82-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51f82-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="51f82-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="51f82-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="51f82-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="51f82-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="51f82-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="51f82-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="51f82-109">окне Имя свойства.</span><span class="sxs-lookup"><span data-stu-id="51f82-109">[in] The name of the property.</span></span>

`lFlags`\
<span data-ttu-id="51f82-110">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="51f82-110">[in] Reserved.</span></span> <span data-ttu-id="51f82-111">Этот параметр должен иметь значение 0.</span><span class="sxs-lookup"><span data-stu-id="51f82-111">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="51f82-112">заполняет Если функция возвращается успешно, содержит значение свойства `wszName`.</span><span class="sxs-lookup"><span data-stu-id="51f82-112">[out] If the function returns successfully, contains the value of the `wszName` property.</span></span> <span data-ttu-id="51f82-113">Аргументу `pval` присваивается правильный тип и значение для квалификатора.</span><span class="sxs-lookup"><span data-stu-id="51f82-113">The `pval` argument is assigned the correct type and value for the qualifier.</span></span>

`pvtType`\
<span data-ttu-id="51f82-114">заполняет Если функция возвращает значение успешно, содержит [константу типа CIM](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) , которая указывает тип свойства.</span><span class="sxs-lookup"><span data-stu-id="51f82-114">[out] If the function returns successfully, contains a [CIM-type constant](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) that indicates the property type.</span></span> <span data-ttu-id="51f82-115">Его значение также можно `null`.</span><span class="sxs-lookup"><span data-stu-id="51f82-115">Its value can also be `null`.</span></span> 

`plFlavor`\
<span data-ttu-id="51f82-116">заполняет Если функция возвращается успешно, получает сведения об источнике свойства.</span><span class="sxs-lookup"><span data-stu-id="51f82-116">[out] If the function returns successfully, receives information about the origin of the property.</span></span> <span data-ttu-id="51f82-117">Его значением может быть `null`или одна из следующих констант WBEM_FLAVOR_TYPE, определенных в файле заголовка *вбемкли. h* :</span><span class="sxs-lookup"><span data-stu-id="51f82-117">Its value can be `null`, or one of the following WBEM_FLAVOR_TYPE constants defined in the *WbemCli.h* header file:</span></span> 

|<span data-ttu-id="51f82-118">Константа</span><span class="sxs-lookup"><span data-stu-id="51f82-118">Constant</span></span>  |<span data-ttu-id="51f82-119">значения</span><span class="sxs-lookup"><span data-stu-id="51f82-119">Value</span></span>  |<span data-ttu-id="51f82-120">Описание</span><span class="sxs-lookup"><span data-stu-id="51f82-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="51f82-121">0x40</span><span class="sxs-lookup"><span data-stu-id="51f82-121">0x40</span></span> | <span data-ttu-id="51f82-122">Свойство является стандартным системным свойством.</span><span class="sxs-lookup"><span data-stu-id="51f82-122">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="51f82-123">0x20</span><span class="sxs-lookup"><span data-stu-id="51f82-123">0x20</span></span> | <span data-ttu-id="51f82-124">Для класса: свойство наследуется от родительского класса.</span><span class="sxs-lookup"><span data-stu-id="51f82-124">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="51f82-125">Для экземпляра: свойство, наследуемое от родительского класса, не было изменено экземпляром.</span><span class="sxs-lookup"><span data-stu-id="51f82-125">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="51f82-126">0</span><span class="sxs-lookup"><span data-stu-id="51f82-126">0</span></span> | <span data-ttu-id="51f82-127">Для класса: свойство принадлежит производному классу.</span><span class="sxs-lookup"><span data-stu-id="51f82-127">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="51f82-128">Для экземпляра: свойство изменяется экземпляром; Это значит, что было предоставлено значение или был добавлен или изменен квалификатор.</span><span class="sxs-lookup"><span data-stu-id="51f82-128">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="return-value"></a><span data-ttu-id="51f82-129">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="51f82-129">Return value</span></span>

<span data-ttu-id="51f82-130">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="51f82-130">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="51f82-131">Константа</span><span class="sxs-lookup"><span data-stu-id="51f82-131">Constant</span></span>  |<span data-ttu-id="51f82-132">значения</span><span class="sxs-lookup"><span data-stu-id="51f82-132">Value</span></span>  |<span data-ttu-id="51f82-133">Описание</span><span class="sxs-lookup"><span data-stu-id="51f82-133">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="51f82-134">0x80041001</span><span class="sxs-lookup"><span data-stu-id="51f82-134">0x80041001</span></span> | <span data-ttu-id="51f82-135">Общий сбой.</span><span class="sxs-lookup"><span data-stu-id="51f82-135">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="51f82-136">0x80041008</span><span class="sxs-lookup"><span data-stu-id="51f82-136">0x80041008</span></span> | <span data-ttu-id="51f82-137">Один или несколько параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="51f82-137">One or more parameters are not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="51f82-138">0x80041002</span><span class="sxs-lookup"><span data-stu-id="51f82-138">0x80041002</span></span> | <span data-ttu-id="51f82-139">Указанное свойство не найдено.</span><span class="sxs-lookup"><span data-stu-id="51f82-139">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="51f82-140">0x80041006</span><span class="sxs-lookup"><span data-stu-id="51f82-140">0x80041006</span></span> | <span data-ttu-id="51f82-141">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="51f82-141">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="51f82-142">0</span><span class="sxs-lookup"><span data-stu-id="51f82-142">0</span></span> | <span data-ttu-id="51f82-143">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="51f82-143">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="51f82-144">Заметки</span><span class="sxs-lookup"><span data-stu-id="51f82-144">Remarks</span></span>

<span data-ttu-id="51f82-145">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) .</span><span class="sxs-lookup"><span data-stu-id="51f82-145">This function wraps a call to the [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) method.</span></span>

<span data-ttu-id="51f82-146">Функция `Get` может также возвращать системные свойства.</span><span class="sxs-lookup"><span data-stu-id="51f82-146">The `Get` function can also return system properties.</span></span>

<span data-ttu-id="51f82-147">Аргументу `pVal` присваивается правильный тип и значение для квалификатора и COM-функции [вариантинит](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit)</span><span class="sxs-lookup"><span data-stu-id="51f82-147">The `pVal` argument is assigned the correct type and value for the qualifier and the COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) function</span></span>

## <a name="requirements"></a><span data-ttu-id="51f82-148">Требования</span><span class="sxs-lookup"><span data-stu-id="51f82-148">Requirements</span></span>

 <span data-ttu-id="51f82-149">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51f82-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="51f82-150">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="51f82-150">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="51f82-151">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="51f82-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="51f82-152">См. также</span><span class="sxs-lookup"><span data-stu-id="51f82-152">See also</span></span>

- [<span data-ttu-id="51f82-153">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="51f82-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
