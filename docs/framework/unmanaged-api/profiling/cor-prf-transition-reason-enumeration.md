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
ms.openlocfilehash: 6d8b408675127cde399a8346f2b9734a0e038cb5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427142"
---
# <a name="cor_prf_transition_reason-enumeration"></a><span data-ttu-id="29a74-102">Перечисление COR_PRF_TRANSITION_REASON</span><span class="sxs-lookup"><span data-stu-id="29a74-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="29a74-103">Указывает причину перехода из управляемого в неуправляемый код или наоборот.</span><span class="sxs-lookup"><span data-stu-id="29a74-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29a74-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29a74-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="29a74-105">Члены</span><span class="sxs-lookup"><span data-stu-id="29a74-105">Members</span></span>  
  
|<span data-ttu-id="29a74-106">Член</span><span class="sxs-lookup"><span data-stu-id="29a74-106">Member</span></span>|<span data-ttu-id="29a74-107">Описание</span><span class="sxs-lookup"><span data-stu-id="29a74-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="29a74-108">Переход происходит из-за вызова функции.</span><span class="sxs-lookup"><span data-stu-id="29a74-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="29a74-109">Переход происходит из-за возврата из функции.</span><span class="sxs-lookup"><span data-stu-id="29a74-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29a74-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="29a74-110">Remarks</span></span>  
 <span data-ttu-id="29a74-111">Когда происходит переход, профилировщик получает обратный вызов [ICorProfilerCallback:: манажедтаунманажедтранситион](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) или [ICorProfilerCallback:: унманажедтоманажедтранситион](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) , который предоставляет значение перечисления `COR_PRF_TRANSITION_REASON`, чтобы указать причину перехода.</span><span class="sxs-lookup"><span data-stu-id="29a74-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29a74-112">Требования</span><span class="sxs-lookup"><span data-stu-id="29a74-112">Requirements</span></span>  
 <span data-ttu-id="29a74-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29a74-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29a74-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="29a74-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="29a74-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29a74-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29a74-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29a74-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
