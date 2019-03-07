---
title: Метод ICorDebugProcess6::ProcessStateChanged
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f25e25f94dae1a959cbb813a44a7f4f09eaa69c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474596"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="e8cab-102">Метод ICorDebugProcess6::ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="e8cab-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="e8cab-103">Уведомляет [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , на котором выполняется процесс.</span><span class="sxs-lookup"><span data-stu-id="e8cab-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8cab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8cab-104">Syntax</span></span>  
  
```  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8cab-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e8cab-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="e8cab-106">[in] Является членом [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) перечисления</span><span class="sxs-lookup"><span data-stu-id="e8cab-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8cab-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="e8cab-107">Remarks</span></span>  
 <span data-ttu-id="e8cab-108">Отладчик вызывает этот метод, чтобы уведомить [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , на котором выполняется процесс.</span><span class="sxs-lookup"><span data-stu-id="e8cab-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e8cab-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="e8cab-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8cab-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e8cab-110">Requirements</span></span>  
 <span data-ttu-id="e8cab-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8cab-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8cab-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8cab-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8cab-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8cab-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8cab-114">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8cab-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8cab-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e8cab-115">See also</span></span>
- [<span data-ttu-id="e8cab-116">Интерфейс ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="e8cab-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="e8cab-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e8cab-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
