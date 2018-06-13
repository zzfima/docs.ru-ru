---
title: Initialize-функция (Справочник по неуправляемым API)
description: Функцию инициализации выполняет инициализацию WMI.
ms.date: 11/06/2017
api_name:
- Initialize
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Initialize
helpviewer_keywords:
- Initialize function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01de35a0cd4d359dfba0375a85fbce017e44b9f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455759"
---
# <a name="initialize-function"></a><span data-ttu-id="03978-103">Initialize-функция</span><span class="sxs-lookup"><span data-stu-id="03978-103">Initialize function</span></span>
<span data-ttu-id="03978-104">Выполняет инициализацию WMI.</span><span class="sxs-lookup"><span data-stu-id="03978-104">Performs WMI initialization.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="03978-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03978-105">Syntax</span></span> 
```  
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
); 
```  
## <a name="parameters"></a><span data-ttu-id="03978-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="03978-106">Parameters</span></span>

`bAllowIManagementObjectQI`   
<span data-ttu-id="03978-107">[in] `true` для указания, что разрешены вызовы QueryInterface для объектов WMI; `false` в противном случае.</span><span class="sxs-lookup"><span data-stu-id="03978-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="03978-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="03978-108">Return value</span></span>

<span data-ttu-id="03978-109">Функция всегда возвращает `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="03978-109">The function always returns `S_OK` (0).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="03978-110">Требования</span><span class="sxs-lookup"><span data-stu-id="03978-110">Requirements</span></span>  
 <span data-ttu-id="03978-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03978-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03978-112">**Заголовок:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="03978-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="03978-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="03978-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03978-114">См. также</span><span class="sxs-lookup"><span data-stu-id="03978-114">See also</span></span>  
[<span data-ttu-id="03978-115">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="03978-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
