---
title: "Функция QualifierSet_Next (Справочник по неуправляемым API)"
description: "Функция QualifierSet_Next получает следующий квалификатор в перечислении."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_Next
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_Next
helpviewer_keywords: QualifierSet_Next function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 01a9c9d162039547849597aaa9c8a6fa38a31455
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetnext-function"></a><span data-ttu-id="becf3-103">Функция QualifierSet_Next</span><span class="sxs-lookup"><span data-stu-id="becf3-103">QualifierSet_Next function</span></span>
<span data-ttu-id="becf3-104">Извлекает следующий квалификатор в перечислении, работы с помощью вызова [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) функции.</span><span class="sxs-lookup"><span data-stu-id="becf3-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="becf3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="becf3-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Next (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,        
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a><span data-ttu-id="becf3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="becf3-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="becf3-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="becf3-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="becf3-108">[in] Указатель на [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="becf3-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`lFlags`   
<span data-ttu-id="becf3-109">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="becf3-109">[in] Reserved.</span></span> <span data-ttu-id="becf3-110">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="becf3-110">This parameter must be 0.</span></span>

`pstrName`   
<span data-ttu-id="becf3-111">[out] Имя квалификатора.</span><span class="sxs-lookup"><span data-stu-id="becf3-111">[out] The name of the qualifier.</span></span> <span data-ttu-id="becf3-112">Если `null`, этот параметр игнорируется, в противном случае — `pstrName` не должен указывать на допустимый `BSTR` или возникает утечка памяти.</span><span class="sxs-lookup"><span data-stu-id="becf3-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="becf3-113">Если значение не null, функция всегда выделяет новый `BSTR` Когда возвращается `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="becf3-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

`pVal`   
<span data-ttu-id="becf3-114">[out] При успешном выполнении значение квалификатора.</span><span class="sxs-lookup"><span data-stu-id="becf3-114">[out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="becf3-115">Если функция завершается с ошибкой, `VARIANT` , на который указывает `pVal` не изменяется.</span><span class="sxs-lookup"><span data-stu-id="becf3-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="becf3-116">Если этот параметр равен `null`, что параметр учитывается.</span><span class="sxs-lookup"><span data-stu-id="becf3-116">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="becf3-117">[out] Указатель на значение типа LONG, принимающий флаг квалификатора.</span><span class="sxs-lookup"><span data-stu-id="becf3-117">[out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="becf3-118">Если сведения о версии не требуется, этот параметр может иметь `null`.</span><span class="sxs-lookup"><span data-stu-id="becf3-118">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="becf3-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="becf3-119">Return value</span></span>

<span data-ttu-id="becf3-120">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="becf3-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="becf3-121">Константа</span><span class="sxs-lookup"><span data-stu-id="becf3-121">Constant</span></span>  |<span data-ttu-id="becf3-122">Значение</span><span class="sxs-lookup"><span data-stu-id="becf3-122">Value</span></span>  |<span data-ttu-id="becf3-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="becf3-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="becf3-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="becf3-124">0x80041008</span></span> | <span data-ttu-id="becf3-125">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="becf3-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="becf3-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="becf3-126">0x8004101d</span></span> | <span data-ttu-id="becf3-127">Вызывающая сторона не вызвала [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="becf3-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="becf3-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="becf3-128">0x80041006</span></span> | <span data-ttu-id="becf3-129">Чтобы начать новое перечисление доступен не хватает памяти.</span><span class="sxs-lookup"><span data-stu-id="becf3-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="becf3-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="becf3-130">0x40005</span></span> | <span data-ttu-id="becf3-131">Нет дополнительные квалификаторы остаются в перечислении.</span><span class="sxs-lookup"><span data-stu-id="becf3-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="becf3-132">0</span><span class="sxs-lookup"><span data-stu-id="becf3-132">0</span></span> | <span data-ttu-id="becf3-133">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="becf3-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="becf3-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="becf3-134">Remarks</span></span>

<span data-ttu-id="becf3-135">Эта функция создает оболочку для вызова [IWbemQualifierSet::Next](https://msdn.microsoft.com/library/aa391870(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="becf3-135">This function wraps a call to the [IWbemQualifierSet::Next](https://msdn.microsoft.com/library/aa391870(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="becf3-136">Можно вызвать `QualifierSet_Next` функции, чтобы перечислить все квалификаторы до возврата функции `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="becf3-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="becf3-137">Чтобы завершить перечисление рано, вызовите [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) функции.</span><span class="sxs-lookup"><span data-stu-id="becf3-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="becf3-138">Заказ квалификаторов, возвращенного во время перечисления не определено.</span><span class="sxs-lookup"><span data-stu-id="becf3-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="becf3-139">Требования</span><span class="sxs-lookup"><span data-stu-id="becf3-139">Requirements</span></span>  
 <span data-ttu-id="becf3-140">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="becf3-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="becf3-141">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="becf3-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="becf3-142">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="becf3-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="becf3-143">См. также</span><span class="sxs-lookup"><span data-stu-id="becf3-143">See also</span></span>  
[<span data-ttu-id="becf3-144">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="becf3-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
