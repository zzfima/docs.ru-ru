---
title: "Функция клона (Справочник по неуправляемым API)"
description: "Функция клон возвращает новый объект, который представляет собой полный клон текущего."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- Clone
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Clone
helpviewer_keywords:
- Clone function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 270150bb674ee7f9a71cf28008c663e3b833600d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="clone-function"></a><span data-ttu-id="8750b-103">Функция клонирования</span><span class="sxs-lookup"><span data-stu-id="8750b-103">Clone function</span></span>
<span data-ttu-id="8750b-104">Возвращает новый объект, который представляет собой полный клон текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="8750b-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="8750b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8750b-105">Syntax</span></span>  
  
```  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="8750b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8750b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="8750b-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="8750b-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="8750b-108">[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="8750b-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`ppCopy`  
<span data-ttu-id="8750b-109">[out] Новый объект, который имеет полный одиночному из `ptr`.</span><span class="sxs-lookup"><span data-stu-id="8750b-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="8750b-110">Этот аргумент не может быть `null` при получении копия текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="8750b-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="8750b-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8750b-111">Return value</span></span>

<span data-ttu-id="8750b-112">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="8750b-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8750b-113">Константа</span><span class="sxs-lookup"><span data-stu-id="8750b-113">Constant</span></span>  |<span data-ttu-id="8750b-114">Значение</span><span class="sxs-lookup"><span data-stu-id="8750b-114">Value</span></span>  |<span data-ttu-id="8750b-115">Описание:</span><span class="sxs-lookup"><span data-stu-id="8750b-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="8750b-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="8750b-116">0x80041001</span></span> | <span data-ttu-id="8750b-117">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="8750b-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8750b-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="8750b-118">0x80041008</span></span> | <span data-ttu-id="8750b-119">`null`был указан в качестве параметра, и он не является допустимым в этом коде.</span><span class="sxs-lookup"><span data-stu-id="8750b-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="8750b-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="8750b-120">0x80041006</span></span> | <span data-ttu-id="8750b-121">Не хватает памяти доступен для клонирования объекта.</span><span class="sxs-lookup"><span data-stu-id="8750b-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="8750b-122">0</span><span class="sxs-lookup"><span data-stu-id="8750b-122">0</span></span> | <span data-ttu-id="8750b-123">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="8750b-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="8750b-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="8750b-124">Remarks</span></span>

<span data-ttu-id="8750b-125">Эта функция создает оболочку для вызова [IWbemClassObject::Clone](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="8750b-125">This function wraps a call to the [IWbemClassObject::Clone](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="8750b-126">Клонированный объект является COM-объект, имеющий значение счетчика ссылок равно 1.</span><span class="sxs-lookup"><span data-stu-id="8750b-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="8750b-127">Требования</span><span class="sxs-lookup"><span data-stu-id="8750b-127">Requirements</span></span>  
 <span data-ttu-id="8750b-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8750b-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8750b-129">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8750b-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8750b-130">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8750b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8750b-131">См. также</span><span class="sxs-lookup"><span data-stu-id="8750b-131">See also</span></span>  
[<span data-ttu-id="8750b-132">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="8750b-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
