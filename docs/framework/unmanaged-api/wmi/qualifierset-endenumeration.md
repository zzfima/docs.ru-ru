---
title: Функция QualifierSet_EndEnumeration (Справочник по неуправляемым API)
description: Функция QualifierSet_EndEnumeration завершает перечисления.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9d3f8966f6333487631a0e155c7be49075a6992
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734679"
---
# <a name="qualifiersetendenumeration-function"></a><span data-ttu-id="545ee-103">Функция QualifierSet_EndEnumeration</span><span class="sxs-lookup"><span data-stu-id="545ee-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="545ee-104">Завершается перечисление начался вызовом [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) функции.</span><span class="sxs-lookup"><span data-stu-id="545ee-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="545ee-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="545ee-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="545ee-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="545ee-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="545ee-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="545ee-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="545ee-108">[in] Указатель на [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="545ee-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="545ee-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="545ee-109">Return value</span></span>

<span data-ttu-id="545ee-110">Следующее значение, возвращаемое этой функцией, определенные в *WbemCli.h* файл заголовка, также можно определить его как константа в коде:</span><span class="sxs-lookup"><span data-stu-id="545ee-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="545ee-111">Константа</span><span class="sxs-lookup"><span data-stu-id="545ee-111">Constant</span></span>  |<span data-ttu-id="545ee-112">Значение</span><span class="sxs-lookup"><span data-stu-id="545ee-112">Value</span></span>  |<span data-ttu-id="545ee-113">Описание</span><span class="sxs-lookup"><span data-stu-id="545ee-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="545ee-114">0</span><span class="sxs-lookup"><span data-stu-id="545ee-114">0</span></span> | <span data-ttu-id="545ee-115">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="545ee-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="545ee-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="545ee-116">Remarks</span></span>

<span data-ttu-id="545ee-117">Эта функция создает оболочку для вызова [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) метод.</span><span class="sxs-lookup"><span data-stu-id="545ee-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="545ee-118">Этот вызов рекомендуется, но не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="545ee-118">This call is recommended, but not required.</span></span> <span data-ttu-id="545ee-119">Она немедленно освобождает ресурсы, связанные с перечислением.</span><span class="sxs-lookup"><span data-stu-id="545ee-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="545ee-120">Требования</span><span class="sxs-lookup"><span data-stu-id="545ee-120">Requirements</span></span>  

<span data-ttu-id="545ee-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="545ee-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="545ee-122">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="545ee-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="545ee-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="545ee-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="545ee-124">См. также</span><span class="sxs-lookup"><span data-stu-id="545ee-124">See also</span></span>
- [<span data-ttu-id="545ee-125">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="545ee-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
