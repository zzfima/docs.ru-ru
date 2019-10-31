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
ms.openlocfilehash: 48986f5ff1cbbb45840ec1a059aa86711848d717
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102587"
---
# <a name="getmethod-function"></a><span data-ttu-id="a8da2-103">Функция GetMethod</span><span class="sxs-lookup"><span data-stu-id="a8da2-103">GetMethod function</span></span>

<span data-ttu-id="a8da2-104">Получает сведения об указанном методе.</span><span class="sxs-lookup"><span data-stu-id="a8da2-104">Retrieves information about the specified method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="a8da2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8da2-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="a8da2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a8da2-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="a8da2-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="a8da2-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="a8da2-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="a8da2-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="a8da2-109">окне Имя метода.</span><span class="sxs-lookup"><span data-stu-id="a8da2-109">[in] The method name.</span></span> <span data-ttu-id="a8da2-110">Этот параметр не может быть `null` и должен указывать на допустимый `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="a8da2-110">This parameter cannot be `null` and must point to a valid `LPCWSTR`.</span></span>

`lFlags`\
<span data-ttu-id="a8da2-111">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="a8da2-111">[in] Reserved.</span></span> <span data-ttu-id="a8da2-112">Этот параметр должен иметь значение 0.</span><span class="sxs-lookup"><span data-stu-id="a8da2-112">This parameter must be 0.</span></span>

`ppInSignature`\
<span data-ttu-id="a8da2-113">заполняет Указатель на адрес экземпляра [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , который описывает входные параметры метода.</span><span class="sxs-lookup"><span data-stu-id="a8da2-113">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the in parameters to the method.</span></span> <span data-ttu-id="a8da2-114">Этот параметр пропускается, если он имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="a8da2-114">This parameter is ignored if it is set to `null`.</span></span>

`ppOutSignature`\
<span data-ttu-id="a8da2-115">заполняет Указатель на адрес экземпляра [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , который описывает выходные параметры метода.</span><span class="sxs-lookup"><span data-stu-id="a8da2-115">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the out parameters to the method.</span></span> <span data-ttu-id="a8da2-116">Этот параметр пропускается, если он имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="a8da2-116">This parameter is ignored if it is set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="a8da2-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a8da2-117">Return value</span></span>

<span data-ttu-id="a8da2-118">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="a8da2-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a8da2-119">Константа</span><span class="sxs-lookup"><span data-stu-id="a8da2-119">Constant</span></span>  |<span data-ttu-id="a8da2-120">значения</span><span class="sxs-lookup"><span data-stu-id="a8da2-120">Value</span></span>  |<span data-ttu-id="a8da2-121">Описание</span><span class="sxs-lookup"><span data-stu-id="a8da2-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="a8da2-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="a8da2-122">0x80041002</span></span> | <span data-ttu-id="a8da2-123">Указанное свойство не найдено.</span><span class="sxs-lookup"><span data-stu-id="a8da2-123">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="a8da2-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="a8da2-124">0x80041006</span></span> | <span data-ttu-id="a8da2-125">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="a8da2-125">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="a8da2-126">0</span><span class="sxs-lookup"><span data-stu-id="a8da2-126">0</span></span> | <span data-ttu-id="a8da2-127">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="a8da2-127">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="a8da2-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="a8da2-128">Remarks</span></span>

<span data-ttu-id="a8da2-129">Эта функция заключает в оболочку вызов метода [ивбемклассобжект::-Method](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) .</span><span class="sxs-lookup"><span data-stu-id="a8da2-129">This function wraps a call to the [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="a8da2-130">Система управления Windows может установить указатель [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) на `null`, если метод не имеет параметров.</span><span class="sxs-lookup"><span data-stu-id="a8da2-130">Windows Management can set the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointer to `null` if the method has no in parameters.</span></span>

<span data-ttu-id="a8da2-131">В `ppInSignature` и `ppOutSignature` описать параметры in и out соответственно как свойства в экземпляре `IWbemClassObject` класса System [_Parameters](/windows/desktop/WmiSdk/--parameters).</span><span class="sxs-lookup"><span data-stu-id="a8da2-131">In `ppInSignature` and `ppOutSignature` describe in and out parameters, respectively, as properties in a `IWbemClassObject` instance of the system class [_Parameters](/windows/desktop/WmiSdk/--parameters).</span></span> <span data-ttu-id="a8da2-132">Свойства в `ppInSignature` именуются `Param`*n*, где *n* — это расположение параметра в сигнатуре метода (например, `Param1`, `Param2`и т. д.).</span><span class="sxs-lookup"><span data-stu-id="a8da2-132">The properties in `ppInSignature` are named `Param`*n*, where *n* is the position of the parameter in the method signature (such as `Param1`, `Param2`, etc.).</span></span> <span data-ttu-id="a8da2-133">Свойства в `ppOutSignature` также называются `Param`*n*, а возвращаемое значение называется `ReturnValue`.</span><span class="sxs-lookup"><span data-stu-id="a8da2-133">The properties in `ppOutSignature` are also named `Param`*n*, and the return value is named `ReturnValue`.</span></span> <span data-ttu-id="a8da2-134">Дополнительные сведения и пример см. в разделе [метод ивбемклассобжект::](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)Method.</span><span class="sxs-lookup"><span data-stu-id="a8da2-134">For more information and an example, see [IWbemClassObject::GetMethod method](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span></span>

## <a name="requirements"></a><span data-ttu-id="a8da2-135">Требования</span><span class="sxs-lookup"><span data-stu-id="a8da2-135">Requirements</span></span>

<span data-ttu-id="a8da2-136">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8da2-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="a8da2-137">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="a8da2-137">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="a8da2-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a8da2-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a8da2-139">См. также</span><span class="sxs-lookup"><span data-stu-id="a8da2-139">See also</span></span>

- [<span data-ttu-id="a8da2-140">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="a8da2-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
