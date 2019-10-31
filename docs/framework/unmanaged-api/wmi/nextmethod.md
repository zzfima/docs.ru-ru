---
title: Функция Некстмесод (Справочник по неуправляемым API)
description: Функция Некстмесод извлекает следующий метод в перечислении.
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
ms.openlocfilehash: 1c20fe5b4a081bd41f51365a36ab5f8f8cfb71ed
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127363"
---
# <a name="nextmethod-function"></a><span data-ttu-id="83eeb-103">Функция Некстмесод</span><span class="sxs-lookup"><span data-stu-id="83eeb-103">NextMethod function</span></span>
<span data-ttu-id="83eeb-104">Извлекает следующий метод в перечислении, который начинается с вызова [бегинмесоденумератион](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="83eeb-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="83eeb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83eeb-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="83eeb-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="83eeb-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="83eeb-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="83eeb-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="83eeb-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="83eeb-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="83eeb-109">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="83eeb-109">[in] Reserved.</span></span> <span data-ttu-id="83eeb-110">Этот параметр должен иметь значение 0.</span><span class="sxs-lookup"><span data-stu-id="83eeb-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="83eeb-111">заполняет Указатель, указывающий на `null` до вызова.</span><span class="sxs-lookup"><span data-stu-id="83eeb-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="83eeb-112">Когда функция возвращает, адрес нового `BSTR`, который содержит имя метода.</span><span class="sxs-lookup"><span data-stu-id="83eeb-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span> 

`ppSignatureIn`  
<span data-ttu-id="83eeb-113">заполняет Указатель, получающий указатель на объект [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , содержащий параметры `in` для метода.</span><span class="sxs-lookup"><span data-stu-id="83eeb-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span> 

`ppSignatureOut`  
<span data-ttu-id="83eeb-114">заполняет Указатель, получающий указатель на объект [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , содержащий параметры `out` для метода.</span><span class="sxs-lookup"><span data-stu-id="83eeb-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span> 

## <a name="return-value"></a><span data-ttu-id="83eeb-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="83eeb-115">Return value</span></span>

<span data-ttu-id="83eeb-116">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="83eeb-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="83eeb-117">Константа</span><span class="sxs-lookup"><span data-stu-id="83eeb-117">Constant</span></span>  |<span data-ttu-id="83eeb-118">значения</span><span class="sxs-lookup"><span data-stu-id="83eeb-118">Value</span></span>  |<span data-ttu-id="83eeb-119">Описание</span><span class="sxs-lookup"><span data-stu-id="83eeb-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="83eeb-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="83eeb-120">0x8004101d</span></span> | <span data-ttu-id="83eeb-121">Вызов функции [`BeginEnumeration`](beginenumeration.md) не выполнялся.</span><span class="sxs-lookup"><span data-stu-id="83eeb-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="83eeb-122">0</span><span class="sxs-lookup"><span data-stu-id="83eeb-122">0</span></span> | <span data-ttu-id="83eeb-123">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="83eeb-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="83eeb-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="83eeb-124">0x40005</span></span> | <span data-ttu-id="83eeb-125">В перечислении больше нет свойств.</span><span class="sxs-lookup"><span data-stu-id="83eeb-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="83eeb-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="83eeb-126">Remarks</span></span>

<span data-ttu-id="83eeb-127">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: некстмесод](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) .</span><span class="sxs-lookup"><span data-stu-id="83eeb-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="83eeb-128">Вызывающий объект начинает последовательность перечисления, вызывая функцию [бегинмесоденумератион](beginmethodenumeration.md) , а затем вызывает функцию [некстмесод], пока функция не вернет `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="83eeb-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="83eeb-129">При необходимости вызывающий объект завершает последовательность путем вызова [ендмесоденумератион](endmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="83eeb-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="83eeb-130">Вызывающий объект может завершить перечисление раньше, вызвав [ендмесоденумератион](endmethodenumeration.md) в любое время.</span><span class="sxs-lookup"><span data-stu-id="83eeb-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="83eeb-131">Пример</span><span class="sxs-lookup"><span data-stu-id="83eeb-131">Example</span></span>

<span data-ttu-id="83eeb-132">C++ Пример см. в описании метода [Ивбемклассобжект:: некстмесод](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) .</span><span class="sxs-lookup"><span data-stu-id="83eeb-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="83eeb-133">Требования</span><span class="sxs-lookup"><span data-stu-id="83eeb-133">Requirements</span></span>  
 <span data-ttu-id="83eeb-134">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83eeb-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83eeb-135">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="83eeb-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="83eeb-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="83eeb-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83eeb-137">См. также</span><span class="sxs-lookup"><span data-stu-id="83eeb-137">See also</span></span>

- [<span data-ttu-id="83eeb-138">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="83eeb-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
