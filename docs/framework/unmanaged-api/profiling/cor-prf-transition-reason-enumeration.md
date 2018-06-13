---
title: Перечисление COR_PRF_TRANSITION_REASON
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2556196b7c8f81709e6880962e8ff36e126dd8b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450067"
---
# <a name="corprftransitionreason-enumeration"></a><span data-ttu-id="1fa2d-102">Перечисление COR_PRF_TRANSITION_REASON</span><span class="sxs-lookup"><span data-stu-id="1fa2d-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="1fa2d-103">Указывает причину перехода из управляемого в неуправляемый код или наоборот.</span><span class="sxs-lookup"><span data-stu-id="1fa2d-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fa2d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1fa2d-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="1fa2d-105">Участники</span><span class="sxs-lookup"><span data-stu-id="1fa2d-105">Members</span></span>  
  
|<span data-ttu-id="1fa2d-106">Член</span><span class="sxs-lookup"><span data-stu-id="1fa2d-106">Member</span></span>|<span data-ttu-id="1fa2d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1fa2d-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="1fa2d-108">Переход происходит из-за вызова функции.</span><span class="sxs-lookup"><span data-stu-id="1fa2d-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="1fa2d-109">Переход происходит из-за возврата из функции.</span><span class="sxs-lookup"><span data-stu-id="1fa2d-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fa2d-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="1fa2d-110">Remarks</span></span>  
 <span data-ttu-id="1fa2d-111">Когда происходит переход, профилировщик получает [ICorProfilerCallback::ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) или [ICorProfilerCallback::UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) обратного вызова, которые предоставляет значение `COR_PRF_TRANSITION_REASON` перечисления, чтобы указать причину для перехода.</span><span class="sxs-lookup"><span data-stu-id="1fa2d-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fa2d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1fa2d-112">Requirements</span></span>  
 <span data-ttu-id="1fa2d-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fa2d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fa2d-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1fa2d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1fa2d-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fa2d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fa2d-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fa2d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
