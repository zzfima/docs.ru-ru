---
title: Интерфейс ICorDebugModuleEnum
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum
helpviewer_keywords:
- ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 2fb93cd6-6d47-4fdc-a9a0-047726fd03a1
topic_type:
- apiref
ms.openlocfilehash: b019c198635373fa6aaea01914dc9747b7486ae0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792881"
---
# <a name="icordebugmoduleenum-interface"></a><span data-ttu-id="3984d-102">Интерфейс ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="3984d-102">ICorDebugModuleEnum Interface</span></span>

<span data-ttu-id="3984d-103">Реализует методы ICorDebugEnum и перечисляет ICorDebugModule массивы.</span><span class="sxs-lookup"><span data-stu-id="3984d-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3984d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="3984d-104">Methods</span></span>  
  
|<span data-ttu-id="3984d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="3984d-105">Method</span></span>|<span data-ttu-id="3984d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3984d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3984d-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="3984d-107">Next Method</span></span>](icordebugmoduleenum-next-method.md)|<span data-ttu-id="3984d-108">Возвращает указанное число экземпляров `ICorDebugModule` из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="3984d-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3984d-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="3984d-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3984d-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="3984d-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3984d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3984d-111">Requirements</span></span>  
 <span data-ttu-id="3984d-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3984d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3984d-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3984d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3984d-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3984d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3984d-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3984d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3984d-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="3984d-116">See also</span></span>

- [<span data-ttu-id="3984d-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3984d-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
