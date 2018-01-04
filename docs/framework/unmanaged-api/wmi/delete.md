---
title: "Удаление функции (Справочник по неуправляемым API)"
description: "Функция удаления удаляет указанное свойство и все его квалификаторов из определения класса CIM."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Delete
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Delete
helpviewer_keywords: Delete function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 30f5bf651990cafe06811019cf2b3d92f866f646
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="delete-function"></a><span data-ttu-id="248df-103">Удаление функции</span><span class="sxs-lookup"><span data-stu-id="248df-103">Delete function</span></span>
<span data-ttu-id="248df-104">Удаляет указанное свойство и все его квалификаторов из определения класса CIM.</span><span class="sxs-lookup"><span data-stu-id="248df-104">Deletes the specified property and all of its qualifiers from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="248df-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="248df-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="248df-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="248df-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="248df-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="248df-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="248df-108">[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="248df-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="248df-109">[in] Имя свойства для удаления.</span><span class="sxs-lookup"><span data-stu-id="248df-109">[in] The name of the property to delete.</span></span> <span data-ttu-id="248df-110">`wszName`должен быть указателем на допустимый `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="248df-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="248df-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="248df-111">Return value</span></span>

<span data-ttu-id="248df-112">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="248df-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="248df-113">Константа</span><span class="sxs-lookup"><span data-stu-id="248df-113">Constant</span></span>  |<span data-ttu-id="248df-114">Значение</span><span class="sxs-lookup"><span data-stu-id="248df-114">Value</span></span>  |<span data-ttu-id="248df-115">Описание:</span><span class="sxs-lookup"><span data-stu-id="248df-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="248df-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="248df-116">0x80041001</span></span> | <span data-ttu-id="248df-117">Произошла неизвестная ошибка.</span><span class="sxs-lookup"><span data-stu-id="248df-117">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="248df-118">0x80041016</span><span class="sxs-lookup"><span data-stu-id="248df-118">0x80041016</span></span> | <span data-ttu-id="248df-119">Не удается удалить свойство.</span><span class="sxs-lookup"><span data-stu-id="248df-119">The property cannot be deleted.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="248df-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="248df-120">0x80041008</span></span> | <span data-ttu-id="248df-121">`wszzName` недопустим.</span><span class="sxs-lookup"><span data-stu-id="248df-121">`wszzName` is invalid.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="248df-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="248df-122">0x80041002</span></span> | <span data-ttu-id="248df-123">Указанное свойство не существует.</span><span class="sxs-lookup"><span data-stu-id="248df-123">The specified property does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="248df-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="248df-124">0x80041006</span></span> | <span data-ttu-id="248df-125">Не хватает памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="248df-125">There is not enough memory to complete the operation.</span></span> |
| `WBEM_E_PROPAGATED_PROPERTY` | <span data-ttu-id="248df-126">0x8004101c</span><span class="sxs-lookup"><span data-stu-id="248df-126">0x8004101c</span></span> | <span data-ttu-id="248df-127">Свойство наследуется от базового класса.</span><span class="sxs-lookup"><span data-stu-id="248df-127">The property is inherited from a base class.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | | <span data-ttu-id="248df-128">Свойство системного свойства.</span><span class="sxs-lookup"><span data-stu-id="248df-128">The property is a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="248df-129">0</span><span class="sxs-lookup"><span data-stu-id="248df-129">0</span></span> | <span data-ttu-id="248df-130">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="248df-130">The function call was successful.</span></span>  |
| `WBEM_E_RESET_TO_DEFAULT` | <span data-ttu-id="248df-131">0x80041030</span><span class="sxs-lookup"><span data-stu-id="248df-131">0x80041030</span></span> | <span data-ttu-id="248df-132">Функция удалить переопределение по умолчанию для текущего класса.</span><span class="sxs-lookup"><span data-stu-id="248df-132">The function deleted an override default value for the current class.</span></span> <span data-ttu-id="248df-133">Значение по умолчанию для этого свойства в родительском классе был reactiviated.</span><span class="sxs-lookup"><span data-stu-id="248df-133">The default value for this property in the parent class has been reactiviated.</span></span> | 

## <a name="remarks"></a><span data-ttu-id="248df-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="248df-134">Remarks</span></span>

<span data-ttu-id="248df-135">Эта функция создает оболочку для вызова [IWbemClassObject::Delete](https://msdn.microsoft.com/library/aa391438(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="248df-135">This function wraps a call to the [IWbemClassObject::Delete](https://msdn.microsoft.com/library/aa391438(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="248df-136">Требования</span><span class="sxs-lookup"><span data-stu-id="248df-136">Requirements</span></span>  
 <span data-ttu-id="248df-137">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="248df-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="248df-138">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="248df-138">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="248df-139">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="248df-139">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="248df-140">См. также</span><span class="sxs-lookup"><span data-stu-id="248df-140">See also</span></span>  
[<span data-ttu-id="248df-141">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="248df-141">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
