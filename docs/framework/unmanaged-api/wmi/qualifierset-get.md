---
title: "Функция QualifierSet_Get (Справочник по неуправляемым API)"
description: "Функция QualifierSet_Get возвращает именованного квалификатора."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_Get
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_Get
helpviewer_keywords: QualifierSet_Get function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aaf5de5b8e16ee2f96c7bc29dbb09f93298dd185
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetget-function"></a><span data-ttu-id="456a7-103">Функция QualifierSet_Get</span><span class="sxs-lookup"><span data-stu-id="456a7-103">QualifierSet_Get function</span></span>
<span data-ttu-id="456a7-104">Возвращает указанный именованный квалификатор.</span><span class="sxs-lookup"><span data-stu-id="456a7-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="456a7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="456a7-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="456a7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="456a7-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="456a7-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="456a7-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="456a7-108">[in] Указатель на [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="456a7-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`wszName`   
<span data-ttu-id="456a7-109">[in] Имя квалификатора, значение которого запрашивается.</span><span class="sxs-lookup"><span data-stu-id="456a7-109">[in] The name of the qualifier whose value is requested.</span></span>

`lFlags`   
<span data-ttu-id="456a7-110">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="456a7-110">[in] Reserved.</span></span> <span data-ttu-id="456a7-111">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="456a7-111">This parameter must be 0.</span></span>

`pVal`   
<span data-ttu-id="456a7-112">[out] При успешном выполнении правильный тип и значение квалификатора.</span><span class="sxs-lookup"><span data-stu-id="456a7-112">[out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="456a7-113">Если функция завершается с ошибкой, `VARIANT` , на который указывает `pVal` не изменяется.</span><span class="sxs-lookup"><span data-stu-id="456a7-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="456a7-114">Если этот параметр равен `null`, что параметр учитывается.</span><span class="sxs-lookup"><span data-stu-id="456a7-114">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="456a7-115">[out] Указатель на значение типа LONG, получающий биты flavor квалификатор для запрошенного квалификатор.</span><span class="sxs-lookup"><span data-stu-id="456a7-115">[out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="456a7-116">Если сведения о версии не требуется, этот параметр может иметь `null`.</span><span class="sxs-lookup"><span data-stu-id="456a7-116">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="456a7-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="456a7-117">Return value</span></span>

<span data-ttu-id="456a7-118">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="456a7-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="456a7-119">Константа</span><span class="sxs-lookup"><span data-stu-id="456a7-119">Constant</span></span>  |<span data-ttu-id="456a7-120">Значение</span><span class="sxs-lookup"><span data-stu-id="456a7-120">Value</span></span>  |<span data-ttu-id="456a7-121">Описание</span><span class="sxs-lookup"><span data-stu-id="456a7-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="456a7-122">0x80041008</span><span class="sxs-lookup"><span data-stu-id="456a7-122">0x80041008</span></span> | <span data-ttu-id="456a7-123">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="456a7-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="456a7-124">0x80041002</span><span class="sxs-lookup"><span data-stu-id="456a7-124">0x80041002</span></span> | <span data-ttu-id="456a7-125">Указанный квалификатор не существует.</span><span class="sxs-lookup"><span data-stu-id="456a7-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="456a7-126">0</span><span class="sxs-lookup"><span data-stu-id="456a7-126">0</span></span> | <span data-ttu-id="456a7-127">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="456a7-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="456a7-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="456a7-128">Remarks</span></span>

<span data-ttu-id="456a7-129">Эта функция создает оболочку для вызова [IWbemQualifierSet::Get](https://msdn.microsoft.com/library/aa391867(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="456a7-129">This function wraps a call to the [IWbemQualifierSet::Get](https://msdn.microsoft.com/library/aa391867(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="456a7-130">Требования</span><span class="sxs-lookup"><span data-stu-id="456a7-130">Requirements</span></span>  
 <span data-ttu-id="456a7-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="456a7-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="456a7-132">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="456a7-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="456a7-133">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="456a7-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="456a7-134">См. также</span><span class="sxs-lookup"><span data-stu-id="456a7-134">See also</span></span>  
[<span data-ttu-id="456a7-135">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="456a7-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
