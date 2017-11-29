---
title: "Функция GetErrorInfo (Справочник по неуправляемым API)"
description: "Функция GetErrorInfo извлекает сведения об ошибках в предыдущем вызове функции."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetErrorInfo
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetErrorInfo
helpviewer_keywords: GetErrorInfo function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a1bdaa72723855c6688a7c8c7704b958f6196dfd
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="09ed6-103">GetErrorInfo-функция</span><span class="sxs-lookup"><span data-stu-id="09ed6-103">GetErrorInfo function</span></span>
<span data-ttu-id="09ed6-104">Извлекает сведения об ошибках в предыдущем вызове функции.</span><span class="sxs-lookup"><span data-stu-id="09ed6-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="09ed6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09ed6-105">Syntax</span></span>  
  
```  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a><span data-ttu-id="09ed6-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="09ed6-106">Return value</span></span>

<span data-ttu-id="09ed6-107">Указатель на [IErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms221233(v=vs.85).aspx) объекта после успешного вызова функции, или `null` в случае неудачи.</span><span class="sxs-lookup"><span data-stu-id="09ed6-107">An pointer to an [IErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms221233(v=vs.85).aspx) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="09ed6-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="09ed6-108">Remarks</span></span>

<span data-ttu-id="09ed6-109">Эта функция создает оболочку для вызова [IComThreadingInfo::GetErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="09ed6-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="09ed6-110">Требования</span><span class="sxs-lookup"><span data-stu-id="09ed6-110">Requirements</span></span>  
 <span data-ttu-id="09ed6-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09ed6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09ed6-112">**Заголовок:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="09ed6-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="09ed6-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="09ed6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09ed6-114">См. также</span><span class="sxs-lookup"><span data-stu-id="09ed6-114">See also</span></span>  
[<span data-ttu-id="09ed6-115">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="09ed6-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
