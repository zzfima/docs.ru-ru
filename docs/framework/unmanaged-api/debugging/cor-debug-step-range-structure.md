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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219685"
---
# <a name="cordebugsteprange-structure"></a><span data-ttu-id="24b0c-102">Структура COR_DEBUG_STEP_RANGE</span><span class="sxs-lookup"><span data-stu-id="24b0c-102">COR_DEBUG_STEP_RANGE Structure</span></span>
<span data-ttu-id="24b0c-103">Содержит сведения о смещении для диапазона кода.</span><span class="sxs-lookup"><span data-stu-id="24b0c-103">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="24b0c-104">Эта структура используется [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="24b0c-104">This structure is used by the [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24b0c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24b0c-105">Syntax</span></span>  
  
```  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="24b0c-106">Участники</span><span class="sxs-lookup"><span data-stu-id="24b0c-106">Members</span></span>  
  
|<span data-ttu-id="24b0c-107">Член</span><span class="sxs-lookup"><span data-stu-id="24b0c-107">Member</span></span>|<span data-ttu-id="24b0c-108">Описание</span><span class="sxs-lookup"><span data-stu-id="24b0c-108">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="24b0c-109">Смещение начала диапазона.</span><span class="sxs-lookup"><span data-stu-id="24b0c-109">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="24b0c-110">Смещение конца диапазона.</span><span class="sxs-lookup"><span data-stu-id="24b0c-110">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="24b0c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="24b0c-111">Requirements</span></span>  
 <span data-ttu-id="24b0c-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24b0c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24b0c-113">**Заголовок.** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="24b0c-113">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="24b0c-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24b0c-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="24b0c-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="24b0c-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="24b0c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="24b0c-116">See also</span></span>

- [<span data-ttu-id="24b0c-117">Метод StepRange</span><span class="sxs-lookup"><span data-stu-id="24b0c-117">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)
- [<span data-ttu-id="24b0c-118">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="24b0c-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="24b0c-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="24b0c-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
