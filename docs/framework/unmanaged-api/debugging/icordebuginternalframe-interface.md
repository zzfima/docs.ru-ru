---
title: Интерфейс ICorDebugInternalFrame
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame
helpviewer_keywords:
- ICorDebugInternalFrame interface [.NET Framework debugging]
ms.assetid: bb4772ca-0d54-4185-b738-7a6ffe9ea85a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f16b4628215bee2410708edeb337b41fbdc0311
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109828"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="9a6cf-102">Интерфейс ICorDebugInternalFrame</span><span class="sxs-lookup"><span data-stu-id="9a6cf-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="9a6cf-103">Представляет кадр внутренней среды выполнения в стеке.</span><span class="sxs-lookup"><span data-stu-id="9a6cf-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="9a6cf-104">Этот интерфейс является подклассом ICorDebugFrame-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="9a6cf-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9a6cf-105">Методы</span><span class="sxs-lookup"><span data-stu-id="9a6cf-105">Methods</span></span>  
  
|<span data-ttu-id="9a6cf-106">Метод</span><span class="sxs-lookup"><span data-stu-id="9a6cf-106">Method</span></span>|<span data-ttu-id="9a6cf-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9a6cf-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9a6cf-108">Метод GetFrameType</span><span class="sxs-lookup"><span data-stu-id="9a6cf-108">GetFrameType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="9a6cf-109">Получает тип данного внутреннего фрейма.</span><span class="sxs-lookup"><span data-stu-id="9a6cf-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a6cf-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="9a6cf-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a6cf-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="9a6cf-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a6cf-112">Требования</span><span class="sxs-lookup"><span data-stu-id="9a6cf-112">Requirements</span></span>  
 <span data-ttu-id="9a6cf-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a6cf-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a6cf-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a6cf-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a6cf-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a6cf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a6cf-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a6cf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a6cf-117">См. также</span><span class="sxs-lookup"><span data-stu-id="9a6cf-117">See also</span></span>

- [<span data-ttu-id="9a6cf-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9a6cf-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
