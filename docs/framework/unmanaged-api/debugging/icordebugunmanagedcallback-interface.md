---
title: Интерфейс ICorDebugUnmanagedCallback
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback
helpviewer_keywords:
- ICorDebugUnmanagedCallback interface [.NET Framework debugging]
ms.assetid: bc71cbca-7d73-40e5-84dd-2109fade3c2a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a34454e7e007b4eba557c712cb824362aa5047c3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952979"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="77871-102">Интерфейс ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="77871-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="77871-103">Предоставляет уведомления о событиях машинного кода, которые не связаны напрямую с общеязыковой средой выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="77871-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="77871-104">Методы</span><span class="sxs-lookup"><span data-stu-id="77871-104">Methods</span></span>  
  
|<span data-ttu-id="77871-105">Метод</span><span class="sxs-lookup"><span data-stu-id="77871-105">Method</span></span>|<span data-ttu-id="77871-106">Описание</span><span class="sxs-lookup"><span data-stu-id="77871-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="77871-107">Метод DebugEvent</span><span class="sxs-lookup"><span data-stu-id="77871-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="77871-108">Уведомляет отладчик о срабатывании собственного события.</span><span class="sxs-lookup"><span data-stu-id="77871-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77871-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="77871-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="77871-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="77871-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77871-111">Требования</span><span class="sxs-lookup"><span data-stu-id="77871-111">Requirements</span></span>  
 <span data-ttu-id="77871-112">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77871-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77871-113">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="77871-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77871-114">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="77871-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77871-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77871-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77871-116">См. также</span><span class="sxs-lookup"><span data-stu-id="77871-116">See also</span></span>

- [<span data-ttu-id="77871-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="77871-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
