---
title: "Функция QualifierSet_Delete (Справочник по неуправляемым API)"
description: "Функция QualifierSet_Delete удаляет квалификатор по имени."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
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
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4e7b5650a0b47fd8d9b64bb9d0fff3511afe2d43
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetdelete-function"></a><span data-ttu-id="05c5f-103">Функция QualifierSet_Delete</span><span class="sxs-lookup"><span data-stu-id="05c5f-103">QualifierSet_Delete function</span></span>
<span data-ttu-id="05c5f-104">Удаляет указанный квалификатор по имени.</span><span class="sxs-lookup"><span data-stu-id="05c5f-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="05c5f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05c5f-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a><span data-ttu-id="05c5f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="05c5f-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="05c5f-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="05c5f-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="05c5f-108">[in] Указатель на [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="05c5f-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`wszName`   
<span data-ttu-id="05c5f-109">[in] Имя квалификатора, которое необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="05c5f-109">[in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="05c5f-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="05c5f-110">Return value</span></span>

<span data-ttu-id="05c5f-111">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="05c5f-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="05c5f-112">Константа</span><span class="sxs-lookup"><span data-stu-id="05c5f-112">Constant</span></span>  |<span data-ttu-id="05c5f-113">Значение</span><span class="sxs-lookup"><span data-stu-id="05c5f-113">Value</span></span>  |<span data-ttu-id="05c5f-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="05c5f-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="05c5f-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="05c5f-115">0x80041008</span></span> | <span data-ttu-id="05c5f-116">`wszName` Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="05c5f-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="05c5f-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="05c5f-117">0x80041016</span></span> | <span data-ttu-id="05c5f-118">Удаление этого квалификатор, недопустимо.</span><span class="sxs-lookup"><span data-stu-id="05c5f-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="05c5f-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="05c5f-119">0x80041002</span></span> | <span data-ttu-id="05c5f-120">Не найден указанный квалификатор.</span><span class="sxs-lookup"><span data-stu-id="05c5f-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="05c5f-121">0</span><span class="sxs-lookup"><span data-stu-id="05c5f-121">0</span></span> | <span data-ttu-id="05c5f-122">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="05c5f-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="05c5f-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="05c5f-123">0x40002</span></span> | <span data-ttu-id="05c5f-124">Переопределение локальной был удален и исходный квалификатор из родительского объекта возобновил области.</span><span class="sxs-lookup"><span data-stu-id="05c5f-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="05c5f-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="05c5f-125">Remarks</span></span>

<span data-ttu-id="05c5f-126">Эта функция создает оболочку для вызова [IWbemQualifierSet::Delete](https://msdn.microsoft.com/library/aa391864(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="05c5f-126">This function wraps a call to the [IWbemQualifierSet::Delete](https://msdn.microsoft.com/library/aa391864(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="05c5f-127">Из-за правила распространения квалификатор квалификатор определенного может были наследуется от другого объекта и просто переопределен в текущего класса или экземпляра.</span><span class="sxs-lookup"><span data-stu-id="05c5f-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="05c5f-128">В этом случае `QualifierSet_Delete` метод сбрасывает квалификатор наследуемые исходное значение.</span><span class="sxs-lookup"><span data-stu-id="05c5f-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="05c5f-129">В этом случае, функция возвращает код состояния `WBEM_S_RESET_TO_DEFAULT`.</span><span class="sxs-lookup"><span data-stu-id="05c5f-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="05c5f-130">Требования</span><span class="sxs-lookup"><span data-stu-id="05c5f-130">Requirements</span></span>  
 <span data-ttu-id="05c5f-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05c5f-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05c5f-132">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="05c5f-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="05c5f-133">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="05c5f-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05c5f-134">См. также</span><span class="sxs-lookup"><span data-stu-id="05c5f-134">See also</span></span>  
[<span data-ttu-id="05c5f-135">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="05c5f-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
