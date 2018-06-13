---
title: Метод ICorDebugProcess6::ProcessStateChanged
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc5861762242412d7ab6f0c02f2b8f5c149f9453
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420183"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="ffbc7-102">Метод ICorDebugProcess6::ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="ffbc7-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="ffbc7-103">Уведомляет [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , на котором выполняется процесс.</span><span class="sxs-lookup"><span data-stu-id="ffbc7-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffbc7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ffbc7-104">Syntax</span></span>  
  
```  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ffbc7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ffbc7-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="ffbc7-106">[in] Член [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) перечисления</span><span class="sxs-lookup"><span data-stu-id="ffbc7-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ffbc7-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ffbc7-107">Remarks</span></span>  
 <span data-ttu-id="ffbc7-108">Отладчик вызывает этот метод для уведомления [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , на котором выполняется процесс.</span><span class="sxs-lookup"><span data-stu-id="ffbc7-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ffbc7-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="ffbc7-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffbc7-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ffbc7-110">Requirements</span></span>  
 <span data-ttu-id="ffbc7-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffbc7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffbc7-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ffbc7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ffbc7-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffbc7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffbc7-114">**Версии платформы .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffbc7-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffbc7-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ffbc7-115">See Also</span></span>  
 [<span data-ttu-id="ffbc7-116">Интерфейс ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="ffbc7-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="ffbc7-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ffbc7-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
