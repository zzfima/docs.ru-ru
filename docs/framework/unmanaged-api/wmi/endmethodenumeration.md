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
ms.openlocfilehash: e7f29c365e9f6ba85f85ceb232f7af89446af2a1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213055"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="2e730-103">Функция EndMethodEnumeration</span><span class="sxs-lookup"><span data-stu-id="2e730-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="2e730-104">Завершает работу вызовом последовательности перечисления [функция BeginMethodEnumeration](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="2e730-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="2e730-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e730-105">Syntax</span></span>  
  
```  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="2e730-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e730-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="2e730-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="2e730-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="2e730-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="2e730-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="2e730-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2e730-109">Return value</span></span>

<span data-ttu-id="2e730-110">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="2e730-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="2e730-111">Константа</span><span class="sxs-lookup"><span data-stu-id="2e730-111">Constant</span></span>  |<span data-ttu-id="2e730-112">Значение</span><span class="sxs-lookup"><span data-stu-id="2e730-112">Value</span></span>  |<span data-ttu-id="2e730-113">Описание</span><span class="sxs-lookup"><span data-stu-id="2e730-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="2e730-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="2e730-114">0x8004101d</span></span> | <span data-ttu-id="2e730-115">Внутренняя ошибка.</span><span class="sxs-lookup"><span data-stu-id="2e730-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="2e730-116">0</span><span class="sxs-lookup"><span data-stu-id="2e730-116">0</span></span> | <span data-ttu-id="2e730-117">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="2e730-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="2e730-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="2e730-118">Remarks</span></span>

<span data-ttu-id="2e730-119">Эта функция создает оболочку для вызова [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) метод.</span><span class="sxs-lookup"><span data-stu-id="2e730-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="2e730-120">Вызывающий объект начинается в последовательности перечисления с помощью [функция BeginMethodEnumeration](beginmethodenumeration.md), а затем вызывает [NextMethod функция](nextmethod.md )до выполнения метода `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="2e730-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="2e730-121">Вызывающий объект (необязательно) завершает последовательность путем вызова `EndMethodEnumeration`.</span><span class="sxs-lookup"><span data-stu-id="2e730-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="2e730-122">Вызывающая сторона может завершить перечисление раньше путем вызова `EndMethodEnumeration` в любое время.</span><span class="sxs-lookup"><span data-stu-id="2e730-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="2e730-123">Требования</span><span class="sxs-lookup"><span data-stu-id="2e730-123">Requirements</span></span>  
 <span data-ttu-id="2e730-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e730-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e730-125">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="2e730-125">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="2e730-126">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2e730-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2e730-127">См. также</span><span class="sxs-lookup"><span data-stu-id="2e730-127">See also</span></span>

- [<span data-ttu-id="2e730-128">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="2e730-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
