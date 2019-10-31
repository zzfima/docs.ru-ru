---
title: Функция QualifierSet_Next (Справочник по неуправляемым API)
description: Функция QualifierSet_Next извлекает следующий квалификатор в перечислении.
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
ms.openlocfilehash: c9c824b0158618848c13183d92f88604460d5099
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141725"
---
# <a name="qualifierset_next-function"></a><span data-ttu-id="4850b-103">Функция QualifierSet_Next</span><span class="sxs-lookup"><span data-stu-id="4850b-103">QualifierSet_Next function</span></span>
<span data-ttu-id="4850b-104">Получает следующий квалификатор в перечислении, начатом вызовом функции [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="4850b-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="4850b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4850b-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="4850b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4850b-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="4850b-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="4850b-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="4850b-108">окне Указатель на экземпляр [ивбемкуалифиерсет](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="4850b-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`   
<span data-ttu-id="4850b-109">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="4850b-109">[in] Reserved.</span></span> <span data-ttu-id="4850b-110">Этот параметр должен иметь значение 0.</span><span class="sxs-lookup"><span data-stu-id="4850b-110">This parameter must be 0.</span></span>

`pstrName`   
<span data-ttu-id="4850b-111">заполняет Имя квалификатора.</span><span class="sxs-lookup"><span data-stu-id="4850b-111">[out] The name of the qualifier.</span></span> <span data-ttu-id="4850b-112">Если `null`, этот параметр игнорируется. в противном случае `pstrName` не должен указывать на допустимый `BSTR` или на утечку памяти.</span><span class="sxs-lookup"><span data-stu-id="4850b-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="4850b-113">Если значение не равно null, функция всегда выделяет новую `BSTR`, когда она возвращает `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="4850b-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

`pVal`   
<span data-ttu-id="4850b-114">заполняет В случае успеха значение квалификатора.</span><span class="sxs-lookup"><span data-stu-id="4850b-114">[out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="4850b-115">Если функция завершается ошибкой, `VARIANT`, на которую указывает `pVal`, не изменяется.</span><span class="sxs-lookup"><span data-stu-id="4850b-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="4850b-116">Если этот параметр имеет значение `null`, параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="4850b-116">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="4850b-117">заполняет Указатель на значение типа LONG, которое получает флаг квалификатора.</span><span class="sxs-lookup"><span data-stu-id="4850b-117">[out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="4850b-118">Если сведения о разновидностях не нужны, этот параметр можно `null`.</span><span class="sxs-lookup"><span data-stu-id="4850b-118">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="4850b-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4850b-119">Return value</span></span>

<span data-ttu-id="4850b-120">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="4850b-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4850b-121">Константа</span><span class="sxs-lookup"><span data-stu-id="4850b-121">Constant</span></span>  |<span data-ttu-id="4850b-122">значения</span><span class="sxs-lookup"><span data-stu-id="4850b-122">Value</span></span>  |<span data-ttu-id="4850b-123">Описание</span><span class="sxs-lookup"><span data-stu-id="4850b-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="4850b-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="4850b-124">0x80041008</span></span> | <span data-ttu-id="4850b-125">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="4850b-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="4850b-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="4850b-126">0x8004101d</span></span> | <span data-ttu-id="4850b-127">Вызывающий объект не вызывал [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="4850b-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="4850b-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="4850b-128">0x80041006</span></span> | <span data-ttu-id="4850b-129">Недостаточно памяти для начала нового перечисления.</span><span class="sxs-lookup"><span data-stu-id="4850b-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="4850b-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="4850b-130">0x40005</span></span> | <span data-ttu-id="4850b-131">В перечислении не осталось квалификаторов.</span><span class="sxs-lookup"><span data-stu-id="4850b-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="4850b-132">0</span><span class="sxs-lookup"><span data-stu-id="4850b-132">0</span></span> | <span data-ttu-id="4850b-133">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="4850b-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="4850b-134">Заметки</span><span class="sxs-lookup"><span data-stu-id="4850b-134">Remarks</span></span>

<span data-ttu-id="4850b-135">Эта функция заключает в оболочку вызов метода [ивбемкуалифиерсет:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) .</span><span class="sxs-lookup"><span data-stu-id="4850b-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="4850b-136">Вы вызываете функцию `QualifierSet_Next` многократно, чтобы перечислить все квалификаторы, пока функция не вернет `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="4850b-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="4850b-137">Чтобы завершить перечисление раньше, вызовите функцию [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="4850b-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="4850b-138">Порядок квалификаторов, возвращаемых во время перечисления, не определен.</span><span class="sxs-lookup"><span data-stu-id="4850b-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="4850b-139">Требования</span><span class="sxs-lookup"><span data-stu-id="4850b-139">Requirements</span></span>  
 <span data-ttu-id="4850b-140">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4850b-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4850b-141">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="4850b-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4850b-142">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4850b-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4850b-143">См. также</span><span class="sxs-lookup"><span data-stu-id="4850b-143">See also</span></span>

- [<span data-ttu-id="4850b-144">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="4850b-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
