---
title: Метод ICorDebugProcess6::ProcessStateChanged
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68dae3839cfb4d04797d81bca41ee212a64cca51
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751566"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="f0d8b-102">Метод ICorDebugProcess6::ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="f0d8b-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="f0d8b-103">Уведомляет [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , на котором выполняется процесс.</span><span class="sxs-lookup"><span data-stu-id="f0d8b-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0d8b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0d8b-104">Syntax</span></span>  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0d8b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0d8b-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="f0d8b-106">[in] Является членом [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) перечисления</span><span class="sxs-lookup"><span data-stu-id="f0d8b-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0d8b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0d8b-107">Remarks</span></span>  
 <span data-ttu-id="f0d8b-108">Отладчик вызывает этот метод, чтобы уведомить [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , на котором выполняется процесс.</span><span class="sxs-lookup"><span data-stu-id="f0d8b-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0d8b-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="f0d8b-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0d8b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f0d8b-110">Requirements</span></span>  
 <span data-ttu-id="f0d8b-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0d8b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0d8b-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0d8b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0d8b-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0d8b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0d8b-114">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0d8b-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0d8b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f0d8b-115">See also</span></span>

- [<span data-ttu-id="f0d8b-116">Интерфейс ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="f0d8b-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="f0d8b-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f0d8b-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
