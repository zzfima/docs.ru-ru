---
title: "Метод ICorDebugProcess2::GetThreadForTaskID"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: af63e6cf0d7e4b51f9365c1ccc4ac78158c091bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess2getthreadfortaskid-method"></a><span data-ttu-id="b9f20-102">Метод ICorDebugProcess2::GetThreadForTaskID</span><span class="sxs-lookup"><span data-stu-id="b9f20-102">ICorDebugProcess2::GetThreadForTaskID Method</span></span>
<span data-ttu-id="b9f20-103">Получает поток, на котором выполняется задача с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="b9f20-103">Gets the thread on which the task with the specified identifier is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9f20-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9f20-104">Syntax</span></span>  
  
```  
HRESULT GetThreadForTaskID (  
    [in]  TASKID            taskid,  
    [out] ICorDebugThread2  **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9f20-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9f20-105">Parameters</span></span>  
 `taskid`  
 <span data-ttu-id="b9f20-106">[in] Идентификатор задачи.</span><span class="sxs-lookup"><span data-stu-id="b9f20-106">[in] The identifier of the task.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="b9f20-107">[out] Указатель на адрес объекта ICorDebugThread2, который представляет поток, который необходимо извлечь.</span><span class="sxs-lookup"><span data-stu-id="b9f20-107">[out] A pointer to the address of an ICorDebugThread2 object that represents the thread to be retrieved.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9f20-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="b9f20-108">Remarks</span></span>  
 <span data-ttu-id="b9f20-109">Основное приложение может задать идентификатор задачи с помощью [ICLRTask::SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="b9f20-109">The host can set the task identifier by using the [ICLRTask::SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9f20-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b9f20-110">Requirements</span></span>  
 <span data-ttu-id="b9f20-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9f20-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9f20-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9f20-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9f20-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9f20-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9f20-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9f20-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
