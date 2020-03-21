---
title: Функция GetqualifierSet (неуправляемая ссылка на API)
description: Функция GetQualifierSet получает набор квалификаторов для класса или экземпляра.
ms.date: 11/06/2017
api_name:
- GetQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetQualifierSet
helpviewer_keywords:
- GetQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 368f0a13871bd48780fa30b370d37157d2724bb8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176777"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="c320f-103">Функция GetQualifierSet</span><span class="sxs-lookup"><span data-stu-id="c320f-103">GetQualifierSet function</span></span>
<span data-ttu-id="c320f-104">Получает набор квалификатор для экземпляра или определения класса.</span><span class="sxs-lookup"><span data-stu-id="c320f-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="c320f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c320f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [out] IWbemQualifierSet  **ppQualSet
);
```  

## <a name="parameters"></a><span data-ttu-id="c320f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c320f-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="c320f-107">(в) Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="c320f-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="c320f-108">(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="c320f-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="c320f-109">(ваут) Получает указатель интерфейса, позволяющий получить доступ к квалификаторам объекта класса.</span><span class="sxs-lookup"><span data-stu-id="c320f-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="c320f-110">Параметр `ppQualSet` не может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="c320f-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="c320f-111">При возникновении ошибки новый объект не возвращается, а указатель остается неизмененным.</span><span class="sxs-lookup"><span data-stu-id="c320f-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="c320f-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c320f-112">Return value</span></span>

<span data-ttu-id="c320f-113">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="c320f-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c320f-114">Постоянно</span><span class="sxs-lookup"><span data-stu-id="c320f-114">Constant</span></span>  |<span data-ttu-id="c320f-115">Значение</span><span class="sxs-lookup"><span data-stu-id="c320f-115">Value</span></span>  |<span data-ttu-id="c320f-116">Описание</span><span class="sxs-lookup"><span data-stu-id="c320f-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="c320f-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="c320f-117">0x80041001</span></span> | <span data-ttu-id="c320f-118">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="c320f-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="c320f-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="c320f-119">0x80041002</span></span> | <span data-ttu-id="c320f-120">Указанный метод не существует.</span><span class="sxs-lookup"><span data-stu-id="c320f-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="c320f-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="c320f-121">0x80041006</span></span> | <span data-ttu-id="c320f-122">Недостаточно памяти для выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="c320f-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c320f-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c320f-123">0x80041008</span></span> | <span data-ttu-id="c320f-124">Параметр `null`.</span><span class="sxs-lookup"><span data-stu-id="c320f-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="c320f-125">0</span><span class="sxs-lookup"><span data-stu-id="c320f-125">0</span></span> | <span data-ttu-id="c320f-126">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="c320f-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="c320f-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="c320f-127">Remarks</span></span>

<span data-ttu-id="c320f-128">Эта функция завершает вызов методом [IWbemClassObject::GetQualifierSet.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset)</span><span class="sxs-lookup"><span data-stu-id="c320f-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) method.</span></span>

<span data-ttu-id="c320f-129">[Указатель IWbemqualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) позволяет вызывающе добавлять, отсеивать или удалять эти квалификаторы.</span><span class="sxs-lookup"><span data-stu-id="c320f-129">The [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="c320f-130">Такие добавленные, отредактированные или удаленные квалификаторы применяются ко всему определению экземпляра или класса.</span><span class="sxs-lookup"><span data-stu-id="c320f-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="c320f-131">Требования</span><span class="sxs-lookup"><span data-stu-id="c320f-131">Requirements</span></span>  
<span data-ttu-id="c320f-132">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c320f-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c320f-133">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c320f-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c320f-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c320f-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c320f-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c320f-135">See also</span></span>

- [<span data-ttu-id="c320f-136">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="c320f-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
