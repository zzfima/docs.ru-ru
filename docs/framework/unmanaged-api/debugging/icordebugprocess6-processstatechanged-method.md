---
title: Метод ICorDebugProcess6::ProcessStateChanged
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb134b7d188c2fb966b53e4520a7fb825f11e428
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612051"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="d8d7c-102">Метод ICorDebugProcess6::ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="d8d7c-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="d8d7c-103">Уведомляет [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , на котором выполняется процесс.</span><span class="sxs-lookup"><span data-stu-id="d8d7c-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8d7c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8d7c-104">Syntax</span></span>  
  
```  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d8d7c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d8d7c-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="d8d7c-106">[in] Является членом [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) перечисления</span><span class="sxs-lookup"><span data-stu-id="d8d7c-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8d7c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="d8d7c-107">Remarks</span></span>  
 <span data-ttu-id="d8d7c-108">Отладчик вызывает этот метод, чтобы уведомить [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , на котором выполняется процесс.</span><span class="sxs-lookup"><span data-stu-id="d8d7c-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8d7c-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="d8d7c-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8d7c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d8d7c-110">Requirements</span></span>  
 <span data-ttu-id="d8d7c-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8d7c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8d7c-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8d7c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8d7c-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8d7c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8d7c-114">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8d7c-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8d7c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d8d7c-115">See also</span></span>
- [<span data-ttu-id="d8d7c-116">Интерфейс ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="d8d7c-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="d8d7c-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d8d7c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
