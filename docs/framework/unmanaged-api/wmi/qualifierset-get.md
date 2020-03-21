---
title: QualifierSet_Get функция (неуправляемая справка API)
description: Функция QualifierSet_Get получает названный квалификатор.
ms.date: 11/06/2017
api_name:
- QualifierSet_Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Get
helpviewer_keywords:
- QualifierSet_Get function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 2f4e2d4518e01f3415b8f17ce5778dd98b2a45c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174892"
---
# <a name="qualifierset_get-function"></a><span data-ttu-id="9f436-103">Функция QualifierSet_Get</span><span class="sxs-lookup"><span data-stu-id="9f436-103">QualifierSet_Get function</span></span>
<span data-ttu-id="9f436-104">Получает указанный именованный квалификатор.</span><span class="sxs-lookup"><span data-stu-id="9f436-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="9f436-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f436-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Get (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor
);
```  

## <a name="parameters"></a><span data-ttu-id="9f436-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9f436-106">Parameters</span></span>

<span data-ttu-id="9f436-107">`vFunc`(в) Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="9f436-107">`vFunc` [in] This parameter is unused.</span></span>

<span data-ttu-id="9f436-108">`ptr`(в) Указатель на экземпляр [IWbemqualifierSet.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)</span><span class="sxs-lookup"><span data-stu-id="9f436-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="9f436-109">`wszName`(в) Имя квалификатора, значение которого запрашивается.</span><span class="sxs-lookup"><span data-stu-id="9f436-109">`wszName` [in] The name of the qualifier whose value is requested.</span></span>

<span data-ttu-id="9f436-110">`lFlags`(в) Защищены.</span><span class="sxs-lookup"><span data-stu-id="9f436-110">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="9f436-111">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="9f436-111">This parameter must be 0.</span></span>

<span data-ttu-id="9f436-112">`pVal`(ваут) В случае успеха правильный тип и значение для квалификатора.</span><span class="sxs-lookup"><span data-stu-id="9f436-112">`pVal` [out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="9f436-113">Если функция выходит `VARIANT` из строя, указанная `pVal` не изменяется.</span><span class="sxs-lookup"><span data-stu-id="9f436-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="9f436-114">Если этот `null`параметр, параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="9f436-114">If this parameter is `null`, the parameter is ignored.</span></span>

<span data-ttu-id="9f436-115">`plFlavor`(ваут) Указатель на LONG, который получает квалификатор вкусбитые биты для запрошенного квалификатора.</span><span class="sxs-lookup"><span data-stu-id="9f436-115">`plFlavor` [out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="9f436-116">Если информация о вкусе не `null`желательна, этот параметр может быть.</span><span class="sxs-lookup"><span data-stu-id="9f436-116">If flavor information is not desired, this parameter can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="9f436-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9f436-117">Return value</span></span>

<span data-ttu-id="9f436-118">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="9f436-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9f436-119">Постоянно</span><span class="sxs-lookup"><span data-stu-id="9f436-119">Constant</span></span>  |<span data-ttu-id="9f436-120">Значение</span><span class="sxs-lookup"><span data-stu-id="9f436-120">Value</span></span>  |<span data-ttu-id="9f436-121">Описание</span><span class="sxs-lookup"><span data-stu-id="9f436-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="9f436-122">0x80041008</span><span class="sxs-lookup"><span data-stu-id="9f436-122">0x80041008</span></span> | <span data-ttu-id="9f436-123">Недействительный параметр.</span><span class="sxs-lookup"><span data-stu-id="9f436-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="9f436-124">0x80041002</span><span class="sxs-lookup"><span data-stu-id="9f436-124">0x80041002</span></span> | <span data-ttu-id="9f436-125">Указанный квалификатор не существует.</span><span class="sxs-lookup"><span data-stu-id="9f436-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="9f436-126">0</span><span class="sxs-lookup"><span data-stu-id="9f436-126">0</span></span> | <span data-ttu-id="9f436-127">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="9f436-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="9f436-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="9f436-128">Remarks</span></span>

<span data-ttu-id="9f436-129">Эта функция обертывает вызов [iWbemqualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) метод.</span><span class="sxs-lookup"><span data-stu-id="9f436-129">This function wraps a call to the [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="9f436-130">Требования</span><span class="sxs-lookup"><span data-stu-id="9f436-130">Requirements</span></span>  
 <span data-ttu-id="9f436-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f436-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f436-132">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9f436-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="9f436-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9f436-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f436-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9f436-134">See also</span></span>

- [<span data-ttu-id="9f436-135">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="9f436-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
