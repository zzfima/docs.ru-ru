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
ms.openlocfilehash: 11d5e2eb5e2743fca4876ed09add79be3eba514f
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274207"
---
# <a name="cor_debug_step_range-structure"></a><span data-ttu-id="b8977-102">Структура COR_DEBUG_STEP_RANGE</span><span class="sxs-lookup"><span data-stu-id="b8977-102">COR_DEBUG_STEP_RANGE Structure</span></span>
<span data-ttu-id="b8977-103">Содержит сведения о смещении для диапазона кода.</span><span class="sxs-lookup"><span data-stu-id="b8977-103">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="b8977-104">Эта структура используется методом [ICorDebugStepper:: степранже](icordebugstepper-steprange-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b8977-104">This structure is used by the [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8977-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b8977-105">Syntax</span></span>  
  
```cpp  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="b8977-106">Участники</span><span class="sxs-lookup"><span data-stu-id="b8977-106">Members</span></span>  
  
|<span data-ttu-id="b8977-107">Член</span><span class="sxs-lookup"><span data-stu-id="b8977-107">Member</span></span>|<span data-ttu-id="b8977-108">Описание</span><span class="sxs-lookup"><span data-stu-id="b8977-108">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="b8977-109">Смещение начала диапазона.</span><span class="sxs-lookup"><span data-stu-id="b8977-109">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="b8977-110">Смещение конца диапазона.</span><span class="sxs-lookup"><span data-stu-id="b8977-110">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b8977-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b8977-111">Requirements</span></span>  
 <span data-ttu-id="b8977-112">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8977-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8977-113">**Заголовок.** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="b8977-113">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="b8977-114">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="b8977-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8977-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8977-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8977-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b8977-116">See also</span></span>

- [<span data-ttu-id="b8977-117">Метод StepRange</span><span class="sxs-lookup"><span data-stu-id="b8977-117">StepRange Method</span></span>](icordebugstepper-steprange-method.md)
- [<span data-ttu-id="b8977-118">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="b8977-118">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="b8977-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="b8977-119">Debugging</span></span>](index.md)
