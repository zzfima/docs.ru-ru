---
title: QualifierSet_Next функция (Неуправляемая справка API)
description: Функция QualifierSet_Next получает следующий квалификатор в перечислении.
ms.date: 11/06/2017
api_name:
- QualifierSet_Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Next
helpviewer_keywords:
- QualifierSet_Next function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: d3702426bc409d601ccfc6b7a8e93e8d9729c64e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174879"
---
# <a name="qualifierset_next-function"></a><span data-ttu-id="3c1f9-103">Функция QualifierSet_Next</span><span class="sxs-lookup"><span data-stu-id="3c1f9-103">QualifierSet_Next function</span></span>
<span data-ttu-id="3c1f9-104">Получает следующий квалификатор в перечислении, начатом вызовом функции [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="3c1f9-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="3c1f9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c1f9-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Next (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor
);
```  

## <a name="parameters"></a><span data-ttu-id="3c1f9-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3c1f9-106">Parameters</span></span>

<span data-ttu-id="3c1f9-107">`vFunc`(в) Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="3c1f9-107">`vFunc` [in] This parameter is unused.</span></span>

<span data-ttu-id="3c1f9-108">`ptr`(в) Указатель на экземпляр [IWbemqualifierSet.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)</span><span class="sxs-lookup"><span data-stu-id="3c1f9-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="3c1f9-109">`lFlags`(в) Защищены.</span><span class="sxs-lookup"><span data-stu-id="3c1f9-109">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="3c1f9-110">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="3c1f9-110">This parameter must be 0.</span></span>

<span data-ttu-id="3c1f9-111">`pstrName`(ваут) Название квалификатора.</span><span class="sxs-lookup"><span data-stu-id="3c1f9-111">`pstrName` [out] The name of the qualifier.</span></span> <span data-ttu-id="3c1f9-112">Если `null`этот параметр игнорируется; в `pstrName` противном случае, `BSTR` не должны указывать на действительный или утечка памяти происходит.</span><span class="sxs-lookup"><span data-stu-id="3c1f9-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="3c1f9-113">Если не нулевые, функция `BSTR` всегда выделяет `WBEM_S_NO_ERROR`новый, когда он возвращается.</span><span class="sxs-lookup"><span data-stu-id="3c1f9-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

<span data-ttu-id="3c1f9-114">`pVal`(ваут) В случае успеха значение для квалификатора.</span><span class="sxs-lookup"><span data-stu-id="3c1f9-114">`pVal` [out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="3c1f9-115">Если функция выходит `VARIANT` из строя, указанная `pVal` не изменяется.</span><span class="sxs-lookup"><span data-stu-id="3c1f9-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="3c1f9-116">Если этот `null`параметр, параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="3c1f9-116">If this parameter is `null`, the parameter is ignored.</span></span>

<span data-ttu-id="3c1f9-117">`plFlavor`(ваут) Указатель на LONG, который получает квалификационный вкус.</span><span class="sxs-lookup"><span data-stu-id="3c1f9-117">`plFlavor` [out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="3c1f9-118">Если информация о вкусе не `null`желательна, этот параметр может быть.</span><span class="sxs-lookup"><span data-stu-id="3c1f9-118">If flavor information is not desired, this parameter can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="3c1f9-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3c1f9-119">Return value</span></span>

<span data-ttu-id="3c1f9-120">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="3c1f9-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3c1f9-121">Постоянно</span><span class="sxs-lookup"><span data-stu-id="3c1f9-121">Constant</span></span>  |<span data-ttu-id="3c1f9-122">Значение</span><span class="sxs-lookup"><span data-stu-id="3c1f9-122">Value</span></span>  |<span data-ttu-id="3c1f9-123">Описание</span><span class="sxs-lookup"><span data-stu-id="3c1f9-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3c1f9-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3c1f9-124">0x80041008</span></span> | <span data-ttu-id="3c1f9-125">Недействительный параметр.</span><span class="sxs-lookup"><span data-stu-id="3c1f9-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="3c1f9-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="3c1f9-126">0x8004101d</span></span> | <span data-ttu-id="3c1f9-127">Звонивший не звонил [QualifierSet_BeginEnumeration.](qualifierset-beginenumeration.md)</span><span class="sxs-lookup"><span data-stu-id="3c1f9-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="3c1f9-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="3c1f9-128">0x80041006</span></span> | <span data-ttu-id="3c1f9-129">Недостаточно памяти доступно для начала нового перечисления.</span><span class="sxs-lookup"><span data-stu-id="3c1f9-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="3c1f9-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="3c1f9-130">0x40005</span></span> | <span data-ttu-id="3c1f9-131">В перечислении больше не осталось квалификаторов.</span><span class="sxs-lookup"><span data-stu-id="3c1f9-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="3c1f9-132">0</span><span class="sxs-lookup"><span data-stu-id="3c1f9-132">0</span></span> | <span data-ttu-id="3c1f9-133">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="3c1f9-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="3c1f9-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="3c1f9-134">Remarks</span></span>

<span data-ttu-id="3c1f9-135">Эта функция завершает вызов [IWbemqualifierSet::Следующий](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) метод.</span><span class="sxs-lookup"><span data-stu-id="3c1f9-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="3c1f9-136">Вы называете функцию `QualifierSet_Next` повторно, чтобы перечислить все `WBEM_S_NO_MORE_DATA`квалификаторы до возвращения функции.</span><span class="sxs-lookup"><span data-stu-id="3c1f9-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="3c1f9-137">Чтобы досрочно завершить перечисление, позвоните [в функцию QualifierSet_EndEnumeration.](qualifierset-endenumeration.md)</span><span class="sxs-lookup"><span data-stu-id="3c1f9-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="3c1f9-138">Порядок квалификаторов, возвращенных во время перечисления, не определен.</span><span class="sxs-lookup"><span data-stu-id="3c1f9-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="3c1f9-139">Требования</span><span class="sxs-lookup"><span data-stu-id="3c1f9-139">Requirements</span></span>  
 <span data-ttu-id="3c1f9-140">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c1f9-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c1f9-141">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3c1f9-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3c1f9-142">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3c1f9-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c1f9-143">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3c1f9-143">See also</span></span>

- [<span data-ttu-id="3c1f9-144">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="3c1f9-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
