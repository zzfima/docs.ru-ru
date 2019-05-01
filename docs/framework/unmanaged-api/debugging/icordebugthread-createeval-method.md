---
title: Метод ICorDebugThread::CreateEval
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2016795e7b2c0588e2bd69e764fb96f7f90b24d0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994075"
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="c706b-102">Метод ICorDebugThread::CreateEval</span><span class="sxs-lookup"><span data-stu-id="c706b-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="c706b-103">Создает объект ICorDebugEval, которая собирает и предоставляет функциональные возможности ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="c706b-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c706b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c706b-104">Syntax</span></span>  
  
```  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c706b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c706b-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="c706b-106">[out] Указатель на адрес `ICorDebugEval` объект, который собирает и предоставляет функциональные возможности для данного потока.</span><span class="sxs-lookup"><span data-stu-id="c706b-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c706b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="c706b-107">Remarks</span></span>  
 <span data-ttu-id="c706b-108">Объект выполнения будет отправлять новую цепочку в потоке перед выполнением этого вычисления.</span><span class="sxs-lookup"><span data-stu-id="c706b-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="c706b-109">Это прервет вычисления, в данный момент выполняется в потоке до завершения оценки.</span><span class="sxs-lookup"><span data-stu-id="c706b-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c706b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c706b-110">Requirements</span></span>  
 <span data-ttu-id="c706b-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c706b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c706b-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c706b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c706b-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c706b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c706b-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c706b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
