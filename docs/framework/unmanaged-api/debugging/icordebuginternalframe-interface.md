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
ms.openlocfilehash: b1ee5a155afa4e33340108e7295adef2309986cf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122707"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="a2e7b-102">Интерфейс ICorDebugInternalFrame</span><span class="sxs-lookup"><span data-stu-id="a2e7b-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="a2e7b-103">Представляет внутренний кадр среды выполнения в стеке.</span><span class="sxs-lookup"><span data-stu-id="a2e7b-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="a2e7b-104">Этот интерфейс является подклассом интерфейса ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="a2e7b-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a2e7b-105">Методы</span><span class="sxs-lookup"><span data-stu-id="a2e7b-105">Methods</span></span>  
  
|<span data-ttu-id="a2e7b-106">Метод</span><span class="sxs-lookup"><span data-stu-id="a2e7b-106">Method</span></span>|<span data-ttu-id="a2e7b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a2e7b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a2e7b-108">Метод GetFrameType</span><span class="sxs-lookup"><span data-stu-id="a2e7b-108">GetFrameType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="a2e7b-109">Возвращает тип этого внутреннего кадра.</span><span class="sxs-lookup"><span data-stu-id="a2e7b-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2e7b-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="a2e7b-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a2e7b-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="a2e7b-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2e7b-112">Требования</span><span class="sxs-lookup"><span data-stu-id="a2e7b-112">Requirements</span></span>  
 <span data-ttu-id="a2e7b-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2e7b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2e7b-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2e7b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2e7b-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2e7b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2e7b-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2e7b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2e7b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="a2e7b-117">See also</span></span>

- [<span data-ttu-id="a2e7b-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a2e7b-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
