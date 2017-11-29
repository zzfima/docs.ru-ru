---
title: "Метод ICorDebugProcess2::GetThreadForTaskID"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.GetThreadForTaskID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::GetThreadForTaskID
helpviewer_keywords:
- ICorDebugProcess2::GetThreadForTaskId method [.NET Framework debugging]
- GetThreadForTaskID method [.NET Framework debugging]
ms.assetid: 32d54a5b-8ad3-405b-a1b9-0936a3b49d1e
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6b7a16baca809bd794b5cf6b668f69487be7c122
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocess2getthreadfortaskid-method"></a><span data-ttu-id="13961-102">Метод ICorDebugProcess2::GetThreadForTaskID</span><span class="sxs-lookup"><span data-stu-id="13961-102">ICorDebugProcess2::GetThreadForTaskID Method</span></span>
<span data-ttu-id="13961-103">Получает поток, на котором выполняется задача с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="13961-103">Gets the thread on which the task with the specified identifier is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13961-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13961-104">Syntax</span></span>  
  
```  
HRESULT GetThreadForTaskID (  
    [in]  TASKID            taskid,  
    [out] ICorDebugThread2  **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13961-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="13961-105">Parameters</span></span>  
 `taskid`  
 <span data-ttu-id="13961-106">[in] Идентификатор задачи.</span><span class="sxs-lookup"><span data-stu-id="13961-106">[in] The identifier of the task.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="13961-107">[out] Указатель на адрес объекта ICorDebugThread2, который представляет поток, который необходимо извлечь.</span><span class="sxs-lookup"><span data-stu-id="13961-107">[out] A pointer to the address of an ICorDebugThread2 object that represents the thread to be retrieved.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13961-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="13961-108">Remarks</span></span>  
 <span data-ttu-id="13961-109">Основное приложение может задать идентификатор задачи с помощью [ICLRTask::SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="13961-109">The host can set the task identifier by using the [ICLRTask::SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13961-110">Требования</span><span class="sxs-lookup"><span data-stu-id="13961-110">Requirements</span></span>  
 <span data-ttu-id="13961-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13961-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13961-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13961-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13961-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13961-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13961-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13961-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
