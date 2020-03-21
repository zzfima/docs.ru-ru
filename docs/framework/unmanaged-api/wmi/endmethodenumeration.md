---
title: Функция EndMethodEnumeration (Неуправляемая справка API)
description: Функция EndMethodEnumeration завершает последовательность перечисления метода.
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
ms.openlocfilehash: 63667d0668f905ded2aedd961be0d1831faf838c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175009"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="4fd19-103">Функция EndMethodEnumeration</span><span class="sxs-lookup"><span data-stu-id="4fd19-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="4fd19-104">Прекращает перечисление последовательности, начатой с вызова к [функции BeginMethodEnumeration.](beginmethodenumeration.md)</span><span class="sxs-lookup"><span data-stu-id="4fd19-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="4fd19-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4fd19-105">Syntax</span></span>  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```  

## <a name="parameters"></a><span data-ttu-id="4fd19-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4fd19-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="4fd19-107">(в) Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="4fd19-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="4fd19-108">(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="4fd19-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="4fd19-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4fd19-109">Return value</span></span>

<span data-ttu-id="4fd19-110">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="4fd19-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4fd19-111">Постоянно</span><span class="sxs-lookup"><span data-stu-id="4fd19-111">Constant</span></span>  |<span data-ttu-id="4fd19-112">Значение</span><span class="sxs-lookup"><span data-stu-id="4fd19-112">Value</span></span>  |<span data-ttu-id="4fd19-113">Описание</span><span class="sxs-lookup"><span data-stu-id="4fd19-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="4fd19-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="4fd19-114">0x8004101d</span></span> | <span data-ttu-id="4fd19-115">Произошла внутренняя ошибка.</span><span class="sxs-lookup"><span data-stu-id="4fd19-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="4fd19-116">0</span><span class="sxs-lookup"><span data-stu-id="4fd19-116">0</span></span> | <span data-ttu-id="4fd19-117">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="4fd19-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="4fd19-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="4fd19-118">Remarks</span></span>

<span data-ttu-id="4fd19-119">Эта функция завершает вызов [методом IWbemClassObject::EndMethodEnumeration.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration)</span><span class="sxs-lookup"><span data-stu-id="4fd19-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="4fd19-120">Вызывающее запускает последовательность перечисления с помощью [функции BeginMethodEnumeration,](beginmethodenumeration.md) `WBEM_S_NO_MORE_DATA`а затем вызывает [функцию NextMethod](nextmethod.md )до тех пор, пока метод не вернется.</span><span class="sxs-lookup"><span data-stu-id="4fd19-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="4fd19-121">Звонящее опционально завершает `EndMethodEnumeration`последовательность, позвонив.</span><span class="sxs-lookup"><span data-stu-id="4fd19-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="4fd19-122">Звонящее может досрочно прекратить перечисление, позвонив `EndMethodEnumeration` в любое время.</span><span class="sxs-lookup"><span data-stu-id="4fd19-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="4fd19-123">Требования</span><span class="sxs-lookup"><span data-stu-id="4fd19-123">Requirements</span></span>  
 <span data-ttu-id="4fd19-124">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fd19-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fd19-125">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4fd19-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4fd19-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4fd19-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fd19-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4fd19-127">See also</span></span>

- [<span data-ttu-id="4fd19-128">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="4fd19-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
