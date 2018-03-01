---
title: "Перечисление COR_PRF_TRANSITION_REASON"
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
- COR_PRF_TRANSITION_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_TRANSITION_REASON
helpviewer_keywords:
- COR_PRF_TRANSITION_REASON enumeration [.NET Framework profiling]
ms.assetid: da941118-01b7-4197-ae5b-9f2f8adcd623
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 498abc57e35946b2b0c8bf08cdd768bd7039c9f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corprftransitionreason-enumeration"></a><span data-ttu-id="0c1b5-102">Перечисление COR_PRF_TRANSITION_REASON</span><span class="sxs-lookup"><span data-stu-id="0c1b5-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="0c1b5-103">Указывает причину перехода из управляемого в неуправляемый код или наоборот.</span><span class="sxs-lookup"><span data-stu-id="0c1b5-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c1b5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c1b5-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="0c1b5-105">Участники</span><span class="sxs-lookup"><span data-stu-id="0c1b5-105">Members</span></span>  
  
|<span data-ttu-id="0c1b5-106">Член</span><span class="sxs-lookup"><span data-stu-id="0c1b5-106">Member</span></span>|<span data-ttu-id="0c1b5-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="0c1b5-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="0c1b5-108">Переход происходит из-за вызова функции.</span><span class="sxs-lookup"><span data-stu-id="0c1b5-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="0c1b5-109">Переход происходит из-за возврата из функции.</span><span class="sxs-lookup"><span data-stu-id="0c1b5-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c1b5-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="0c1b5-110">Remarks</span></span>  
 <span data-ttu-id="0c1b5-111">Когда происходит переход, профилировщик получает [ICorProfilerCallback::ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) или [ICorProfilerCallback::UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) обратного вызова, которые предоставляет значение `COR_PRF_TRANSITION_REASON` перечисления, чтобы указать причину для перехода.</span><span class="sxs-lookup"><span data-stu-id="0c1b5-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c1b5-112">Требования</span><span class="sxs-lookup"><span data-stu-id="0c1b5-112">Requirements</span></span>  
 <span data-ttu-id="0c1b5-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c1b5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c1b5-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0c1b5-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0c1b5-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c1b5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c1b5-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c1b5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
