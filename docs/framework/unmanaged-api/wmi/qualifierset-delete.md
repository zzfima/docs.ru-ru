---
title: Функция QualifierSet_Delete (Справочник по неуправляемым API)
description: Функция QualifierSet_Delete удаляет квалификатор по имени.
ms.date: 11/06/2017
api_name:
- QualifierSet_Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Delete
helpviewer_keywords:
- QualifierSet_Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ca4cc9fb65d1a4bd8713f969bbda5551ce5a2e2
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2018
ms.locfileid: "47236260"
---
# <a name="qualifiersetdelete-function"></a><span data-ttu-id="eadf2-103">Функция QualifierSet_Delete</span><span class="sxs-lookup"><span data-stu-id="eadf2-103">QualifierSet_Delete function</span></span>
<span data-ttu-id="eadf2-104">Удаляет указанный квалификатор по имени.</span><span class="sxs-lookup"><span data-stu-id="eadf2-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="eadf2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eadf2-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a><span data-ttu-id="eadf2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="eadf2-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="eadf2-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="eadf2-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="eadf2-108">[in] Указатель на [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="eadf2-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="eadf2-109">[in] Имя квалификатора, которое необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="eadf2-109">[in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="eadf2-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="eadf2-110">Return value</span></span>

<span data-ttu-id="eadf2-111">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="eadf2-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="eadf2-112">Константа</span><span class="sxs-lookup"><span data-stu-id="eadf2-112">Constant</span></span>  |<span data-ttu-id="eadf2-113">Значение</span><span class="sxs-lookup"><span data-stu-id="eadf2-113">Value</span></span>  |<span data-ttu-id="eadf2-114">Описание</span><span class="sxs-lookup"><span data-stu-id="eadf2-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="eadf2-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="eadf2-115">0x80041008</span></span> | <span data-ttu-id="eadf2-116">`wszName` Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="eadf2-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="eadf2-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="eadf2-117">0x80041016</span></span> | <span data-ttu-id="eadf2-118">Удаление этот квалификатор является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="eadf2-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="eadf2-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="eadf2-119">0x80041002</span></span> | <span data-ttu-id="eadf2-120">Не удалось найти заданного квалификатора.</span><span class="sxs-lookup"><span data-stu-id="eadf2-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="eadf2-121">0</span><span class="sxs-lookup"><span data-stu-id="eadf2-121">0</span></span> | <span data-ttu-id="eadf2-122">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="eadf2-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="eadf2-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="eadf2-123">0x40002</span></span> | <span data-ttu-id="eadf2-124">Локальное переопределение был удален, и исходный квалификатор из родительского объекта была возобновлена области.</span><span class="sxs-lookup"><span data-stu-id="eadf2-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="eadf2-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="eadf2-125">Remarks</span></span>

<span data-ttu-id="eadf2-126">Эта функция создает оболочку для вызова [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) метод.</span><span class="sxs-lookup"><span data-stu-id="eadf2-126">This function wraps a call to the [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) method.</span></span>

<span data-ttu-id="eadf2-127">Из-за правила распространения квалификатор определенного квалификатор может были унаследованную от другого объекта и просто переопределен в текущем классе или экземпляре.</span><span class="sxs-lookup"><span data-stu-id="eadf2-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="eadf2-128">В этом случае `QualifierSet_Delete` метод сбрасывает квалификатор унаследованные исходное значение.</span><span class="sxs-lookup"><span data-stu-id="eadf2-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="eadf2-129">В этом случае, функция возвращает код состояния `WBEM_S_RESET_TO_DEFAULT`.</span><span class="sxs-lookup"><span data-stu-id="eadf2-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="eadf2-130">Требования</span><span class="sxs-lookup"><span data-stu-id="eadf2-130">Requirements</span></span>  
 <span data-ttu-id="eadf2-131">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eadf2-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eadf2-132">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="eadf2-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="eadf2-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="eadf2-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eadf2-134">См. также</span><span class="sxs-lookup"><span data-stu-id="eadf2-134">See also</span></span>  
[<span data-ttu-id="eadf2-135">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="eadf2-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
