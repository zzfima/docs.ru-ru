---
title: Интерфейс ICorDebugStepper2
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2
helpviewer_keywords:
- ICorDebugStepper2 interface [.NET Framework debugging]
ms.assetid: 7a191c2a-95ea-4d47-83b0-44de2b632d63
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 69adabbe5bb607e00d383c8bd80d9e150608890e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970419"
---
# <a name="icordebugstepper2-interface"></a><span data-ttu-id="220e1-102">Интерфейс ICorDebugStepper2</span><span class="sxs-lookup"><span data-stu-id="220e1-102">ICorDebugStepper2 Interface</span></span>
<span data-ttu-id="220e1-103">Обеспечивает поддержку Отладка только собственного кода (JMC).</span><span class="sxs-lookup"><span data-stu-id="220e1-103">Provides support for just my code (JMC) debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="220e1-104">Методы</span><span class="sxs-lookup"><span data-stu-id="220e1-104">Methods</span></span>  
  
|<span data-ttu-id="220e1-105">Метод</span><span class="sxs-lookup"><span data-stu-id="220e1-105">Method</span></span>|<span data-ttu-id="220e1-106">Описание</span><span class="sxs-lookup"><span data-stu-id="220e1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="220e1-107">Метод SetJMC</span><span class="sxs-lookup"><span data-stu-id="220e1-107">SetJMC Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-setjmc-method.md)|<span data-ttu-id="220e1-108">Задает значение, указывающее ли ICorDebugStepper проходит только через код, который создается разработчиком приложения.</span><span class="sxs-lookup"><span data-stu-id="220e1-108">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="220e1-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="220e1-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="220e1-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="220e1-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="220e1-111">Требования</span><span class="sxs-lookup"><span data-stu-id="220e1-111">Requirements</span></span>  
 <span data-ttu-id="220e1-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="220e1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="220e1-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="220e1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="220e1-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="220e1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="220e1-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="220e1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="220e1-116">См. также</span><span class="sxs-lookup"><span data-stu-id="220e1-116">See also</span></span>
- [<span data-ttu-id="220e1-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="220e1-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
