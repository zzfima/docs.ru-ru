---
title: Интерфейс ICorDebugBlockingObjectEnum
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum
helpviewer_keywords:
- ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
ms.assetid: 208e5c2d-3f3f-404e-8b3c-7cccc14ddb16
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a23d21d0ed8c6a6a226d5e58eafb7bde65a4896
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645439"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="f39bd-102">Интерфейс ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="f39bd-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="f39bd-103">Предоставляет перечислитель для списка [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="f39bd-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="f39bd-104">Этот интерфейс является подклассом ICorDebugEnum-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f39bd-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f39bd-105">Методы</span><span class="sxs-lookup"><span data-stu-id="f39bd-105">Methods</span></span>  
  
|<span data-ttu-id="f39bd-106">Метод</span><span class="sxs-lookup"><span data-stu-id="f39bd-106">Method</span></span>|<span data-ttu-id="f39bd-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f39bd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f39bd-108">Метод Next</span><span class="sxs-lookup"><span data-stu-id="f39bd-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="f39bd-109">Перечисляет список [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="f39bd-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f39bd-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="f39bd-110">Remarks</span></span>  
 <span data-ttu-id="f39bd-111">Каждая структура `CorDebugBlockingObject` представляет объект, блокирующий поток.</span><span class="sxs-lookup"><span data-stu-id="f39bd-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f39bd-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="f39bd-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f39bd-113">Требования</span><span class="sxs-lookup"><span data-stu-id="f39bd-113">Requirements</span></span>  
 <span data-ttu-id="f39bd-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f39bd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f39bd-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f39bd-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f39bd-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f39bd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f39bd-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f39bd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f39bd-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f39bd-118">See also</span></span>

- [<span data-ttu-id="f39bd-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f39bd-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f39bd-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="f39bd-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
