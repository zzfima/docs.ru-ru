---
title: QualifierSet_Delete функция (Неуправляемая справка API)
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
ms.openlocfilehash: 0d2a02ba9d89ba16e776bb73563eaebf8a92f1fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174905"
---
# <a name="qualifierset_delete-function"></a><span data-ttu-id="e3910-103">Функция QualifierSet_Delete</span><span class="sxs-lookup"><span data-stu-id="e3910-103">QualifierSet_Delete function</span></span>
<span data-ttu-id="e3910-104">Удаляет указанный квалификатор по имени.</span><span class="sxs-lookup"><span data-stu-id="e3910-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="e3910-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3910-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName
);
```  

## <a name="parameters"></a><span data-ttu-id="e3910-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e3910-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e3910-107">(в) Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="e3910-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="e3910-108">`ptr`(в) Указатель на экземпляр [IWbemqualifierSet.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)</span><span class="sxs-lookup"><span data-stu-id="e3910-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="e3910-109">`wszName`(в) Имя квалификатора для удаления.</span><span class="sxs-lookup"><span data-stu-id="e3910-109">`wszName` [in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="e3910-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e3910-110">Return value</span></span>

<span data-ttu-id="e3910-111">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="e3910-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e3910-112">Постоянно</span><span class="sxs-lookup"><span data-stu-id="e3910-112">Constant</span></span>  |<span data-ttu-id="e3910-113">Значение</span><span class="sxs-lookup"><span data-stu-id="e3910-113">Value</span></span>  |<span data-ttu-id="e3910-114">Описание</span><span class="sxs-lookup"><span data-stu-id="e3910-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e3910-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e3910-115">0x80041008</span></span> | <span data-ttu-id="e3910-116">Недопустимый параметр `wszName`.</span><span class="sxs-lookup"><span data-stu-id="e3910-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="e3910-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="e3910-117">0x80041016</span></span> | <span data-ttu-id="e3910-118">Удалять этот квалификатор незаконно.</span><span class="sxs-lookup"><span data-stu-id="e3910-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="e3910-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="e3910-119">0x80041002</span></span> | <span data-ttu-id="e3910-120">Указанный квалификатор не найден.</span><span class="sxs-lookup"><span data-stu-id="e3910-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e3910-121">0</span><span class="sxs-lookup"><span data-stu-id="e3910-121">0</span></span> | <span data-ttu-id="e3910-122">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="e3910-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="e3910-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="e3910-123">0x40002</span></span> | <span data-ttu-id="e3910-124">Локальный переопределение был удален, и исходный квалификатор из родительского объекта возобновил область действия.</span><span class="sxs-lookup"><span data-stu-id="e3910-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="e3910-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="e3910-125">Remarks</span></span>

<span data-ttu-id="e3910-126">Эта функция обертывает вызов методом [IWbemqualifierSet::Delete.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete)</span><span class="sxs-lookup"><span data-stu-id="e3910-126">This function wraps a call to the [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) method.</span></span>

<span data-ttu-id="e3910-127">Из-за правил распространения квалификаторов определенный квалификатор может быть унаследован от другого объекта и просто переопределен в текущем классе или экземпляре.</span><span class="sxs-lookup"><span data-stu-id="e3910-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="e3910-128">В этом случае `QualifierSet_Delete` метод сбрасывает квалификатор в исходное унаследованое значение.</span><span class="sxs-lookup"><span data-stu-id="e3910-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="e3910-129">Функция в этом случае возвращает `WBEM_S_RESET_TO_DEFAULT`код статуса.</span><span class="sxs-lookup"><span data-stu-id="e3910-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="e3910-130">Требования</span><span class="sxs-lookup"><span data-stu-id="e3910-130">Requirements</span></span>  
 <span data-ttu-id="e3910-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3910-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3910-132">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e3910-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e3910-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e3910-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3910-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e3910-134">See also</span></span>

- [<span data-ttu-id="e3910-135">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="e3910-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
