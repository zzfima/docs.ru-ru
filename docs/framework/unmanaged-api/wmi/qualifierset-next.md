---
title: Функция QualifierSet_Next (Справочник по неуправляемым API)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8b96957467b0acb100f7eea137b3294a60e208a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180912"
---
# <a name="qualifiersetnext-function"></a><span data-ttu-id="aff30-103">Функция QualifierSet_Next</span><span class="sxs-lookup"><span data-stu-id="aff30-103">QualifierSet_Next function</span></span>
<span data-ttu-id="aff30-104">Получает следующий квалификатор в перечислении, начатом вызовом функции [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="aff30-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="aff30-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aff30-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="aff30-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="aff30-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="aff30-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="aff30-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="aff30-108">[in] Указатель на [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="aff30-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`   
<span data-ttu-id="aff30-109">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="aff30-109">[in] Reserved.</span></span> <span data-ttu-id="aff30-110">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="aff30-110">This parameter must be 0.</span></span>

`pstrName`   
<span data-ttu-id="aff30-111">[out] Имя квалификатора.</span><span class="sxs-lookup"><span data-stu-id="aff30-111">[out] The name of the qualifier.</span></span> <span data-ttu-id="aff30-112">Если `null`, этот параметр не учитывается, в противном случае — значение `pstrName` не должна указывать на допустимый `BSTR` или возникает утечка памяти.</span><span class="sxs-lookup"><span data-stu-id="aff30-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="aff30-113">Если не равно null, функция всегда назначает новый `BSTR` при возврате `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="aff30-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

`pVal`   
<span data-ttu-id="aff30-114">[out] При успешном выполнении значение для квалификатора.</span><span class="sxs-lookup"><span data-stu-id="aff30-114">[out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="aff30-115">Если функция завершается с ошибкой, `VARIANT` , на которые указывают `pVal` не изменяется.</span><span class="sxs-lookup"><span data-stu-id="aff30-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="aff30-116">Если этот параметр имеет `null`, параметр учитывается.</span><span class="sxs-lookup"><span data-stu-id="aff30-116">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="aff30-117">[out] Указатель на значение типа LONG, принимающий флаг квалификатора.</span><span class="sxs-lookup"><span data-stu-id="aff30-117">[out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="aff30-118">Если сведения о версии не требуется, этот параметр может быть `null`.</span><span class="sxs-lookup"><span data-stu-id="aff30-118">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="aff30-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="aff30-119">Return value</span></span>

<span data-ttu-id="aff30-120">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="aff30-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="aff30-121">Константа</span><span class="sxs-lookup"><span data-stu-id="aff30-121">Constant</span></span>  |<span data-ttu-id="aff30-122">Значение</span><span class="sxs-lookup"><span data-stu-id="aff30-122">Value</span></span>  |<span data-ttu-id="aff30-123">Описание</span><span class="sxs-lookup"><span data-stu-id="aff30-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="aff30-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="aff30-124">0x80041008</span></span> | <span data-ttu-id="aff30-125">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="aff30-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="aff30-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="aff30-126">0x8004101d</span></span> | <span data-ttu-id="aff30-127">Вызывающая сторона не вызвала [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="aff30-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="aff30-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="aff30-128">0x80041006</span></span> | <span data-ttu-id="aff30-129">Не хватает памяти, позволяющих начать новое перечисление.</span><span class="sxs-lookup"><span data-stu-id="aff30-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="aff30-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="aff30-130">0x40005</span></span> | <span data-ttu-id="aff30-131">Нет дополнительные квалификаторы, остаются в перечислении.</span><span class="sxs-lookup"><span data-stu-id="aff30-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="aff30-132">0</span><span class="sxs-lookup"><span data-stu-id="aff30-132">0</span></span> | <span data-ttu-id="aff30-133">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="aff30-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="aff30-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="aff30-134">Remarks</span></span>

<span data-ttu-id="aff30-135">Эта функция создает оболочку для вызова [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) метод.</span><span class="sxs-lookup"><span data-stu-id="aff30-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="aff30-136">Вы вызываете `QualifierSet_Next` функции несколько раз, чтобы перечислить все квалификаторы до возврата функции `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="aff30-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="aff30-137">Чтобы завершить перечисление раньше, вызовите [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) функции.</span><span class="sxs-lookup"><span data-stu-id="aff30-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="aff30-138">Порядок квалификаторы, возвращаемых во время перечисления не определено.</span><span class="sxs-lookup"><span data-stu-id="aff30-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="aff30-139">Требования</span><span class="sxs-lookup"><span data-stu-id="aff30-139">Requirements</span></span>  
 <span data-ttu-id="aff30-140">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aff30-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aff30-141">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="aff30-141">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="aff30-142">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="aff30-142">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="aff30-143">См. также</span><span class="sxs-lookup"><span data-stu-id="aff30-143">See also</span></span>

- [<span data-ttu-id="aff30-144">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="aff30-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
