---
title: Функция NextMethod (Справочник по неуправляемым API)
description: Функция NextMethod получает следующий метод в перечисление.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b3667f7371131a4c1394ba5ca619d1f605c89ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000185"
---
# <a name="nextmethod-function"></a><span data-ttu-id="5a4fe-103">Функция NextMethod</span><span class="sxs-lookup"><span data-stu-id="5a4fe-103">NextMethod function</span></span>
<span data-ttu-id="5a4fe-104">Извлекает следующий метод в перечисление, которое начинается с вызова [BeginMethodEnumeration](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="5a4fe-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="5a4fe-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a4fe-105">Syntax</span></span>  
  
```  
HRESULT NextMethod (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature   
); 
```  

## <a name="parameters"></a><span data-ttu-id="5a4fe-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5a4fe-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="5a4fe-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="5a4fe-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="5a4fe-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="5a4fe-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="5a4fe-109">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="5a4fe-109">[in] Reserved.</span></span> <span data-ttu-id="5a4fe-110">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="5a4fe-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="5a4fe-111">[out] Указатель на `null` до вызова метода.</span><span class="sxs-lookup"><span data-stu-id="5a4fe-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="5a4fe-112">Если функция возвращает, новый адрес `BSTR` , содержащий имя метода.</span><span class="sxs-lookup"><span data-stu-id="5a4fe-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span> 

`ppSignatureIn`  
<span data-ttu-id="5a4fe-113">[out] Указатель, получающий указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , содержащий `in` параметры метода.</span><span class="sxs-lookup"><span data-stu-id="5a4fe-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span> 

`ppSignatureOut`  
<span data-ttu-id="5a4fe-114">[out] Указатель, получающий указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , содержащий `out` параметры метода.</span><span class="sxs-lookup"><span data-stu-id="5a4fe-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span> 

## <a name="return-value"></a><span data-ttu-id="5a4fe-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5a4fe-115">Return value</span></span>

<span data-ttu-id="5a4fe-116">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="5a4fe-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5a4fe-117">Константа</span><span class="sxs-lookup"><span data-stu-id="5a4fe-117">Constant</span></span>  |<span data-ttu-id="5a4fe-118">Значение</span><span class="sxs-lookup"><span data-stu-id="5a4fe-118">Value</span></span>  |<span data-ttu-id="5a4fe-119">Описание</span><span class="sxs-lookup"><span data-stu-id="5a4fe-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="5a4fe-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="5a4fe-120">0x8004101d</span></span> | <span data-ttu-id="5a4fe-121">Возникла не вызывался метод [ `BeginEnumeration` ](beginenumeration.md) функции.</span><span class="sxs-lookup"><span data-stu-id="5a4fe-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="5a4fe-122">0</span><span class="sxs-lookup"><span data-stu-id="5a4fe-122">0</span></span> | <span data-ttu-id="5a4fe-123">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="5a4fe-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="5a4fe-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="5a4fe-124">0x40005</span></span> | <span data-ttu-id="5a4fe-125">Нет дополнительных свойств в перечислении.</span><span class="sxs-lookup"><span data-stu-id="5a4fe-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="5a4fe-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="5a4fe-126">Remarks</span></span>

<span data-ttu-id="5a4fe-127">Эта функция создает оболочку для вызова [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) метод.</span><span class="sxs-lookup"><span data-stu-id="5a4fe-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="5a4fe-128">Вызывающий объект начинается последовательность перечисления путем вызова метода [BeginMethodEnumeration](beginmethodenumeration.md) функции, а затем вызывает функцию [NextMethod] до возврата функции `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="5a4fe-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="5a4fe-129">При необходимости, вызывающий объект завершает последовательность путем вызова [EndMethodEnumeration](endmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="5a4fe-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="5a4fe-130">Вызывающая сторона может завершить перечисление раньше, вызвав [EndMethodEnumeration](endmethodenumeration.md) в любое время.</span><span class="sxs-lookup"><span data-stu-id="5a4fe-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="5a4fe-131">Пример</span><span class="sxs-lookup"><span data-stu-id="5a4fe-131">Example</span></span>

<span data-ttu-id="5a4fe-132">Пример C++, см. в разделе [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) метод.</span><span class="sxs-lookup"><span data-stu-id="5a4fe-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="5a4fe-133">Требования</span><span class="sxs-lookup"><span data-stu-id="5a4fe-133">Requirements</span></span>  
 <span data-ttu-id="5a4fe-134">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a4fe-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a4fe-135">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="5a4fe-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="5a4fe-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5a4fe-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a4fe-137">См. также</span><span class="sxs-lookup"><span data-stu-id="5a4fe-137">See also</span></span>

- [<span data-ttu-id="5a4fe-138">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="5a4fe-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
