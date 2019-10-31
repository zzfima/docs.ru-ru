---
title: Метод ICorDebugThread2::GetTaskID
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetTaskID
helpviewer_keywords:
- ICorDebugThread2::GetTaskID method [.NET Framework debugging]
- GetTaskID method [.NET Framework debugging]
ms.assetid: 6ba3c6ee-4ba1-4c98-bf1e-8531acd3da09
topic_type:
- apiref
ms.openlocfilehash: d5f2838007504e56ad44614a6778083be046629f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140083"
---
# <a name="icordebugthread2gettaskid-method"></a><span data-ttu-id="eb4f2-102">Метод ICorDebugThread2::GetTaskID</span><span class="sxs-lookup"><span data-stu-id="eb4f2-102">ICorDebugThread2::GetTaskID Method</span></span>
<span data-ttu-id="eb4f2-103">Возвращает идентификатор задачи, выполняющейся в этом потоке.</span><span class="sxs-lookup"><span data-stu-id="eb4f2-103">Gets the identifier of the task running on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb4f2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb4f2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb4f2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eb4f2-105">Parameters</span></span>  
 `pTaskId`  
 <span data-ttu-id="eb4f2-106">заполняет Указатель на идентификатор задачи, выполняемой в потоке, представленном этим объектом ICorDebugThread2.</span><span class="sxs-lookup"><span data-stu-id="eb4f2-106">[out] A pointer to the identifier of the task running on the thread represented by this ICorDebugThread2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb4f2-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="eb4f2-107">Remarks</span></span>  
 <span data-ttu-id="eb4f2-108">Задача может выполняться только в потоке, если поток связан с соединением.</span><span class="sxs-lookup"><span data-stu-id="eb4f2-108">A task can only be running on the thread if the thread is associated with a connection.</span></span> <span data-ttu-id="eb4f2-109">`GetTaskID` возвращает ноль в `pTaskId`, если поток не связан с соединением.</span><span class="sxs-lookup"><span data-stu-id="eb4f2-109">`GetTaskID` returns zero in `pTaskId` if the thread is not associated with a connection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb4f2-110">Требования</span><span class="sxs-lookup"><span data-stu-id="eb4f2-110">Requirements</span></span>  
 <span data-ttu-id="eb4f2-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb4f2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb4f2-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb4f2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb4f2-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb4f2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb4f2-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb4f2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
