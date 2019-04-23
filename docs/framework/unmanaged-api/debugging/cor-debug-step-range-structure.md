---
title: Структура COR_DEBUG_STEP_RANGE
ms.date: 03/30/2017
api_name:
- COR_DEBUG_STEP_RANGE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_STEP_RANGE
helpviewer_keywords:
- COR_DEBUG_STEP_RANGE structure [.NET Framework debugging]
ms.assetid: 8809d00e-beaa-4dcf-b4e8-e89d0a5406b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57d7c3256d7b52a4e55dbb5bc420b0438983d2f2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59219685"
---
# <a name="cordebugsteprange-structure"></a><span data-ttu-id="12d5e-102">Структура COR_DEBUG_STEP_RANGE</span><span class="sxs-lookup"><span data-stu-id="12d5e-102">COR_DEBUG_STEP_RANGE Structure</span></span>
<span data-ttu-id="12d5e-103">Содержит сведения о смещении для диапазона кода.</span><span class="sxs-lookup"><span data-stu-id="12d5e-103">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="12d5e-104">Эта структура используется [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="12d5e-104">This structure is used by the [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12d5e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12d5e-105">Syntax</span></span>  
  
```  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="12d5e-106">Участники</span><span class="sxs-lookup"><span data-stu-id="12d5e-106">Members</span></span>  
  
|<span data-ttu-id="12d5e-107">Член</span><span class="sxs-lookup"><span data-stu-id="12d5e-107">Member</span></span>|<span data-ttu-id="12d5e-108">Описание</span><span class="sxs-lookup"><span data-stu-id="12d5e-108">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="12d5e-109">Смещение начала диапазона.</span><span class="sxs-lookup"><span data-stu-id="12d5e-109">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="12d5e-110">Смещение конца диапазона.</span><span class="sxs-lookup"><span data-stu-id="12d5e-110">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="12d5e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="12d5e-111">Requirements</span></span>  
 <span data-ttu-id="12d5e-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12d5e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12d5e-113">**Заголовок.** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="12d5e-113">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="12d5e-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12d5e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12d5e-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12d5e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12d5e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="12d5e-116">See also</span></span>

- [<span data-ttu-id="12d5e-117">Метод StepRange</span><span class="sxs-lookup"><span data-stu-id="12d5e-117">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)
- [<span data-ttu-id="12d5e-118">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="12d5e-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="12d5e-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="12d5e-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
