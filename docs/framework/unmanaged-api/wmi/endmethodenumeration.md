---
title: "Функция EndMethodEnumeration (Справочник по неуправляемым API)"
description: "Функция EndMethodEnumeration завершает последовательность метод перечисления."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: EndMethodEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: EndMethodEnumeration
helpviewer_keywords: EndMethodEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1b768292811a752e7a319f853ca8eff85f1bb08
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="a8f6e-103">Функция EndMethodEnumeration</span><span class="sxs-lookup"><span data-stu-id="a8f6e-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="a8f6e-104">Завершает последовательность перечисления запущен с помощью вызова [BeginMethodEnumeration функция](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="a8f6e-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="a8f6e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8f6e-105">Syntax</span></span>  
  
```  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="a8f6e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a8f6e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="a8f6e-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="a8f6e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="a8f6e-108">[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a8f6e-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="a8f6e-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a8f6e-109">Return value</span></span>

<span data-ttu-id="a8f6e-110">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="a8f6e-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a8f6e-111">Константа</span><span class="sxs-lookup"><span data-stu-id="a8f6e-111">Constant</span></span>  |<span data-ttu-id="a8f6e-112">Значение</span><span class="sxs-lookup"><span data-stu-id="a8f6e-112">Value</span></span>  |<span data-ttu-id="a8f6e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a8f6e-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="a8f6e-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="a8f6e-114">0x8004101d</span></span> | <span data-ttu-id="a8f6e-115">Произошла внутренняя ошибка.</span><span class="sxs-lookup"><span data-stu-id="a8f6e-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="a8f6e-116">0</span><span class="sxs-lookup"><span data-stu-id="a8f6e-116">0</span></span> | <span data-ttu-id="a8f6e-117">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="a8f6e-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="a8f6e-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="a8f6e-118">Remarks</span></span>

<span data-ttu-id="a8f6e-119">Эта функция создает оболочку для вызова [IWbemClassObject::EndMethodEnumeration](https://msdn.microsoft.com/library/aa391441(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="a8f6e-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](https://msdn.microsoft.com/library/aa391441(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="a8f6e-120">Вызывающий объект начинает последовательность перечисления с помощью [функция BeginMethodEnumeration](beginmethodenumeration.md)и затем вызывает [функция NextMethod](nextmethod.md )до возвращения методом `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="a8f6e-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="a8f6e-121">Вызывающий объект при необходимости завершения последовательности путем вызова `EndMethodEnumeration`.</span><span class="sxs-lookup"><span data-stu-id="a8f6e-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="a8f6e-122">Вызывающий объект может завершить перечисление раньше путем вызова `EndMethodEnumeration` в любое время.</span><span class="sxs-lookup"><span data-stu-id="a8f6e-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="a8f6e-123">Требования</span><span class="sxs-lookup"><span data-stu-id="a8f6e-123">Requirements</span></span>  
 <span data-ttu-id="a8f6e-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8f6e-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8f6e-125">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="a8f6e-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="a8f6e-126">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a8f6e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8f6e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="a8f6e-127">See also</span></span>  
[<span data-ttu-id="a8f6e-128">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="a8f6e-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
