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
ms.openlocfilehash: f24c07a654dc2345cb65226463573576a6fb3658
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125337"
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="870ac-102">Метод ICorDebugController::IsRunning</span><span class="sxs-lookup"><span data-stu-id="870ac-102">ICorDebugController::IsRunning Method</span></span>
<span data-ttu-id="870ac-103">Возвращает значение, указывающее, выполняются ли в настоящий момент потоки в процессе.</span><span class="sxs-lookup"><span data-stu-id="870ac-103">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="870ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="870ac-104">Syntax</span></span>  
  
```cpp  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="870ac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="870ac-105">Parameters</span></span>  
 `pbRunning`  
 <span data-ttu-id="870ac-106">заполняет Указатель на значение, которое `true`, если потоки в процессе выполняются свободно; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="870ac-106">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="870ac-107">Требования</span><span class="sxs-lookup"><span data-stu-id="870ac-107">Requirements</span></span>  
 <span data-ttu-id="870ac-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="870ac-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="870ac-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="870ac-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="870ac-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="870ac-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="870ac-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="870ac-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="870ac-112">См. также</span><span class="sxs-lookup"><span data-stu-id="870ac-112">See also</span></span>
