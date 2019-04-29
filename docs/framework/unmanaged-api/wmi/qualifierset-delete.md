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
ms.openlocfilehash: 543cc63b3e2188c11a6a8bf1eaa846461375be99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597275"
---
# <a name="qualifiersetdelete-function"></a><span data-ttu-id="89207-103">Функция QualifierSet_Delete</span><span class="sxs-lookup"><span data-stu-id="89207-103">QualifierSet_Delete function</span></span>
<span data-ttu-id="89207-104">Удаляет указанный квалификатор по имени.</span><span class="sxs-lookup"><span data-stu-id="89207-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="89207-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89207-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a><span data-ttu-id="89207-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="89207-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="89207-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="89207-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="89207-108">[in] Указатель на [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="89207-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="89207-109">[in] Имя квалификатора, которое необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="89207-109">[in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="89207-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="89207-110">Return value</span></span>

<span data-ttu-id="89207-111">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="89207-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="89207-112">Константа</span><span class="sxs-lookup"><span data-stu-id="89207-112">Constant</span></span>  |<span data-ttu-id="89207-113">Значение</span><span class="sxs-lookup"><span data-stu-id="89207-113">Value</span></span>  |<span data-ttu-id="89207-114">Описание</span><span class="sxs-lookup"><span data-stu-id="89207-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="89207-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="89207-115">0x80041008</span></span> | <span data-ttu-id="89207-116">Недопустимый параметр `wszName`.</span><span class="sxs-lookup"><span data-stu-id="89207-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="89207-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="89207-117">0x80041016</span></span> | <span data-ttu-id="89207-118">Удаление этот квалификатор является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="89207-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="89207-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="89207-119">0x80041002</span></span> | <span data-ttu-id="89207-120">Не удалось найти заданного квалификатора.</span><span class="sxs-lookup"><span data-stu-id="89207-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="89207-121">0</span><span class="sxs-lookup"><span data-stu-id="89207-121">0</span></span> | <span data-ttu-id="89207-122">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="89207-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="89207-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="89207-123">0x40002</span></span> | <span data-ttu-id="89207-124">Локальное переопределение был удален, и исходный квалификатор из родительского объекта была возобновлена области.</span><span class="sxs-lookup"><span data-stu-id="89207-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="89207-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="89207-125">Remarks</span></span>

<span data-ttu-id="89207-126">Эта функция создает оболочку для вызова [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) метод.</span><span class="sxs-lookup"><span data-stu-id="89207-126">This function wraps a call to the [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) method.</span></span>

<span data-ttu-id="89207-127">Из-за правила распространения квалификатор определенного квалификатор может были унаследованную от другого объекта и просто переопределен в текущем классе или экземпляре.</span><span class="sxs-lookup"><span data-stu-id="89207-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="89207-128">В этом случае `QualifierSet_Delete` метод сбрасывает квалификатор унаследованные исходное значение.</span><span class="sxs-lookup"><span data-stu-id="89207-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="89207-129">В этом случае, функция возвращает код состояния `WBEM_S_RESET_TO_DEFAULT`.</span><span class="sxs-lookup"><span data-stu-id="89207-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="89207-130">Требования</span><span class="sxs-lookup"><span data-stu-id="89207-130">Requirements</span></span>  
 <span data-ttu-id="89207-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89207-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89207-132">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="89207-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="89207-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="89207-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89207-134">См. также</span><span class="sxs-lookup"><span data-stu-id="89207-134">See also</span></span>

- [<span data-ttu-id="89207-135">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="89207-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
