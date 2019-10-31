---
title: Метод ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: b6bfd258f35f19719be5e5169a1edc22a358371c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123375"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="9277e-102">Метод ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode</span><span class="sxs-lookup"><span data-stu-id="9277e-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="9277e-103">[Поддерживается в .NET Framework 4,6 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="9277e-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="9277e-104">Включает или отключает определенные типы обратных вызовов исключений [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9277e-104">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9277e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9277e-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9277e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9277e-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="9277e-107">[in]</span><span class="sxs-lookup"><span data-stu-id="9277e-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9277e-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="9277e-108">Remarks</span></span>  
 <span data-ttu-id="9277e-109">Если `enableExceptionsOutsideOfJMC` имеет значение `false`:</span><span class="sxs-lookup"><span data-stu-id="9277e-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
- <span data-ttu-id="9277e-110">Исключение DEBUG_EXCEPTION_FIRST_CHANCE не приведет к обратному вызову отладчика.</span><span class="sxs-lookup"><span data-stu-id="9277e-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
- <span data-ttu-id="9277e-111">Исключение DEBUG_EXCEPTION_CATCH_HANDLER_FOUND не приведет к обратному вызову отладчика, если исключение никогда не переключается в пользовательский код (то есть путь от источника исключения к обработчику исключений не имеет методов, помеченных как Жустмикоде или JMC).</span><span class="sxs-lookup"><span data-stu-id="9277e-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="9277e-112">Значением свойства `enableExceptionsOutsideOfJMC` по умолчанию является `true`.</span><span class="sxs-lookup"><span data-stu-id="9277e-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9277e-113">Требования</span><span class="sxs-lookup"><span data-stu-id="9277e-113">Requirements</span></span>  
 <span data-ttu-id="9277e-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9277e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9277e-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9277e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9277e-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9277e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9277e-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9277e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9277e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="9277e-118">See also</span></span>

- [<span data-ttu-id="9277e-119">Интерфейс ICorDebugProcess8</span><span class="sxs-lookup"><span data-stu-id="9277e-119">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)
- [<span data-ttu-id="9277e-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9277e-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
