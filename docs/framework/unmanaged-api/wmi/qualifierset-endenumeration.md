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
ms.openlocfilehash: dbf47dbfddac7d48b78c9d52969de1ef03385c15
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43486822"
---
# <a name="qualifiersetendenumeration-function"></a><span data-ttu-id="fd2ac-103">Функция QualifierSet_EndEnumeration</span><span class="sxs-lookup"><span data-stu-id="fd2ac-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="fd2ac-104">Завершается перечисление начался вызовом [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) функции.</span><span class="sxs-lookup"><span data-stu-id="fd2ac-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="fd2ac-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd2ac-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="fd2ac-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="fd2ac-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="fd2ac-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="fd2ac-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="fd2ac-108">[in] Указатель на [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="fd2ac-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="fd2ac-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fd2ac-109">Return value</span></span>

<span data-ttu-id="fd2ac-110">Следующее значение, возвращаемое этой функцией, определенные в *WbemCli.h* файл заголовка, также можно определить его как константа в коде:</span><span class="sxs-lookup"><span data-stu-id="fd2ac-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="fd2ac-111">Константа</span><span class="sxs-lookup"><span data-stu-id="fd2ac-111">Constant</span></span>  |<span data-ttu-id="fd2ac-112">Значение</span><span class="sxs-lookup"><span data-stu-id="fd2ac-112">Value</span></span>  |<span data-ttu-id="fd2ac-113">Описание</span><span class="sxs-lookup"><span data-stu-id="fd2ac-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="fd2ac-114">0</span><span class="sxs-lookup"><span data-stu-id="fd2ac-114">0</span></span> | <span data-ttu-id="fd2ac-115">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="fd2ac-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="fd2ac-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="fd2ac-116">Remarks</span></span>

<span data-ttu-id="fd2ac-117">Эта функция создает оболочку для вызова [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) метод.</span><span class="sxs-lookup"><span data-stu-id="fd2ac-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="fd2ac-118">Этот вызов рекомендуется, но не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="fd2ac-118">This call is recommended, but not required.</span></span> <span data-ttu-id="fd2ac-119">Она немедленно освобождает ресурсы, связанные с перечислением.</span><span class="sxs-lookup"><span data-stu-id="fd2ac-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="fd2ac-120">Требования</span><span class="sxs-lookup"><span data-stu-id="fd2ac-120">Requirements</span></span>  

<span data-ttu-id="fd2ac-121">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd2ac-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="fd2ac-122">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fd2ac-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="fd2ac-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fd2ac-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd2ac-124">См. также</span><span class="sxs-lookup"><span data-stu-id="fd2ac-124">See also</span></span>  
[<span data-ttu-id="fd2ac-125">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="fd2ac-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
