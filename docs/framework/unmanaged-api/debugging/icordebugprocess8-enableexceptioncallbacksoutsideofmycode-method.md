---
title: "Метод ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e7de3622498e8417a961e0d4708c53527a833ef2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="83cea-102">Метод ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode</span><span class="sxs-lookup"><span data-stu-id="83cea-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="83cea-103">[Поддерживается в [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="83cea-103">[Supported in the [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="83cea-104">Включает или отключает определенные типы [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) обратных вызовов исключения.</span><span class="sxs-lookup"><span data-stu-id="83cea-104">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83cea-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83cea-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83cea-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="83cea-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="83cea-107">[in]</span><span class="sxs-lookup"><span data-stu-id="83cea-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83cea-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="83cea-108">Remarks</span></span>  
 <span data-ttu-id="83cea-109">Если `enableExceptionsOutsideOfJMC` имеет значение `false`:</span><span class="sxs-lookup"><span data-stu-id="83cea-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
-   <span data-ttu-id="83cea-110">Исключение DEBUG_EXCEPTION_FIRST_CHANCE не приведет к с помощью обратного вызова отладчика.</span><span class="sxs-lookup"><span data-stu-id="83cea-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
-   <span data-ttu-id="83cea-111">Исключение DEBUG_EXCEPTION_CATCH_HANDLER_FOUND не приведет обратный вызов в отладчик, если исключение никогда не попадает в пользовательский код (то есть путь от источника исключения в обработчик исключений не имеет методов помеченных как JustMyCode или JMC).</span><span class="sxs-lookup"><span data-stu-id="83cea-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="83cea-112">Значением свойства `enableExceptionsOutsideOfJMC` по умолчанию является `true`.</span><span class="sxs-lookup"><span data-stu-id="83cea-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83cea-113">Требования</span><span class="sxs-lookup"><span data-stu-id="83cea-113">Requirements</span></span>  
 <span data-ttu-id="83cea-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83cea-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83cea-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83cea-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83cea-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83cea-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83cea-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83cea-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83cea-118">См. также</span><span class="sxs-lookup"><span data-stu-id="83cea-118">See Also</span></span>  
 [<span data-ttu-id="83cea-119">Интерфейс ICorDebugProcess8</span><span class="sxs-lookup"><span data-stu-id="83cea-119">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 [<span data-ttu-id="83cea-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="83cea-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
