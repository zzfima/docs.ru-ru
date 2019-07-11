---
title: Метод ICorDebugThread::CreateStepper
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95a00e8646589e7897636c1698b7c2647cd233fd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771802"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="bbcc5-102">Метод ICorDebugThread::CreateStepper</span><span class="sxs-lookup"><span data-stu-id="bbcc5-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="bbcc5-103">Создает объект, позволяющий пошаговое выполнение активного кадра ICorDebugThread ICorDebugStepper.</span><span class="sxs-lookup"><span data-stu-id="bbcc5-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbcc5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bbcc5-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbcc5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bbcc5-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="bbcc5-106">[out] Указатель на адрес `ICorDebugStepper` объект, который позволяет пошаговое выполнение активного кадра для данного потока.</span><span class="sxs-lookup"><span data-stu-id="bbcc5-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbcc5-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="bbcc5-107">Remarks</span></span>  
 <span data-ttu-id="bbcc5-108">Возможно, активного кадра неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="bbcc5-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="bbcc5-109">`ICorDebugStepper` Интерфейс необходимо использовать для фактического пошагового выполнения.</span><span class="sxs-lookup"><span data-stu-id="bbcc5-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbcc5-110">Требования</span><span class="sxs-lookup"><span data-stu-id="bbcc5-110">Requirements</span></span>  
 <span data-ttu-id="bbcc5-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbcc5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbcc5-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bbcc5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bbcc5-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbcc5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbcc5-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbcc5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
