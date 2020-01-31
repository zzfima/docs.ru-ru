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
ms.openlocfilehash: 1c3c311fd431b6c0b18af3d6516973b2471cfabd
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867066"
---
# <a name="cor_prf_transition_reason-enumeration"></a><span data-ttu-id="83a26-102">Перечисление COR_PRF_TRANSITION_REASON</span><span class="sxs-lookup"><span data-stu-id="83a26-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="83a26-103">Указывает причину перехода из управляемого в неуправляемый код или наоборот.</span><span class="sxs-lookup"><span data-stu-id="83a26-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83a26-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83a26-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="83a26-105">Участники</span><span class="sxs-lookup"><span data-stu-id="83a26-105">Members</span></span>  
  
|<span data-ttu-id="83a26-106">Член</span><span class="sxs-lookup"><span data-stu-id="83a26-106">Member</span></span>|<span data-ttu-id="83a26-107">Описание</span><span class="sxs-lookup"><span data-stu-id="83a26-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="83a26-108">Переход происходит из-за вызова функции.</span><span class="sxs-lookup"><span data-stu-id="83a26-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="83a26-109">Переход происходит из-за возврата из функции.</span><span class="sxs-lookup"><span data-stu-id="83a26-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83a26-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="83a26-110">Remarks</span></span>  
 <span data-ttu-id="83a26-111">Когда происходит переход, профилировщик получает обратный вызов [ICorProfilerCallback:: манажедтаунманажедтранситион](icorprofilercallback-managedtounmanagedtransition-method.md) или [ICorProfilerCallback:: унманажедтоманажедтранситион](icorprofilercallback-unmanagedtomanagedtransition-method.md) , который предоставляет значение перечисления `COR_PRF_TRANSITION_REASON`, чтобы указать причину перехода.</span><span class="sxs-lookup"><span data-stu-id="83a26-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83a26-112">Требования</span><span class="sxs-lookup"><span data-stu-id="83a26-112">Requirements</span></span>  
 <span data-ttu-id="83a26-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83a26-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83a26-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="83a26-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="83a26-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83a26-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83a26-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83a26-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
