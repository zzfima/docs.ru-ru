---
title: Метод ICorDebug::Terminate
ms.date: 03/30/2017
api_name:
- ICorDebug.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type:
- apiref
ms.openlocfilehash: 2d3f8360a1fb1164fd4e26f85246251409bee376
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788952"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="9f312-102">Метод ICorDebug::Terminate</span><span class="sxs-lookup"><span data-stu-id="9f312-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="9f312-103">Завершает объект `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="9f312-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9f312-104">`Terminate` не следует вызывать, пока не получен обратный вызов [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) для всех отлаживаемых процессов.</span><span class="sxs-lookup"><span data-stu-id="9f312-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f312-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f312-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="9f312-106">Заметки</span><span class="sxs-lookup"><span data-stu-id="9f312-106">Remarks</span></span>  
 <span data-ttu-id="9f312-107">`Terminate` должны вызываться, когда объект `ICorDebug` больше не нужен.</span><span class="sxs-lookup"><span data-stu-id="9f312-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f312-108">Требования</span><span class="sxs-lookup"><span data-stu-id="9f312-108">Requirements</span></span>  
 <span data-ttu-id="9f312-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f312-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f312-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f312-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f312-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f312-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f312-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f312-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f312-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="9f312-113">See also</span></span>

- [<span data-ttu-id="9f312-114">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="9f312-114">ICorDebug Interface</span></span>](icordebug-interface.md)
