---
title: Функция GetObjectText (Неуправляемая ссылка на API)
description: Функция GetObjectText возвращает текстовую визуализацию объекта в синтаксисе MOF.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6881125760e0f1dc38e6b01917d5829edc95e3ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176790"
---
# <a name="getobjecttext-function"></a><span data-ttu-id="445e5-103">Функция GetObjectText</span><span class="sxs-lookup"><span data-stu-id="445e5-103">GetObjectText function</span></span>
<span data-ttu-id="445e5-104">Возвращает текстовую визуализацию объекта в синтаксисе Управляемого объекта (MOF).</span><span class="sxs-lookup"><span data-stu-id="445e5-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="445e5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="445e5-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
);
```  

## <a name="parameters"></a><span data-ttu-id="445e5-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="445e5-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="445e5-107">(в) Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="445e5-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="445e5-108">(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="445e5-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="445e5-109">(в) Обычно 0.</span><span class="sxs-lookup"><span data-stu-id="445e5-109">[in] Normally 0.</span></span> <span data-ttu-id="445e5-110">Если `WBEM_FLAG_NO_FLAVORS` (или 0x1) указан, квалификаторы включаются без распространения или информации о вкусе.</span><span class="sxs-lookup"><span data-stu-id="445e5-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

<span data-ttu-id="445e5-111">`pstrObjectText`(ваут) Указатель `null` на вход.</span><span class="sxs-lookup"><span data-stu-id="445e5-111">`pstrObjectText` [out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="445e5-112">В ответ недавно `BSTR` выделенное, содержащее синтаксис MOF, рендеризирующее объект.</span><span class="sxs-lookup"><span data-stu-id="445e5-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="445e5-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="445e5-113">Return value</span></span>

<span data-ttu-id="445e5-114">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="445e5-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="445e5-115">Постоянно</span><span class="sxs-lookup"><span data-stu-id="445e5-115">Constant</span></span>  |<span data-ttu-id="445e5-116">Значение</span><span class="sxs-lookup"><span data-stu-id="445e5-116">Value</span></span>  |<span data-ttu-id="445e5-117">Описание</span><span class="sxs-lookup"><span data-stu-id="445e5-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="445e5-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="445e5-118">0x80041001</span></span> | <span data-ttu-id="445e5-119">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="445e5-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="445e5-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="445e5-120">0x80041008</span></span> | <span data-ttu-id="445e5-121">Недействительный параметр.</span><span class="sxs-lookup"><span data-stu-id="445e5-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="445e5-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="445e5-122">0x80041006</span></span> | <span data-ttu-id="445e5-123">Недостаточно памяти для выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="445e5-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="445e5-124">0</span><span class="sxs-lookup"><span data-stu-id="445e5-124">0</span></span> | <span data-ttu-id="445e5-125">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="445e5-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="445e5-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="445e5-126">Remarks</span></span>

<span data-ttu-id="445e5-127">Эта функция завершает вызов методом [IWbemClassObject::GetObjectText.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext)</span><span class="sxs-lookup"><span data-stu-id="445e5-127">This function wraps a call to the [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) method.</span></span>

<span data-ttu-id="445e5-128">Ответный текст MOF не содержит всю информацию об объекте, но только достаточно информации для компилятора MOF, чтобы иметь возможность воссоздать исходный объект.</span><span class="sxs-lookup"><span data-stu-id="445e5-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="445e5-129">Например, не включены распространяемые квалификаторы или свойства родительского класса.</span><span class="sxs-lookup"><span data-stu-id="445e5-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="445e5-130">Для реконструкции текста параметров метода используется следующий алгоритм:</span><span class="sxs-lookup"><span data-stu-id="445e5-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="445e5-131">Параметры ресекризируются в порядке значений идентификатора.</span><span class="sxs-lookup"><span data-stu-id="445e5-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="445e5-132">Параметры, которые указаны как `[in]` и `[out]` объединены в единый параметр.</span><span class="sxs-lookup"><span data-stu-id="445e5-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>

<span data-ttu-id="445e5-133">`pstrObjectText`должен быть указателем `null` на то, когда функция называется; он не должен указывать на строку, действительную до вызова метода, потому что указатель не будет расположен.</span><span class="sxs-lookup"><span data-stu-id="445e5-133">`pstrObjectText` must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="445e5-134">Требования</span><span class="sxs-lookup"><span data-stu-id="445e5-134">Requirements</span></span>  
<span data-ttu-id="445e5-135">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="445e5-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="445e5-136">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="445e5-136">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="445e5-137">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="445e5-137">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="445e5-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="445e5-138">See also</span></span>

- [<span data-ttu-id="445e5-139">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="445e5-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
