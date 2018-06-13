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
ms.openlocfilehash: d5809221f2f31bc725c6a62fa5f8f91822f1c157
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407243"
---
# <a name="cordebugsteprange-structure"></a><span data-ttu-id="29682-102">Структура COR_DEBUG_STEP_RANGE</span><span class="sxs-lookup"><span data-stu-id="29682-102">COR_DEBUG_STEP_RANGE Structure</span></span>
<span data-ttu-id="29682-103">Содержит сведения о смещении для диапазона кода.</span><span class="sxs-lookup"><span data-stu-id="29682-103">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="29682-104">Эта структура используется [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="29682-104">This structure is used by the [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29682-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29682-105">Syntax</span></span>  
  
```  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="29682-106">Участники</span><span class="sxs-lookup"><span data-stu-id="29682-106">Members</span></span>  
  
|<span data-ttu-id="29682-107">Член</span><span class="sxs-lookup"><span data-stu-id="29682-107">Member</span></span>|<span data-ttu-id="29682-108">Описание</span><span class="sxs-lookup"><span data-stu-id="29682-108">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="29682-109">Смещение начала диапазона.</span><span class="sxs-lookup"><span data-stu-id="29682-109">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="29682-110">Смещение конца диапазона.</span><span class="sxs-lookup"><span data-stu-id="29682-110">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="29682-111">Требования</span><span class="sxs-lookup"><span data-stu-id="29682-111">Requirements</span></span>  
 <span data-ttu-id="29682-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29682-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29682-113">**Заголовок:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="29682-113">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="29682-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29682-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29682-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29682-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29682-116">См. также</span><span class="sxs-lookup"><span data-stu-id="29682-116">See Also</span></span>  
 [<span data-ttu-id="29682-117">Метод StepRange</span><span class="sxs-lookup"><span data-stu-id="29682-117">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)  
 [<span data-ttu-id="29682-118">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="29682-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="29682-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="29682-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
