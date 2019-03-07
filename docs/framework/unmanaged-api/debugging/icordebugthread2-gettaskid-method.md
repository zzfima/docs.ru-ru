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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 417f99c2b9fa7e77f8696c27cb3929c92956c08c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494653"
---
# <a name="icordebugthread2gettaskid-method"></a><span data-ttu-id="60ae1-102">Метод ICorDebugThread2::GetTaskID</span><span class="sxs-lookup"><span data-stu-id="60ae1-102">ICorDebugThread2::GetTaskID Method</span></span>
<span data-ttu-id="60ae1-103">Получает идентификатор задачи, выполняемой в данном потоке.</span><span class="sxs-lookup"><span data-stu-id="60ae1-103">Gets the identifier of the task running on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60ae1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="60ae1-104">Syntax</span></span>  
  
```  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60ae1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="60ae1-105">Parameters</span></span>  
 `pTaskId`  
 <span data-ttu-id="60ae1-106">[out] Указатель на идентификатор задачи, выполняемой в потоке, представленный этим объектом ICorDebugThread2.</span><span class="sxs-lookup"><span data-stu-id="60ae1-106">[out] A pointer to the identifier of the task running on the thread represented by this ICorDebugThread2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60ae1-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="60ae1-107">Remarks</span></span>  
 <span data-ttu-id="60ae1-108">Задача может быть запущен только в потоке, если поток связан с соединением.</span><span class="sxs-lookup"><span data-stu-id="60ae1-108">A task can only be running on the thread if the thread is associated with a connection.</span></span> <span data-ttu-id="60ae1-109">`GetTaskID` Возвращает нуль `pTaskId` Если поток не связан с соединением.</span><span class="sxs-lookup"><span data-stu-id="60ae1-109">`GetTaskID` returns zero in `pTaskId` if the thread is not associated with a connection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60ae1-110">Требования</span><span class="sxs-lookup"><span data-stu-id="60ae1-110">Requirements</span></span>  
 <span data-ttu-id="60ae1-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60ae1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60ae1-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60ae1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60ae1-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60ae1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60ae1-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60ae1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
