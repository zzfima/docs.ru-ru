---
title: Функция метода WebMethod (Справочник по неуправляемым интерфейсам API)
description: Функция метода WebMethod получает сведения о методе.
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
ms.openlocfilehash: b9cc185bf8cccb8ed3c24e28954afd86464602d7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798565"
---
# <a name="getmethod-function"></a><span data-ttu-id="b58c7-103">Функция GetMethod</span><span class="sxs-lookup"><span data-stu-id="b58c7-103">GetMethod function</span></span>

<span data-ttu-id="b58c7-104">Получает сведения об указанном методе.</span><span class="sxs-lookup"><span data-stu-id="b58c7-104">Retrieves information about the specified method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="b58c7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b58c7-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="b58c7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b58c7-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="b58c7-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="b58c7-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="b58c7-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="b58c7-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="b58c7-109">окне Имя метода.</span><span class="sxs-lookup"><span data-stu-id="b58c7-109">[in] The method name.</span></span> <span data-ttu-id="b58c7-110">Этот параметр не может `null` быть и должен указывать на допустимый. `LPCWSTR`</span><span class="sxs-lookup"><span data-stu-id="b58c7-110">This parameter cannot be `null` and must point to a valid `LPCWSTR`.</span></span>

`lFlags`\
<span data-ttu-id="b58c7-111">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="b58c7-111">[in] Reserved.</span></span> <span data-ttu-id="b58c7-112">Этот параметр должен иметь значение 0.</span><span class="sxs-lookup"><span data-stu-id="b58c7-112">This parameter must be 0.</span></span>

`ppInSignature`\
<span data-ttu-id="b58c7-113">заполняет Указатель на адрес экземпляра [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , который описывает входные параметры метода.</span><span class="sxs-lookup"><span data-stu-id="b58c7-113">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the in parameters to the method.</span></span> <span data-ttu-id="b58c7-114">Этот параметр пропускается, если он имеет `null`значение.</span><span class="sxs-lookup"><span data-stu-id="b58c7-114">This parameter is ignored if it is set to `null`.</span></span>

`ppOutSignature`\
<span data-ttu-id="b58c7-115">заполняет Указатель на адрес экземпляра [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , который описывает выходные параметры метода.</span><span class="sxs-lookup"><span data-stu-id="b58c7-115">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the out parameters to the method.</span></span> <span data-ttu-id="b58c7-116">Этот параметр пропускается, если он имеет `null`значение.</span><span class="sxs-lookup"><span data-stu-id="b58c7-116">This parameter is ignored if it is set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="b58c7-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b58c7-117">Return value</span></span>

<span data-ttu-id="b58c7-118">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="b58c7-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b58c7-119">Константа</span><span class="sxs-lookup"><span data-stu-id="b58c7-119">Constant</span></span>  |<span data-ttu-id="b58c7-120">Значение</span><span class="sxs-lookup"><span data-stu-id="b58c7-120">Value</span></span>  |<span data-ttu-id="b58c7-121">Описание</span><span class="sxs-lookup"><span data-stu-id="b58c7-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="b58c7-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="b58c7-122">0x80041002</span></span> | <span data-ttu-id="b58c7-123">Указанное свойство не найдено.</span><span class="sxs-lookup"><span data-stu-id="b58c7-123">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b58c7-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="b58c7-124">0x80041006</span></span> | <span data-ttu-id="b58c7-125">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="b58c7-125">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b58c7-126">0</span><span class="sxs-lookup"><span data-stu-id="b58c7-126">0</span></span> | <span data-ttu-id="b58c7-127">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="b58c7-127">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="b58c7-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="b58c7-128">Remarks</span></span>

<span data-ttu-id="b58c7-129">Эта функция заключает в оболочку вызов метода [ивбемклассобжект::-Method](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) .</span><span class="sxs-lookup"><span data-stu-id="b58c7-129">This function wraps a call to the [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="b58c7-130">Управление Windows может установить указатель [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) на значение `null` , если метод не имеет параметров.</span><span class="sxs-lookup"><span data-stu-id="b58c7-130">Windows Management can set the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointer to `null` if the method has no in parameters.</span></span>

<span data-ttu-id="b58c7-131">В `ppInSignature` `IWbemClassObject` и `ppOutSignature` описывают параметры in и out соответственно как свойства в экземпляре системного класса [_Parameters](/windows/desktop/WmiSdk/--parameters).</span><span class="sxs-lookup"><span data-stu-id="b58c7-131">In `ppInSignature` and `ppOutSignature` describe in and out parameters, respectively, as properties in a `IWbemClassObject` instance of the system class [_Parameters](/windows/desktop/WmiSdk/--parameters).</span></span> <span data-ttu-id="b58c7-132">`ppInSignature` Свойства в `Param`имеют имя *n*, где *n* — это расположение параметра в сигнатуре метода (например `Param1`, `Param2`, и т. д.).</span><span class="sxs-lookup"><span data-stu-id="b58c7-132">The properties in `ppInSignature` are named `Param`*n*, where *n* is the position of the parameter in the method signature (such as `Param1`, `Param2`, etc.).</span></span> <span data-ttu-id="b58c7-133">Свойства в `ppOutSignature` также называются `Param` *n* `ReturnValue`, а возвращаемое значение называется.</span><span class="sxs-lookup"><span data-stu-id="b58c7-133">The properties in `ppOutSignature` are also named `Param`*n*, and the return value is named `ReturnValue`.</span></span> <span data-ttu-id="b58c7-134">Дополнительные сведения и пример см. в разделе [метод ивбемклассобжект::](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)Method.</span><span class="sxs-lookup"><span data-stu-id="b58c7-134">For more information and an example, see [IWbemClassObject::GetMethod method](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span></span>

## <a name="requirements"></a><span data-ttu-id="b58c7-135">Требования</span><span class="sxs-lookup"><span data-stu-id="b58c7-135">Requirements</span></span>

<span data-ttu-id="b58c7-136">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b58c7-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="b58c7-137">**Заголовок.** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="b58c7-137">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="b58c7-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b58c7-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b58c7-139">См. также</span><span class="sxs-lookup"><span data-stu-id="b58c7-139">See also</span></span>

- [<span data-ttu-id="b58c7-140">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="b58c7-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
