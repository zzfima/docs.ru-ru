---
title: "Метод ICorDebug::SetUnmanagedHandler"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.SetUnmanagedHandler
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 658cbaeb10496ccd88e0abb3d2174289a820c2e6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugsetunmanagedhandler-method"></a><span data-ttu-id="6c5f2-102">Метод ICorDebug::SetUnmanagedHandler</span><span class="sxs-lookup"><span data-stu-id="6c5f2-102">ICorDebug::SetUnmanagedHandler Method</span></span>
<span data-ttu-id="6c5f2-103">Задает объект обработчика событий для неуправляемых событий.</span><span class="sxs-lookup"><span data-stu-id="6c5f2-103">Specifies the event handler object for unmanaged events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c5f2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c5f2-104">Syntax</span></span>  
  
```  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6c5f2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6c5f2-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="6c5f2-106">[in] Указатель на [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) , представляющий обработчик событий для неуправляемых событий.</span><span class="sxs-lookup"><span data-stu-id="6c5f2-106">[in] A pointer to an [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) object that represents the event handler for unmanaged events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c5f2-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="6c5f2-107">Remarks</span></span>  
 <span data-ttu-id="6c5f2-108">Обработчик события объекта для неуправляемого события необходимо задать после вызова [ICorDebug::Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) и перед любыми вызовами [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) или [ICorDebug::DebugActiveProcess ](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span><span class="sxs-lookup"><span data-stu-id="6c5f2-108">The event handler object for unmanaged events must be set after a call to [ICorDebug::Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) and before any calls to [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) or [ICorDebug::DebugActiveProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span></span> <span data-ttu-id="6c5f2-109">Тем не менее для обратной совместимости, вы не требуются для установки объект обработчика событий для неуправляемых событий до первого события отладчика машинного кода.</span><span class="sxs-lookup"><span data-stu-id="6c5f2-109">However, for legacy purposes, you are not required to set the event handler object for unmanaged events until the first native debug event is raised.</span></span> <span data-ttu-id="6c5f2-110">В частности Если `ICorDebug::CreateProcess` установлен флаг CREATE_SUSPENDED, события не могут быть доставлены, пока не будет возобновлена основной поток отладчика машинного кода.</span><span class="sxs-lookup"><span data-stu-id="6c5f2-110">Specifically, if `ICorDebug::CreateProcess` has set the CREATE_SUSPENDED flag, native debug events cannot be dispatched until the main thread is resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c5f2-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6c5f2-111">Requirements</span></span>  
 <span data-ttu-id="6c5f2-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c5f2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c5f2-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c5f2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c5f2-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c5f2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c5f2-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c5f2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c5f2-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6c5f2-116">See Also</span></span>  
 [<span data-ttu-id="6c5f2-117">ICorDebug-интерфейс</span><span class="sxs-lookup"><span data-stu-id="6c5f2-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
