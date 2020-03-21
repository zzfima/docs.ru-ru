---
title: Функция GetErrorInfo (Неуправляемая справка API)
description: Функция GetErrorInfo извлекает информацию об ошибках из предыдущего вызова функции.
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
ms.openlocfilehash: 802ee66a5be213ac7a599b193ec6de589773ea17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176816"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="6be21-103">Функция GetErrorInfo</span><span class="sxs-lookup"><span data-stu-id="6be21-103">GetErrorInfo function</span></span>
<span data-ttu-id="6be21-104">Получает сведения об ошибках из предыдущего вызова функции.</span><span class="sxs-lookup"><span data-stu-id="6be21-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="6be21-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6be21-105">Syntax</span></span>  
  
```cpp  
IErrorInfo* GetErrorInfo();
```  

## <a name="return-value"></a><span data-ttu-id="6be21-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6be21-106">Return value</span></span>

<span data-ttu-id="6be21-107">Указатель на объект [IErrorInfo,](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) если вызов функции удается, или `null` если он не удается.</span><span class="sxs-lookup"><span data-stu-id="6be21-107">An pointer to an [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="6be21-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="6be21-108">Remarks</span></span>

<span data-ttu-id="6be21-109">Эта функция завершает вызов методом [IComThreadingInfo::GetErrorInfo.](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype)</span><span class="sxs-lookup"><span data-stu-id="6be21-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="6be21-110">Требования</span><span class="sxs-lookup"><span data-stu-id="6be21-110">Requirements</span></span>  
 <span data-ttu-id="6be21-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6be21-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6be21-112">**Заголовок:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="6be21-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="6be21-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6be21-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6be21-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6be21-114">See also</span></span>

- [<span data-ttu-id="6be21-115">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="6be21-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
