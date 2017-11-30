---
title: "Функция GetQualifierSet (Справочник по неуправляемым API)"
description: "Функция GetQualifierSet получает квалификатор для класса или экземпляра."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetQualifierSet
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetQualifierSet
helpviewer_keywords: GetQualifierSet function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 15d384003f3a18124a07d83a8308f4b8a5c6a31b
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="getqualifierset-function"></a><span data-ttu-id="5584e-103">Функция GetQualifierSet</span><span class="sxs-lookup"><span data-stu-id="5584e-103">GetQualifierSet function</span></span>
<span data-ttu-id="5584e-104">Извлекает квалификатор для экземпляра класса или определения класса.</span><span class="sxs-lookup"><span data-stu-id="5584e-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="5584e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5584e-105">Syntax</span></span>  
  
```  
HRESULT GetQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="5584e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5584e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="5584e-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="5584e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="5584e-108">[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="5584e-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="5584e-109">[out] Получает указатель интерфейса, обеспечивающего доступ к квалификаторы объекта класса.</span><span class="sxs-lookup"><span data-stu-id="5584e-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="5584e-110">Параметр `ppQualSet` не может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="5584e-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="5584e-111">Если возникает ошибка, не возвращается новый объект и курсор остается без изменений.</span><span class="sxs-lookup"><span data-stu-id="5584e-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span> 

## <a name="return-value"></a><span data-ttu-id="5584e-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5584e-112">Return value</span></span>

<span data-ttu-id="5584e-113">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="5584e-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5584e-114">Константа</span><span class="sxs-lookup"><span data-stu-id="5584e-114">Constant</span></span>  |<span data-ttu-id="5584e-115">Значение</span><span class="sxs-lookup"><span data-stu-id="5584e-115">Value</span></span>  |<span data-ttu-id="5584e-116">Описание</span><span class="sxs-lookup"><span data-stu-id="5584e-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="5584e-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="5584e-117">0x80041001</span></span> | <span data-ttu-id="5584e-118">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="5584e-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="5584e-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="5584e-119">0x80041002</span></span> | <span data-ttu-id="5584e-120">Указанный метод не существует.</span><span class="sxs-lookup"><span data-stu-id="5584e-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="5584e-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="5584e-121">0x80041006</span></span> | <span data-ttu-id="5584e-122">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="5584e-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5584e-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5584e-123">0x80041008</span></span> | <span data-ttu-id="5584e-124">Параметр — `null`.</span><span class="sxs-lookup"><span data-stu-id="5584e-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="5584e-125">0</span><span class="sxs-lookup"><span data-stu-id="5584e-125">0</span></span> | <span data-ttu-id="5584e-126">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="5584e-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="5584e-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="5584e-127">Remarks</span></span>

<span data-ttu-id="5584e-128">Эта функция создает оболочку для вызова [IWbemClassObject::GetQualifierSet](https://msdn.microsoft.com/library/aa391451(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="5584e-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](https://msdn.microsoft.com/library/aa391451(v=vs.85).aspx) method.</span></span> 

<span data-ttu-id="5584e-129">[IWbemQualifierSet указатель](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) позволяет вызывающему объекту добавить, изменить или удалить эти квалификаторы.</span><span class="sxs-lookup"><span data-stu-id="5584e-129">The [IWbemQualifierSet pointer](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="5584e-130">Такие квалификаторы, добавлено, изменяемых или удаляемых применяются для всего экземпляра или класса определения.</span><span class="sxs-lookup"><span data-stu-id="5584e-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="5584e-131">Требования</span><span class="sxs-lookup"><span data-stu-id="5584e-131">Requirements</span></span>  
<span data-ttu-id="5584e-132">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5584e-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5584e-133">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="5584e-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="5584e-134">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5584e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5584e-135">См. также</span><span class="sxs-lookup"><span data-stu-id="5584e-135">See also</span></span>  
[<span data-ttu-id="5584e-136">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="5584e-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
