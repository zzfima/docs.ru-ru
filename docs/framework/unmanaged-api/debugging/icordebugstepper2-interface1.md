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
ms.openlocfilehash: d154cf10e60935d12653c70875323079f92ae288
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791733"
---
# <a name="icordebugstepper2-interface"></a><span data-ttu-id="4b95e-102">Интерфейс ICorDebugStepper2</span><span class="sxs-lookup"><span data-stu-id="4b95e-102">ICorDebugStepper2 Interface</span></span>
<span data-ttu-id="4b95e-103">Обеспечивает поддержку отладки "только мой код" (JMC).</span><span class="sxs-lookup"><span data-stu-id="4b95e-103">Provides support for just my code (JMC) debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4b95e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4b95e-104">Methods</span></span>  
  
|<span data-ttu-id="4b95e-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4b95e-105">Method</span></span>|<span data-ttu-id="4b95e-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4b95e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4b95e-107">Метод SetJMC</span><span class="sxs-lookup"><span data-stu-id="4b95e-107">SetJMC Method</span></span>](icordebugstepper2-setjmc-method.md)|<span data-ttu-id="4b95e-108">Задает значение, указывающее, следует ли выполнить шаги для этого параметра ICorDebugStepper только с помощью кода, созданного разработчиком приложения.</span><span class="sxs-lookup"><span data-stu-id="4b95e-108">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b95e-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="4b95e-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4b95e-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="4b95e-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b95e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4b95e-111">Requirements</span></span>  
 <span data-ttu-id="4b95e-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b95e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b95e-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b95e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b95e-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b95e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b95e-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b95e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b95e-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="4b95e-116">See also</span></span>

- [<span data-ttu-id="4b95e-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4b95e-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
