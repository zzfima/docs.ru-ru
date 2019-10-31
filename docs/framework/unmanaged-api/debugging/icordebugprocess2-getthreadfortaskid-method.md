---
title: Метод ICorDebugProcess2::GetThreadForTaskID
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetThreadForTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetThreadForTaskID
helpviewer_keywords:
- ICorDebugProcess2::GetThreadForTaskId method [.NET Framework debugging]
- GetThreadForTaskID method [.NET Framework debugging]
ms.assetid: 32d54a5b-8ad3-405b-a1b9-0936a3b49d1e
topic_type:
- apiref
ms.openlocfilehash: 11acf997b2efd74bc8394d830f36d3acbd1eef56
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137202"
---
# <a name="icordebugprocess2getthreadfortaskid-method"></a><span data-ttu-id="e7f64-102">Метод ICorDebugProcess2::GetThreadForTaskID</span><span class="sxs-lookup"><span data-stu-id="e7f64-102">ICorDebugProcess2::GetThreadForTaskID Method</span></span>
<span data-ttu-id="e7f64-103">Возвращает поток, в котором выполняются задачи с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="e7f64-103">Gets the thread on which the task with the specified identifier is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7f64-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7f64-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadForTaskID (  
    [in]  TASKID            taskid,  
    [out] ICorDebugThread2  **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7f64-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e7f64-105">Parameters</span></span>  
 `taskid`  
 <span data-ttu-id="e7f64-106">окне Идентификатор задачи.</span><span class="sxs-lookup"><span data-stu-id="e7f64-106">[in] The identifier of the task.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="e7f64-107">заполняет Указатель на адрес объекта ICorDebugThread2, который представляет поток для извлечения.</span><span class="sxs-lookup"><span data-stu-id="e7f64-107">[out] A pointer to the address of an ICorDebugThread2 object that represents the thread to be retrieved.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7f64-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="e7f64-108">Remarks</span></span>  
 <span data-ttu-id="e7f64-109">Узел может задать идентификатор задачи с помощью метода [ICLRTask:: SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e7f64-109">The host can set the task identifier by using the [ICLRTask::SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7f64-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e7f64-110">Requirements</span></span>  
 <span data-ttu-id="e7f64-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7f64-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7f64-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7f64-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7f64-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7f64-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7f64-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7f64-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
