---
title: "Метод ICorDebugController::IsRunning"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.IsRunning
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::IsRunning
helpviewer_keywords:
- IsRunning method [.NET Framework debugging]
- ICorDebugController::IsRunning method [.NET Framework debugging]
ms.assetid: b33ff059-40c4-4dfe-9cb2-21bfed2de0b0
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 57621c0097c63ee9caca0a3fc4d5e95666b4e5b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="4b89e-102">Метод ICorDebugController::IsRunning</span><span class="sxs-lookup"><span data-stu-id="4b89e-102">ICorDebugController::IsRunning Method</span></span>
<span data-ttu-id="4b89e-103">Возвращает значение, указывающее, является ли потоки в процессе в данный момент выполнения свободно.</span><span class="sxs-lookup"><span data-stu-id="4b89e-103">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b89e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b89e-104">Syntax</span></span>  
  
```  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b89e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4b89e-105">Parameters</span></span>  
 `pbRunning`  
 <span data-ttu-id="4b89e-106">[out] Указатель на значение, являющееся `true` если потоки в процессе выполняются свободно, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="4b89e-106">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b89e-107">Требования</span><span class="sxs-lookup"><span data-stu-id="4b89e-107">Requirements</span></span>  
 <span data-ttu-id="4b89e-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b89e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b89e-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b89e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b89e-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b89e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b89e-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b89e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b89e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4b89e-112">See Also</span></span>  
 
