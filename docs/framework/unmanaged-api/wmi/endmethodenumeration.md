---
title: Функция EndMethodEnumeration (Справочник по неуправляемым API)
description: Функция EndMethodEnumeration завершает метод последовательности перечисления.
ms.date: 11/06/2017
api_name:
- EndMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndMethodEnumeration
helpviewer_keywords:
- EndMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f62ea692c055b0537394ad5e16501d4162faef12
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746828"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="da1cc-103">Функция EndMethodEnumeration</span><span class="sxs-lookup"><span data-stu-id="da1cc-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="da1cc-104">Завершает работу вызовом последовательности перечисления [функция BeginMethodEnumeration](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="da1cc-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="da1cc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da1cc-105">Syntax</span></span>  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="da1cc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="da1cc-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="da1cc-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="da1cc-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="da1cc-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="da1cc-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="da1cc-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="da1cc-109">Return value</span></span>

<span data-ttu-id="da1cc-110">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="da1cc-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="da1cc-111">Константа</span><span class="sxs-lookup"><span data-stu-id="da1cc-111">Constant</span></span>  |<span data-ttu-id="da1cc-112">Значение</span><span class="sxs-lookup"><span data-stu-id="da1cc-112">Value</span></span>  |<span data-ttu-id="da1cc-113">Описание</span><span class="sxs-lookup"><span data-stu-id="da1cc-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="da1cc-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="da1cc-114">0x8004101d</span></span> | <span data-ttu-id="da1cc-115">Внутренняя ошибка.</span><span class="sxs-lookup"><span data-stu-id="da1cc-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="da1cc-116">0</span><span class="sxs-lookup"><span data-stu-id="da1cc-116">0</span></span> | <span data-ttu-id="da1cc-117">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="da1cc-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="da1cc-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="da1cc-118">Remarks</span></span>

<span data-ttu-id="da1cc-119">Эта функция создает оболочку для вызова [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) метод.</span><span class="sxs-lookup"><span data-stu-id="da1cc-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="da1cc-120">Вызывающий объект начинается в последовательности перечисления с помощью [функция BeginMethodEnumeration](beginmethodenumeration.md), а затем вызывает [NextMethod функция](nextmethod.md )до выполнения метода `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="da1cc-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="da1cc-121">Вызывающий объект (необязательно) завершает последовательность путем вызова `EndMethodEnumeration`.</span><span class="sxs-lookup"><span data-stu-id="da1cc-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="da1cc-122">Вызывающая сторона может завершить перечисление раньше путем вызова `EndMethodEnumeration` в любое время.</span><span class="sxs-lookup"><span data-stu-id="da1cc-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="da1cc-123">Требования</span><span class="sxs-lookup"><span data-stu-id="da1cc-123">Requirements</span></span>  
 <span data-ttu-id="da1cc-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da1cc-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da1cc-125">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="da1cc-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="da1cc-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="da1cc-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da1cc-127">См. также</span><span class="sxs-lookup"><span data-stu-id="da1cc-127">See also</span></span>

- [<span data-ttu-id="da1cc-128">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="da1cc-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
