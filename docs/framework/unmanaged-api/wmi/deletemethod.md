---
title: "Функция DeleteMethod (Справочник по неуправляемым API)"
description: "Функция DeleteMethod Удаляет указанный метод из определения класса CIM."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- DeleteMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- DeleteMethod
helpviewer_keywords:
- DeleteMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 03b147d2fd76e34c6152a0b41ee14319811e9300
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="deletemethod-function"></a><span data-ttu-id="7bbd0-103">Функция DeleteMethod</span><span class="sxs-lookup"><span data-stu-id="7bbd0-103">DeleteMethod function</span></span>
<span data-ttu-id="7bbd0-104">Удаляет указанный метод из определения класса CIM.</span><span class="sxs-lookup"><span data-stu-id="7bbd0-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="7bbd0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7bbd0-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="7bbd0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7bbd0-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="7bbd0-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="7bbd0-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="7bbd0-108">[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="7bbd0-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="7bbd0-109">[in] Имя метода, который требуется удалить из таблицы класса.</span><span class="sxs-lookup"><span data-stu-id="7bbd0-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="7bbd0-110">`wszName`должен быть указателем на допустимый `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="7bbd0-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="7bbd0-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7bbd0-111">Return value</span></span>

<span data-ttu-id="7bbd0-112">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="7bbd0-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7bbd0-113">Константа</span><span class="sxs-lookup"><span data-stu-id="7bbd0-113">Constant</span></span>  |<span data-ttu-id="7bbd0-114">Значение</span><span class="sxs-lookup"><span data-stu-id="7bbd0-114">Value</span></span>  |<span data-ttu-id="7bbd0-115">Описание:</span><span class="sxs-lookup"><span data-stu-id="7bbd0-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="7bbd0-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="7bbd0-116">0x80041002</span></span> | <span data-ttu-id="7bbd0-117">Указанный метод не существует.</span><span class="sxs-lookup"><span data-stu-id="7bbd0-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7bbd0-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7bbd0-118">0x80041006</span></span> | <span data-ttu-id="7bbd0-119">Не хватает памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="7bbd0-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="7bbd0-120">0</span><span class="sxs-lookup"><span data-stu-id="7bbd0-120">0</span></span> | <span data-ttu-id="7bbd0-121">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="7bbd0-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="7bbd0-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="7bbd0-122">Remarks</span></span>

<span data-ttu-id="7bbd0-123">Эта функция создает оболочку для вызова [IWbemClassObject::DeleteMethod](https://msdn.microsoft.com/library/aa391439(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="7bbd0-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](https://msdn.microsoft.com/library/aa391439(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="7bbd0-124">Удаление метода не поддерживается для [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) указателей, указывающих на экземпляры CIM.</span><span class="sxs-lookup"><span data-stu-id="7bbd0-124">Method deletion is not supported for [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="7bbd0-125">Требования</span><span class="sxs-lookup"><span data-stu-id="7bbd0-125">Requirements</span></span>  
 <span data-ttu-id="7bbd0-126">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bbd0-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bbd0-127">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7bbd0-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7bbd0-128">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7bbd0-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bbd0-129">См. также</span><span class="sxs-lookup"><span data-stu-id="7bbd0-129">See also</span></span>  
[<span data-ttu-id="7bbd0-130">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="7bbd0-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
