---
title: Функция GetErrorInfo (Справочник по неуправляемым API)
description: Функция GetErrorInfo получает сведения об ошибке из предыдущего вызова функции.
ms.date: 11/06/2017
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
ms.openlocfilehash: 5f25777402fa31e72cbbf36f58a6c4cc65542979
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44183763"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="3a1f5-103">GetErrorInfo-функция</span><span class="sxs-lookup"><span data-stu-id="3a1f5-103">GetErrorInfo function</span></span>
<span data-ttu-id="3a1f5-104">Получает сведения об ошибках из предыдущего вызова функции.</span><span class="sxs-lookup"><span data-stu-id="3a1f5-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="3a1f5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a1f5-105">Syntax</span></span>  
  
```  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a><span data-ttu-id="3a1f5-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3a1f5-106">Return value</span></span>

<span data-ttu-id="3a1f5-107">Указатель на [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) объекта, если вызов функции завершается успешно, или `null` при сбое.</span><span class="sxs-lookup"><span data-stu-id="3a1f5-107">An pointer to an [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="3a1f5-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="3a1f5-108">Remarks</span></span>

<span data-ttu-id="3a1f5-109">Эта функция создает оболочку для вызова [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) метод.</span><span class="sxs-lookup"><span data-stu-id="3a1f5-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="3a1f5-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3a1f5-110">Requirements</span></span>  
 <span data-ttu-id="3a1f5-111">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a1f5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a1f5-112">**Заголовок:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="3a1f5-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="3a1f5-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3a1f5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a1f5-114">См. также</span><span class="sxs-lookup"><span data-stu-id="3a1f5-114">See also</span></span>  
[<span data-ttu-id="3a1f5-115">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="3a1f5-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
