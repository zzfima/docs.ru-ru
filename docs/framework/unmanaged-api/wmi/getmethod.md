---
title: Функция GetMethod (Справочник по неуправляемым API)
description: Функция GetMethod получает сведения о методе.
ms.date: 11/06/2017
api_name:
- GetMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethod
helpviewer_keywords:
- GetMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb8919e8760616676ea5ff99069e2d2ceb5f7451
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608922"
---
# <a name="getmethod-function"></a><span data-ttu-id="7e177-103">Функция GetMethod</span><span class="sxs-lookup"><span data-stu-id="7e177-103">GetMethod function</span></span>

<span data-ttu-id="7e177-104">Получает сведения об указанном методе.</span><span class="sxs-lookup"><span data-stu-id="7e177-104">Retrieves information about the specified method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="7e177-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e177-105">Syntax</span></span>

```cpp
HRESULT GetMethod (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
);
```

## <a name="parameters"></a><span data-ttu-id="7e177-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7e177-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="7e177-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="7e177-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="7e177-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="7e177-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="7e177-109">[in] Имя метода.</span><span class="sxs-lookup"><span data-stu-id="7e177-109">[in] The method name.</span></span> <span data-ttu-id="7e177-110">Этот параметр не может быть `null` и должен указывать на допустимый `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="7e177-110">This parameter cannot be `null` and must point to a valid `LPCWSTR`.</span></span>

`lFlags`\
<span data-ttu-id="7e177-111">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="7e177-111">[in] Reserved.</span></span> <span data-ttu-id="7e177-112">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="7e177-112">This parameter must be 0.</span></span>

`ppInSignature`\
<span data-ttu-id="7e177-113">[out] Указатель на адрес [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляр, описывающий входные параметры метода.</span><span class="sxs-lookup"><span data-stu-id="7e177-113">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the in parameters to the method.</span></span> <span data-ttu-id="7e177-114">Этот параметр учитывается, если он становится равным `null`.</span><span class="sxs-lookup"><span data-stu-id="7e177-114">This parameter is ignored if it is set to `null`.</span></span>

`ppOutSignature`\
<span data-ttu-id="7e177-115">[out] Указатель на адрес [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляр, описывающий выходные параметры метода.</span><span class="sxs-lookup"><span data-stu-id="7e177-115">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the out parameters to the method.</span></span> <span data-ttu-id="7e177-116">Этот параметр учитывается, если он становится равным `null`.</span><span class="sxs-lookup"><span data-stu-id="7e177-116">This parameter is ignored if it is set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="7e177-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7e177-117">Return value</span></span>

<span data-ttu-id="7e177-118">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="7e177-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7e177-119">Константа</span><span class="sxs-lookup"><span data-stu-id="7e177-119">Constant</span></span>  |<span data-ttu-id="7e177-120">Значение</span><span class="sxs-lookup"><span data-stu-id="7e177-120">Value</span></span>  |<span data-ttu-id="7e177-121">Описание</span><span class="sxs-lookup"><span data-stu-id="7e177-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="7e177-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="7e177-122">0x80041002</span></span> | <span data-ttu-id="7e177-123">Указанное свойство не найден.</span><span class="sxs-lookup"><span data-stu-id="7e177-123">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7e177-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7e177-124">0x80041006</span></span> | <span data-ttu-id="7e177-125">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="7e177-125">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="7e177-126">0</span><span class="sxs-lookup"><span data-stu-id="7e177-126">0</span></span> | <span data-ttu-id="7e177-127">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="7e177-127">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="7e177-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="7e177-128">Remarks</span></span>

<span data-ttu-id="7e177-129">Эта функция создает оболочку для вызова [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) метод.</span><span class="sxs-lookup"><span data-stu-id="7e177-129">This function wraps a call to the [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="7e177-130">Можно установить Windows Management [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) указатель на `null` Если у метода нет входные параметры.</span><span class="sxs-lookup"><span data-stu-id="7e177-130">Windows Management can set the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointer to `null` if the method has no in parameters.</span></span>

<span data-ttu-id="7e177-131">В `ppInSignature` и `ppOutSignature` описывают входным и выходным параметрами, соответственно, в виде свойств `IWbemClassObject` экземпляр системного класса [_Parameters](/windows/desktop/WmiSdk/--parameters).</span><span class="sxs-lookup"><span data-stu-id="7e177-131">In `ppInSignature` and `ppOutSignature` describe in and out parameters, respectively, as properties in a `IWbemClassObject` instance of the system class [_Parameters](/windows/desktop/WmiSdk/--parameters).</span></span> <span data-ttu-id="7e177-132">Свойства в `ppInSignature` именуются `Param` *n*, где *n* позиция параметра в сигнатуре метода (такие как `Param1`, `Param2`и т. д.).</span><span class="sxs-lookup"><span data-stu-id="7e177-132">The properties in `ppInSignature` are named `Param`*n*, where *n* is the position of the parameter in the method signature (such as `Param1`, `Param2`, etc.).</span></span> <span data-ttu-id="7e177-133">Свойства в `ppOutSignature` также называются `Param` *n*, и возвращаемое значение имеет имя `ReturnValue`.</span><span class="sxs-lookup"><span data-stu-id="7e177-133">The properties in `ppOutSignature` are also named `Param`*n*, and the return value is named `ReturnValue`.</span></span> <span data-ttu-id="7e177-134">Дополнительные сведения и пример см. в разделе [IWbemClassObject::GetMethod метод](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span><span class="sxs-lookup"><span data-stu-id="7e177-134">For more information and an example, see [IWbemClassObject::GetMethod method](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span></span>

## <a name="requirements"></a><span data-ttu-id="7e177-135">Требования</span><span class="sxs-lookup"><span data-stu-id="7e177-135">Requirements</span></span>

<span data-ttu-id="7e177-136">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e177-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="7e177-137">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7e177-137">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="7e177-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7e177-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7e177-139">См. также</span><span class="sxs-lookup"><span data-stu-id="7e177-139">See also</span></span>

- [<span data-ttu-id="7e177-140">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="7e177-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)