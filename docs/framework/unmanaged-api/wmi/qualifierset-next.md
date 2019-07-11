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
ms.openlocfilehash: 5ac5cc8633881749bdc167e1b3925a83f7adf3b3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760298"
---
# <a name="qualifiersetnext-function"></a><span data-ttu-id="8f420-103">Функция QualifierSet_Next</span><span class="sxs-lookup"><span data-stu-id="8f420-103">QualifierSet_Next function</span></span>
<span data-ttu-id="8f420-104">Получает следующий квалификатор в перечислении, начатом вызовом функции [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="8f420-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="8f420-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f420-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="8f420-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8f420-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="8f420-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="8f420-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="8f420-108">[in] Указатель на [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="8f420-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`   
<span data-ttu-id="8f420-109">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="8f420-109">[in] Reserved.</span></span> <span data-ttu-id="8f420-110">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="8f420-110">This parameter must be 0.</span></span>

`pstrName`   
<span data-ttu-id="8f420-111">[out] Имя квалификатора.</span><span class="sxs-lookup"><span data-stu-id="8f420-111">[out] The name of the qualifier.</span></span> <span data-ttu-id="8f420-112">Если `null`, этот параметр не учитывается, в противном случае — значение `pstrName` не должна указывать на допустимый `BSTR` или возникает утечка памяти.</span><span class="sxs-lookup"><span data-stu-id="8f420-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="8f420-113">Если не равно null, функция всегда назначает новый `BSTR` при возврате `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="8f420-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

`pVal`   
<span data-ttu-id="8f420-114">[out] При успешном выполнении значение для квалификатора.</span><span class="sxs-lookup"><span data-stu-id="8f420-114">[out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="8f420-115">Если функция завершается с ошибкой, `VARIANT` , на которые указывают `pVal` не изменяется.</span><span class="sxs-lookup"><span data-stu-id="8f420-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="8f420-116">Если этот параметр имеет `null`, параметр учитывается.</span><span class="sxs-lookup"><span data-stu-id="8f420-116">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="8f420-117">[out] Указатель на значение типа LONG, принимающий флаг квалификатора.</span><span class="sxs-lookup"><span data-stu-id="8f420-117">[out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="8f420-118">Если сведения о версии не требуется, этот параметр может быть `null`.</span><span class="sxs-lookup"><span data-stu-id="8f420-118">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="8f420-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8f420-119">Return value</span></span>

<span data-ttu-id="8f420-120">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="8f420-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8f420-121">Константа</span><span class="sxs-lookup"><span data-stu-id="8f420-121">Constant</span></span>  |<span data-ttu-id="8f420-122">Значение</span><span class="sxs-lookup"><span data-stu-id="8f420-122">Value</span></span>  |<span data-ttu-id="8f420-123">Описание</span><span class="sxs-lookup"><span data-stu-id="8f420-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8f420-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="8f420-124">0x80041008</span></span> | <span data-ttu-id="8f420-125">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="8f420-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="8f420-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="8f420-126">0x8004101d</span></span> | <span data-ttu-id="8f420-127">Вызывающая сторона не вызвала [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="8f420-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="8f420-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="8f420-128">0x80041006</span></span> | <span data-ttu-id="8f420-129">Не хватает памяти, позволяющих начать новое перечисление.</span><span class="sxs-lookup"><span data-stu-id="8f420-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="8f420-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="8f420-130">0x40005</span></span> | <span data-ttu-id="8f420-131">Нет дополнительные квалификаторы, остаются в перечислении.</span><span class="sxs-lookup"><span data-stu-id="8f420-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="8f420-132">0</span><span class="sxs-lookup"><span data-stu-id="8f420-132">0</span></span> | <span data-ttu-id="8f420-133">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="8f420-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="8f420-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="8f420-134">Remarks</span></span>

<span data-ttu-id="8f420-135">Эта функция создает оболочку для вызова [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) метод.</span><span class="sxs-lookup"><span data-stu-id="8f420-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="8f420-136">Вы вызываете `QualifierSet_Next` функции несколько раз, чтобы перечислить все квалификаторы до возврата функции `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="8f420-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="8f420-137">Чтобы завершить перечисление раньше, вызовите [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) функции.</span><span class="sxs-lookup"><span data-stu-id="8f420-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="8f420-138">Порядок квалификаторы, возвращаемых во время перечисления не определено.</span><span class="sxs-lookup"><span data-stu-id="8f420-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="8f420-139">Требования</span><span class="sxs-lookup"><span data-stu-id="8f420-139">Requirements</span></span>  
 <span data-ttu-id="8f420-140">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f420-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f420-141">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8f420-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8f420-142">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8f420-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f420-143">См. также</span><span class="sxs-lookup"><span data-stu-id="8f420-143">See also</span></span>

- [<span data-ttu-id="8f420-144">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="8f420-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
