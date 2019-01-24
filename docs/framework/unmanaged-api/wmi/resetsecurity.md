---
title: Функция ResetSecurity (Справочник по неуправляемым API)
description: Функция ResetSecurity присваивает маркер олицетворения для текущего потока.
ms.date: 11/06/2017
api_name:
- ResetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ResetSecurity
helpviewer_keywords:
- ResetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f117b9807d57847d53cf00fbb4983e187798f09
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730858"
---
# <a name="resetsecurity-function"></a><span data-ttu-id="18eda-103">Функция ResetSecurity</span><span class="sxs-lookup"><span data-stu-id="18eda-103">ResetSecurity function</span></span>
<span data-ttu-id="18eda-104">Назначает предоставленный маркер олицетворения текущему потоку.</span><span class="sxs-lookup"><span data-stu-id="18eda-104">Assigns the supplied impersonation token to the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="18eda-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18eda-105">Syntax</span></span>  
  
```  
HRESULT ResetSecurity (
   [in] HANDLE token
); 
```  

## <a name="parameters"></a><span data-ttu-id="18eda-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="18eda-106">Parameters</span></span>

`token`  
<span data-ttu-id="18eda-107">[in] Маркер олицетворения, связываемый с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="18eda-107">[in] The impersonation token to associate with the current thread.</span></span> <span data-ttu-id="18eda-108">Это значение может быть равно `null`.</span><span class="sxs-lookup"><span data-stu-id="18eda-108">Its value can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="18eda-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="18eda-109">Return value</span></span>

<span data-ttu-id="18eda-110">Если функция выполняется успешно, возвращаемое значение равно `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="18eda-110">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="18eda-111">Если функция завершается с ошибкой, возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="18eda-111">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="18eda-112">Чтобы получить расширенные сведения об ошибке, вызовите [GetErrorInfo](geterrorinfo.md) функции.</span><span class="sxs-lookup"><span data-stu-id="18eda-112">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="18eda-113">Требования</span><span class="sxs-lookup"><span data-stu-id="18eda-113">Requirements</span></span>  
 <span data-ttu-id="18eda-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18eda-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18eda-115">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="18eda-115">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="18eda-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="18eda-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18eda-117">См. также</span><span class="sxs-lookup"><span data-stu-id="18eda-117">See also</span></span>
- [<span data-ttu-id="18eda-118">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="18eda-118">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
