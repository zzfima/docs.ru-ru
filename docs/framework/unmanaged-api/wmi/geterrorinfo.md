---
title: "Функция GetErrorInfo (Справочник по неуправляемым API)"
description: "Функция GetErrorInfo извлекает сведения об ошибках в предыдущем вызове функции."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- GetErrorInfo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetErrorInfo
helpviewer_keywords:
- GetErrorInfo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d4b4acde080c61fbfd5cec319c1986b8c86352c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="47b66-103">GetErrorInfo-функция</span><span class="sxs-lookup"><span data-stu-id="47b66-103">GetErrorInfo function</span></span>
<span data-ttu-id="47b66-104">Извлекает сведения об ошибках в предыдущем вызове функции.</span><span class="sxs-lookup"><span data-stu-id="47b66-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="47b66-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47b66-105">Syntax</span></span>  
  
```  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a><span data-ttu-id="47b66-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="47b66-106">Return value</span></span>

<span data-ttu-id="47b66-107">Указатель на [IErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms221233(v=vs.85).aspx) объекта после успешного вызова функции, или `null` в случае неудачи.</span><span class="sxs-lookup"><span data-stu-id="47b66-107">An pointer to an [IErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms221233(v=vs.85).aspx) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="47b66-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="47b66-108">Remarks</span></span>

<span data-ttu-id="47b66-109">Эта функция создает оболочку для вызова [IComThreadingInfo::GetErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="47b66-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="47b66-110">Требования</span><span class="sxs-lookup"><span data-stu-id="47b66-110">Requirements</span></span>  
 <span data-ttu-id="47b66-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47b66-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47b66-112">**Заголовок:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="47b66-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="47b66-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="47b66-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47b66-114">См. также</span><span class="sxs-lookup"><span data-stu-id="47b66-114">See also</span></span>  
[<span data-ttu-id="47b66-115">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="47b66-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
