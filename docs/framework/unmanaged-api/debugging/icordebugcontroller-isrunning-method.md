---
title: Метод ICorDebugController::IsRunning
ms.date: 03/30/2017
api_name:
- ICorDebugController.IsRunning
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::IsRunning
helpviewer_keywords:
- IsRunning method [.NET Framework debugging]
- ICorDebugController::IsRunning method [.NET Framework debugging]
ms.assetid: b33ff059-40c4-4dfe-9cb2-21bfed2de0b0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5eae9e14bcd0ca430f03a873818246896438463
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227097"
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="8cb8e-102">Метод ICorDebugController::IsRunning</span><span class="sxs-lookup"><span data-stu-id="8cb8e-102">ICorDebugController::IsRunning Method</span></span>
<span data-ttu-id="8cb8e-103">Получает значение, указывающее, потоки в процессе, в настоящее время работают ли свободно.</span><span class="sxs-lookup"><span data-stu-id="8cb8e-103">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cb8e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8cb8e-104">Syntax</span></span>  
  
```  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cb8e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8cb8e-105">Parameters</span></span>  
 `pbRunning`  
 <span data-ttu-id="8cb8e-106">[out] Указатель на значение, являющееся `true` если потоки в процессе выполняются свободно, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="8cb8e-106">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cb8e-107">Требования</span><span class="sxs-lookup"><span data-stu-id="8cb8e-107">Requirements</span></span>  
 <span data-ttu-id="8cb8e-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cb8e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cb8e-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8cb8e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8cb8e-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cb8e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cb8e-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cb8e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cb8e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="8cb8e-112">See also</span></span>
