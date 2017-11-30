---
title: "Метод ICorDebugExceptionDebugEvent::GetFlags"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 33534a65f7a58981abd3df324b5fe005a06669d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="62c93-102">Метод ICorDebugExceptionDebugEvent::GetFlags</span><span class="sxs-lookup"><span data-stu-id="62c93-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="62c93-103">Возвращает флаг, указывающий, может ли исключение быть перехвачено.</span><span class="sxs-lookup"><span data-stu-id="62c93-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62c93-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62c93-104">Syntax</span></span>  
  
```  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62c93-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="62c93-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="62c93-106">[out] Указатель на [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) значение, указывающее, может ли исключение быть перехвачено.</span><span class="sxs-lookup"><span data-stu-id="62c93-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62c93-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="62c93-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62c93-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="62c93-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62c93-109">Требования</span><span class="sxs-lookup"><span data-stu-id="62c93-109">Requirements</span></span>  
 <span data-ttu-id="62c93-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62c93-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62c93-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62c93-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62c93-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62c93-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62c93-113">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62c93-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62c93-114">См. также</span><span class="sxs-lookup"><span data-stu-id="62c93-114">See Also</span></span>  
 [<span data-ttu-id="62c93-115">Интерфейс ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="62c93-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 [<span data-ttu-id="62c93-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="62c93-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
