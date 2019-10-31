---
title: Функция Жетерроринфо (Справочник по неуправляемым API)
description: Функция Жетерроринфо получает сведения об ошибке из предыдущего вызова функции.
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
ms.openlocfilehash: 062dc62dfe53af3bf5158cb1add0897eccc1df60
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102611"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="ba685-103">Функция Жетерроринфо</span><span class="sxs-lookup"><span data-stu-id="ba685-103">GetErrorInfo function</span></span>
<span data-ttu-id="ba685-104">Получает сведения об ошибках из предыдущего вызова функции.</span><span class="sxs-lookup"><span data-stu-id="ba685-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ba685-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba685-105">Syntax</span></span>  
  
```cpp  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a><span data-ttu-id="ba685-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ba685-106">Return value</span></span>

<span data-ttu-id="ba685-107">Указатель на объект [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) , если вызов функции завершается успешно, или `null` в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="ba685-107">An pointer to an [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ba685-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="ba685-108">Remarks</span></span>

<span data-ttu-id="ba685-109">Эта функция заключает в оболочку вызов метода [икомсреадингинфо:: жетерроринфо](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) .</span><span class="sxs-lookup"><span data-stu-id="ba685-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ba685-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ba685-110">Requirements</span></span>  
 <span data-ttu-id="ba685-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba685-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba685-112">**Заголовок:** WMINet_Utils. def</span><span class="sxs-lookup"><span data-stu-id="ba685-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="ba685-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ba685-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba685-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ba685-114">See also</span></span>

- [<span data-ttu-id="ba685-115">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="ba685-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
