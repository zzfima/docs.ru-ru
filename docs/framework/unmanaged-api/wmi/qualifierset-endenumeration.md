---
title: функция QualifierSet_EndEnumeration (неуправляемая справка API)
description: Функция QualifierSet_EndEnumeration завершает перечисление.
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: c606580ff2e02c5659c14b134b1a17a65651952b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176751"
---
# <a name="qualifierset_endenumeration-function"></a><span data-ttu-id="98446-103">Функция QualifierSet_EndEnumeration</span><span class="sxs-lookup"><span data-stu-id="98446-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="98446-104">Прекращает перечисление, начатое с вызова на [функцию QualifierSet_BeginEnumeration.](qualifierset-beginenumeration.md)</span><span class="sxs-lookup"><span data-stu-id="98446-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="98446-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98446-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr
);
```  

## <a name="parameters"></a><span data-ttu-id="98446-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="98446-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="98446-107">(в) Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="98446-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="98446-108">`ptr`(в) Указатель на экземпляр [IWbemqualifierSet.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)</span><span class="sxs-lookup"><span data-stu-id="98446-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="98446-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="98446-109">Return value</span></span>

<span data-ttu-id="98446-110">Следующее значение, возвращенное этой функцией, определяется в файле заголовка *WbemCli.h* или вы можете определить его как константу в коде:</span><span class="sxs-lookup"><span data-stu-id="98446-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="98446-111">Постоянно</span><span class="sxs-lookup"><span data-stu-id="98446-111">Constant</span></span>  |<span data-ttu-id="98446-112">Значение</span><span class="sxs-lookup"><span data-stu-id="98446-112">Value</span></span>  |<span data-ttu-id="98446-113">Описание</span><span class="sxs-lookup"><span data-stu-id="98446-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="98446-114">0</span><span class="sxs-lookup"><span data-stu-id="98446-114">0</span></span> | <span data-ttu-id="98446-115">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="98446-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="98446-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="98446-116">Remarks</span></span>

<span data-ttu-id="98446-117">Эта функция завершает вызов [iWbemqualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) метод.</span><span class="sxs-lookup"><span data-stu-id="98446-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="98446-118">Этот вызов рекомендуется, но не требуется.</span><span class="sxs-lookup"><span data-stu-id="98446-118">This call is recommended, but not required.</span></span> <span data-ttu-id="98446-119">Он немедленно выпускает ресурсы, связанные с перечислением.</span><span class="sxs-lookup"><span data-stu-id="98446-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="98446-120">Требования</span><span class="sxs-lookup"><span data-stu-id="98446-120">Requirements</span></span>  

<span data-ttu-id="98446-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98446-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="98446-122">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="98446-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="98446-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="98446-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98446-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="98446-124">See also</span></span>

- [<span data-ttu-id="98446-125">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="98446-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
