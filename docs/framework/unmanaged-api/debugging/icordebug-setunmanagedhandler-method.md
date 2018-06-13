---
title: Метод ICorDebug::SetUnmanagedHandler
ms.date: 03/30/2017
api_name:
- ICorDebug.SetUnmanagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1be18d374bad07b590096acac985812c2e2ed9b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407588"
---
# <a name="icordebugsetunmanagedhandler-method"></a><span data-ttu-id="7ab81-102">Метод ICorDebug::SetUnmanagedHandler</span><span class="sxs-lookup"><span data-stu-id="7ab81-102">ICorDebug::SetUnmanagedHandler Method</span></span>
<span data-ttu-id="7ab81-103">Задает объект обработчика событий для неуправляемых событий.</span><span class="sxs-lookup"><span data-stu-id="7ab81-103">Specifies the event handler object for unmanaged events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ab81-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ab81-104">Syntax</span></span>  
  
```  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7ab81-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7ab81-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="7ab81-106">[in] Указатель на [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) , представляющий обработчик событий для неуправляемых событий.</span><span class="sxs-lookup"><span data-stu-id="7ab81-106">[in] A pointer to an [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) object that represents the event handler for unmanaged events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ab81-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="7ab81-107">Remarks</span></span>  
 <span data-ttu-id="7ab81-108">Обработчик события объекта для неуправляемого события необходимо задать после вызова [ICorDebug::Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) и перед любыми вызовами [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) или [ICorDebug::DebugActiveProcess ](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span><span class="sxs-lookup"><span data-stu-id="7ab81-108">The event handler object for unmanaged events must be set after a call to [ICorDebug::Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) and before any calls to [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) or [ICorDebug::DebugActiveProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span></span> <span data-ttu-id="7ab81-109">Тем не менее для обратной совместимости, вы не требуются для установки объект обработчика событий для неуправляемых событий до первого события отладчика машинного кода.</span><span class="sxs-lookup"><span data-stu-id="7ab81-109">However, for legacy purposes, you are not required to set the event handler object for unmanaged events until the first native debug event is raised.</span></span> <span data-ttu-id="7ab81-110">В частности Если `ICorDebug::CreateProcess` установлен флаг CREATE_SUSPENDED, события не могут быть доставлены, пока не будет возобновлена основной поток отладчика машинного кода.</span><span class="sxs-lookup"><span data-stu-id="7ab81-110">Specifically, if `ICorDebug::CreateProcess` has set the CREATE_SUSPENDED flag, native debug events cannot be dispatched until the main thread is resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ab81-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7ab81-111">Requirements</span></span>  
 <span data-ttu-id="7ab81-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ab81-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ab81-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ab81-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ab81-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ab81-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ab81-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ab81-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ab81-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7ab81-116">See Also</span></span>  
 [<span data-ttu-id="7ab81-117">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="7ab81-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
