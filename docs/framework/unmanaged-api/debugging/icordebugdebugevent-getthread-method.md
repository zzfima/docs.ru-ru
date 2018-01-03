---
title: "ICorDebugDebugEvent::Метод GetThread"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: faf1ace6c65f38e9a1d5b958b633c95dbcd3dcf8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="2b246-102">ICorDebugDebugEvent::Метод GetThread</span><span class="sxs-lookup"><span data-stu-id="2b246-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="2b246-103">Получает поток, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="2b246-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b246-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b246-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2b246-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2b246-105">Parameters</span></span>  
 <span data-ttu-id="2b246-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="2b246-106">ppThread</span></span>  
 <span data-ttu-id="2b246-107">[out] Указатель на адрес объекта ICorDebugThread, который представляет поток, на котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="2b246-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b246-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="2b246-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b246-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="2b246-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b246-110">Требования</span><span class="sxs-lookup"><span data-stu-id="2b246-110">Requirements</span></span>  
 <span data-ttu-id="2b246-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b246-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b246-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b246-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b246-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b246-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b246-114">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b246-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b246-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2b246-115">See Also</span></span>  
 [<span data-ttu-id="2b246-116">Интерфейс ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="2b246-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 [<span data-ttu-id="2b246-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2b246-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
