---
title: Функция NextMethod (Неуправляемая ссылка API)
description: Функция NextMethod извлекает следующий метод в перечислении.
ms.date: 11/06/2017
api_name:
- NextMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- NextMethod
helpviewer_keywords:
- NextMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 36acd6135110a8865bd8efdda628c352c01b4f26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174931"
---
# <a name="nextmethod-function"></a><span data-ttu-id="f503a-103">Функция NextMethod</span><span class="sxs-lookup"><span data-stu-id="f503a-103">NextMethod function</span></span>
<span data-ttu-id="f503a-104">Извлекает следующий метод в перечислении, который начинается с вызова [beginMethodEnumeration.](beginmethodenumeration.md)</span><span class="sxs-lookup"><span data-stu-id="f503a-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f503a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f503a-105">Syntax</span></span>  
  
```cpp  
HRESULT NextMethod (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
);
```  

## <a name="parameters"></a><span data-ttu-id="f503a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f503a-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f503a-107">(в) Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="f503a-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f503a-108">(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="f503a-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="f503a-109">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="f503a-109">[in] Reserved.</span></span> <span data-ttu-id="f503a-110">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="f503a-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="f503a-111">(ваут) Указатель, который `null` указывает на до вызова.</span><span class="sxs-lookup"><span data-stu-id="f503a-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="f503a-112">Когда функция возвращается, адрес `BSTR` нового, который содержит имя метода.</span><span class="sxs-lookup"><span data-stu-id="f503a-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span>

`ppSignatureIn`  
<span data-ttu-id="f503a-113">(ваут) Указатель, который получает указатель на [IWbemClassObject,](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) содержащий `in` параметры для метода.</span><span class="sxs-lookup"><span data-stu-id="f503a-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span>

`ppSignatureOut`  
<span data-ttu-id="f503a-114">(ваут) Указатель, который получает указатель на [IWbemClassObject,](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) содержащий `out` параметры для метода.</span><span class="sxs-lookup"><span data-stu-id="f503a-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="f503a-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f503a-115">Return value</span></span>

<span data-ttu-id="f503a-116">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="f503a-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f503a-117">Постоянно</span><span class="sxs-lookup"><span data-stu-id="f503a-117">Constant</span></span>  |<span data-ttu-id="f503a-118">Значение</span><span class="sxs-lookup"><span data-stu-id="f503a-118">Value</span></span>  |<span data-ttu-id="f503a-119">Описание</span><span class="sxs-lookup"><span data-stu-id="f503a-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="f503a-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="f503a-120">0x8004101d</span></span> | <span data-ttu-id="f503a-121">Не было никакого [`BeginEnumeration`](beginenumeration.md) вызова к функции.</span><span class="sxs-lookup"><span data-stu-id="f503a-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="f503a-122">0</span><span class="sxs-lookup"><span data-stu-id="f503a-122">0</span></span> | <span data-ttu-id="f503a-123">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="f503a-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="f503a-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="f503a-124">0x40005</span></span> | <span data-ttu-id="f503a-125">В перечислении больше нет свойств.</span><span class="sxs-lookup"><span data-stu-id="f503a-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="f503a-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="f503a-126">Remarks</span></span>

<span data-ttu-id="f503a-127">Эта функция завершает вызов методом [IWbemClassObject::NextMethod.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod)</span><span class="sxs-lookup"><span data-stu-id="f503a-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="f503a-128">Вызывающий абонент начинает последовательность перечисления, вызывая функцию [BeginMethodEnumeration,](beginmethodenumeration.md) а затем вызывает `WBEM_S_NO_MORE_DATA`функцию «NextMethod» до тех пор, пока функция не вернется.</span><span class="sxs-lookup"><span data-stu-id="f503a-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="f503a-129">Дополнительно абонент завершает последовательность, позвонив [в EndMethodEnumeration.](endmethodenumeration.md)</span><span class="sxs-lookup"><span data-stu-id="f503a-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="f503a-130">Звонящее может досрочно завершить перечисление, позвонив в [EndMethodEnumeration](endmethodenumeration.md) в любое время.</span><span class="sxs-lookup"><span data-stu-id="f503a-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="f503a-131">Пример</span><span class="sxs-lookup"><span data-stu-id="f503a-131">Example</span></span>

<span data-ttu-id="f503a-132">На примере СЗ см. [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod)</span><span class="sxs-lookup"><span data-stu-id="f503a-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="f503a-133">Требования</span><span class="sxs-lookup"><span data-stu-id="f503a-133">Requirements</span></span>  
 <span data-ttu-id="f503a-134">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f503a-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f503a-135">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f503a-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f503a-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f503a-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f503a-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f503a-137">See also</span></span>

- [<span data-ttu-id="f503a-138">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="f503a-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
