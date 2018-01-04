---
title: "Initialize-функция (Справочник по неуправляемым API)"
description: "Функцию инициализации выполняет инициализацию WMI."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Initialize
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Initialize
helpviewer_keywords: Initialize function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d62d959c5dfeac237abb20b86df87ae07a077dbd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="initialize-function"></a><span data-ttu-id="312da-103">Initialize-функция</span><span class="sxs-lookup"><span data-stu-id="312da-103">Initialize function</span></span>
<span data-ttu-id="312da-104">Выполняет инициализацию WMI.</span><span class="sxs-lookup"><span data-stu-id="312da-104">Performs WMI initialization.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="312da-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="312da-105">Syntax</span></span> 
```  
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
); 
```  
## <a name="parameters"></a><span data-ttu-id="312da-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="312da-106">Parameters</span></span>

`bAllowIManagementObjectQI`   
<span data-ttu-id="312da-107">[in] `true` для указания, что разрешены вызовы QueryInterface для объектов WMI; `false` в противном случае.</span><span class="sxs-lookup"><span data-stu-id="312da-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="312da-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="312da-108">Return value</span></span>

<span data-ttu-id="312da-109">Функция всегда возвращает `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="312da-109">The function always returns `S_OK` (0).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="312da-110">Требования</span><span class="sxs-lookup"><span data-stu-id="312da-110">Requirements</span></span>  
 <span data-ttu-id="312da-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="312da-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="312da-112">**Заголовок:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="312da-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="312da-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="312da-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="312da-114">См. также</span><span class="sxs-lookup"><span data-stu-id="312da-114">See also</span></span>  
[<span data-ttu-id="312da-115">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="312da-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
