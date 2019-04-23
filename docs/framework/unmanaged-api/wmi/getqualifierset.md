---
title: Функция GetQualifierSet (Справочник по неуправляемым API)
description: Функция GetQualifierSet получает квалификатор класс или экземпляр.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75bf52fbf9552dc464d9c646f0a2b1bc01cf89c0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59193100"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="bf171-103">Функция GetQualifierSet</span><span class="sxs-lookup"><span data-stu-id="bf171-103">GetQualifierSet function</span></span>
<span data-ttu-id="bf171-104">Получает набор квалификатор для экземпляра или определения класса.</span><span class="sxs-lookup"><span data-stu-id="bf171-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="bf171-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf171-105">Syntax</span></span>  
  
```  
HRESULT GetQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="bf171-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="bf171-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="bf171-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="bf171-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="bf171-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="bf171-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="bf171-109">[out] Получает указатель интерфейса, обеспечивающий доступ к квалификаторы объекта класса.</span><span class="sxs-lookup"><span data-stu-id="bf171-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="bf171-110">Параметр `ppQualSet` не может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="bf171-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="bf171-111">Если возникает ошибка, не возвращается новый объект и указатель остается без изменений.</span><span class="sxs-lookup"><span data-stu-id="bf171-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span> 

## <a name="return-value"></a><span data-ttu-id="bf171-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bf171-112">Return value</span></span>

<span data-ttu-id="bf171-113">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="bf171-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="bf171-114">Константа</span><span class="sxs-lookup"><span data-stu-id="bf171-114">Constant</span></span>  |<span data-ttu-id="bf171-115">Значение</span><span class="sxs-lookup"><span data-stu-id="bf171-115">Value</span></span>  |<span data-ttu-id="bf171-116">Описание</span><span class="sxs-lookup"><span data-stu-id="bf171-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="bf171-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="bf171-117">0x80041001</span></span> | <span data-ttu-id="bf171-118">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="bf171-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="bf171-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="bf171-119">0x80041002</span></span> | <span data-ttu-id="bf171-120">Указанный метод не существует.</span><span class="sxs-lookup"><span data-stu-id="bf171-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="bf171-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="bf171-121">0x80041006</span></span> | <span data-ttu-id="bf171-122">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="bf171-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="bf171-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="bf171-123">0x80041008</span></span> | <span data-ttu-id="bf171-124">Параметр — `null`.</span><span class="sxs-lookup"><span data-stu-id="bf171-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="bf171-125">0</span><span class="sxs-lookup"><span data-stu-id="bf171-125">0</span></span> | <span data-ttu-id="bf171-126">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="bf171-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="bf171-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="bf171-127">Remarks</span></span>

<span data-ttu-id="bf171-128">Эта функция создает оболочку для вызова [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) метод.</span><span class="sxs-lookup"><span data-stu-id="bf171-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) method.</span></span> 

<span data-ttu-id="bf171-129">[IWbemQualifierSet указатель](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) позволяет вызывающему объекту добавить, изменить или удалить эти квалификаторы.</span><span class="sxs-lookup"><span data-stu-id="bf171-129">The [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="bf171-130">Таких добавлена, измененные или удаленные квалификаторы применяются ко всей определения класса или экземпляра.</span><span class="sxs-lookup"><span data-stu-id="bf171-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="bf171-131">Требования</span><span class="sxs-lookup"><span data-stu-id="bf171-131">Requirements</span></span>  
<span data-ttu-id="bf171-132">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf171-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf171-133">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="bf171-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="bf171-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bf171-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf171-135">См. также</span><span class="sxs-lookup"><span data-stu-id="bf171-135">See also</span></span>

- [<span data-ttu-id="bf171-136">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="bf171-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
