---
title: Функция EndMethodEnumeration (Справочник по неуправляемым API)
description: Функция EndMethodEnumeration завершает последовательность метод перечисления.
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
ms.openlocfilehash: d09a2ee278dba7e711891bc6d72043bb3a499dd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="d14a5-103">Функция EndMethodEnumeration</span><span class="sxs-lookup"><span data-stu-id="d14a5-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="d14a5-104">Завершает последовательность перечисления запущен с помощью вызова [BeginMethodEnumeration функция](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="d14a5-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="d14a5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d14a5-105">Syntax</span></span>  
  
```  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="d14a5-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d14a5-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="d14a5-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="d14a5-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="d14a5-108">[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d14a5-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="d14a5-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d14a5-109">Return value</span></span>

<span data-ttu-id="d14a5-110">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="d14a5-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d14a5-111">Константа</span><span class="sxs-lookup"><span data-stu-id="d14a5-111">Constant</span></span>  |<span data-ttu-id="d14a5-112">Значение</span><span class="sxs-lookup"><span data-stu-id="d14a5-112">Value</span></span>  |<span data-ttu-id="d14a5-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d14a5-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="d14a5-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="d14a5-114">0x8004101d</span></span> | <span data-ttu-id="d14a5-115">Произошла внутренняя ошибка.</span><span class="sxs-lookup"><span data-stu-id="d14a5-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="d14a5-116">0</span><span class="sxs-lookup"><span data-stu-id="d14a5-116">0</span></span> | <span data-ttu-id="d14a5-117">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="d14a5-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="d14a5-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="d14a5-118">Remarks</span></span>

<span data-ttu-id="d14a5-119">Эта функция создает оболочку для вызова [IWbemClassObject::EndMethodEnumeration](https://msdn.microsoft.com/library/aa391441(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="d14a5-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](https://msdn.microsoft.com/library/aa391441(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="d14a5-120">Вызывающий объект начинает последовательность перечисления с помощью [функция BeginMethodEnumeration](beginmethodenumeration.md)и затем вызывает [функция NextMethod](nextmethod.md )до возвращения методом `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="d14a5-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="d14a5-121">Вызывающий объект при необходимости завершения последовательности путем вызова `EndMethodEnumeration`.</span><span class="sxs-lookup"><span data-stu-id="d14a5-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="d14a5-122">Вызывающий объект может завершить перечисление раньше путем вызова `EndMethodEnumeration` в любое время.</span><span class="sxs-lookup"><span data-stu-id="d14a5-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="d14a5-123">Требования</span><span class="sxs-lookup"><span data-stu-id="d14a5-123">Requirements</span></span>  
 <span data-ttu-id="d14a5-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d14a5-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d14a5-125">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d14a5-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="d14a5-126">**Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d14a5-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d14a5-127">См. также</span><span class="sxs-lookup"><span data-stu-id="d14a5-127">See also</span></span>  
[<span data-ttu-id="d14a5-128">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="d14a5-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
