---
title: Функция QualifierSet_Get (Справочник по неуправляемым API)
description: Функция QualifierSet_Get возвращает именованного квалификатора.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8c10a680f1caffd583097b16c046729fe10b140
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43804244"
---
# <a name="qualifiersetget-function"></a><span data-ttu-id="bb9c2-103">Функция QualifierSet_Get</span><span class="sxs-lookup"><span data-stu-id="bb9c2-103">QualifierSet_Get function</span></span>
<span data-ttu-id="bb9c2-104">Получает указанный именованный квалификатор.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="bb9c2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb9c2-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Get (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a><span data-ttu-id="bb9c2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="bb9c2-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="bb9c2-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="bb9c2-108">[in] Указатель на [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="bb9c2-109">[in] Имя квалификатора, значение которого запрашивается.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-109">[in] The name of the qualifier whose value is requested.</span></span>

`lFlags`   
<span data-ttu-id="bb9c2-110">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-110">[in] Reserved.</span></span> <span data-ttu-id="bb9c2-111">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-111">This parameter must be 0.</span></span>

`pVal`   
<span data-ttu-id="bb9c2-112">[out] При успешном выполнении правильный тип и значение квалификатора.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-112">[out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="bb9c2-113">Если функция завершается с ошибкой, `VARIANT` , на которые указывают `pVal` не изменяется.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="bb9c2-114">Если этот параметр имеет `null`, параметр учитывается.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-114">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="bb9c2-115">[out] Указатель на значение типа LONG, получающий биты flavor квалификатор для запрошенного квалификатор.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-115">[out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="bb9c2-116">Если сведения о версии не требуется, этот параметр может быть `null`.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-116">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="bb9c2-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bb9c2-117">Return value</span></span>

<span data-ttu-id="bb9c2-118">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="bb9c2-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="bb9c2-119">Константа</span><span class="sxs-lookup"><span data-stu-id="bb9c2-119">Constant</span></span>  |<span data-ttu-id="bb9c2-120">Значение</span><span class="sxs-lookup"><span data-stu-id="bb9c2-120">Value</span></span>  |<span data-ttu-id="bb9c2-121">Описание</span><span class="sxs-lookup"><span data-stu-id="bb9c2-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="bb9c2-122">0x80041008</span><span class="sxs-lookup"><span data-stu-id="bb9c2-122">0x80041008</span></span> | <span data-ttu-id="bb9c2-123">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="bb9c2-124">0x80041002</span><span class="sxs-lookup"><span data-stu-id="bb9c2-124">0x80041002</span></span> | <span data-ttu-id="bb9c2-125">Заданного квалификатора не существует.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="bb9c2-126">0</span><span class="sxs-lookup"><span data-stu-id="bb9c2-126">0</span></span> | <span data-ttu-id="bb9c2-127">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="bb9c2-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="bb9c2-128">Remarks</span></span>

<span data-ttu-id="bb9c2-129">Эта функция создает оболочку для вызова [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) метод.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-129">This function wraps a call to the [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="bb9c2-130">Требования</span><span class="sxs-lookup"><span data-stu-id="bb9c2-130">Requirements</span></span>  
 <span data-ttu-id="bb9c2-131">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb9c2-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb9c2-132">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="bb9c2-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="bb9c2-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bb9c2-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb9c2-134">См. также</span><span class="sxs-lookup"><span data-stu-id="bb9c2-134">See also</span></span>  
[<span data-ttu-id="bb9c2-135">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="bb9c2-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
