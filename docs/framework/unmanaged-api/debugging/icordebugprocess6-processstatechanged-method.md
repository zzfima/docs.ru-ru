---
title: Метод ICorDebugProcess6::ProcessStateChanged
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb158b383745cd7e44c8fede6ddd43ae81ced2d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930765"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="140b2-102">Метод ICorDebugProcess6::ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="140b2-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="140b2-103">Уведомляет [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) о том, что процесс выполняется.</span><span class="sxs-lookup"><span data-stu-id="140b2-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="140b2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="140b2-104">Syntax</span></span>  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="140b2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="140b2-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="140b2-106">окне Член перечисления [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)</span><span class="sxs-lookup"><span data-stu-id="140b2-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="140b2-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="140b2-107">Remarks</span></span>  
 <span data-ttu-id="140b2-108">Отладчик вызывает этот метод, чтобы уведомить [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) о том, что процесс выполняется.</span><span class="sxs-lookup"><span data-stu-id="140b2-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="140b2-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="140b2-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="140b2-110">Требования</span><span class="sxs-lookup"><span data-stu-id="140b2-110">Requirements</span></span>  
 <span data-ttu-id="140b2-111">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="140b2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="140b2-112">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="140b2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="140b2-113">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="140b2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="140b2-114">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="140b2-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="140b2-115">См. также</span><span class="sxs-lookup"><span data-stu-id="140b2-115">See also</span></span>

- [<span data-ttu-id="140b2-116">Интерфейс ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="140b2-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="140b2-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="140b2-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
