---
title: "Функция DeleteMethod (Справочник по неуправляемым API)"
description: "Функция DeleteMethod Удаляет указанный метод из определения класса CIM."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: DeleteMethod
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: DeleteMethod
helpviewer_keywords: DeleteMethod function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d931cb76eeaf19ddeb80bdde412fabeea4b70203
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="deletemethod-function"></a><span data-ttu-id="e4f82-103">Функция DeleteMethod</span><span class="sxs-lookup"><span data-stu-id="e4f82-103">DeleteMethod function</span></span>
<span data-ttu-id="e4f82-104">Удаляет указанный метод из определения класса CIM.</span><span class="sxs-lookup"><span data-stu-id="e4f82-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="e4f82-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e4f82-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="e4f82-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e4f82-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e4f82-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="e4f82-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="e4f82-108">[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="e4f82-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="e4f82-109">[in] Имя метода, который требуется удалить из таблицы класса.</span><span class="sxs-lookup"><span data-stu-id="e4f82-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="e4f82-110">`wszName`должен быть указателем на допустимый `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="e4f82-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="e4f82-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e4f82-111">Return value</span></span>

<span data-ttu-id="e4f82-112">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="e4f82-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e4f82-113">Константа</span><span class="sxs-lookup"><span data-stu-id="e4f82-113">Constant</span></span>  |<span data-ttu-id="e4f82-114">Значение</span><span class="sxs-lookup"><span data-stu-id="e4f82-114">Value</span></span>  |<span data-ttu-id="e4f82-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e4f82-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="e4f82-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="e4f82-116">0x80041002</span></span> | <span data-ttu-id="e4f82-117">Указанный метод не существует.</span><span class="sxs-lookup"><span data-stu-id="e4f82-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e4f82-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e4f82-118">0x80041006</span></span> | <span data-ttu-id="e4f82-119">Не хватает памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="e4f82-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="e4f82-120">0</span><span class="sxs-lookup"><span data-stu-id="e4f82-120">0</span></span> | <span data-ttu-id="e4f82-121">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="e4f82-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="e4f82-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="e4f82-122">Remarks</span></span>

<span data-ttu-id="e4f82-123">Эта функция создает оболочку для вызова [IWbemClassObject::DeleteMethod](https://msdn.microsoft.com/library/aa391439(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="e4f82-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](https://msdn.microsoft.com/library/aa391439(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="e4f82-124">Удаление метода не поддерживается для [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) указателей, указывающих на экземпляры CIM.</span><span class="sxs-lookup"><span data-stu-id="e4f82-124">Method deletion is not supported for [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="e4f82-125">Требования</span><span class="sxs-lookup"><span data-stu-id="e4f82-125">Requirements</span></span>  
 <span data-ttu-id="e4f82-126">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4f82-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4f82-127">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e4f82-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e4f82-128">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e4f82-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4f82-129">См. также</span><span class="sxs-lookup"><span data-stu-id="e4f82-129">See also</span></span>  
[<span data-ttu-id="e4f82-130">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="e4f82-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
