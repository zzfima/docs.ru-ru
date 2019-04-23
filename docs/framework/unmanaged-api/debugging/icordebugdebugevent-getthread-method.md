---
title: ICorDebugDebugEvent::Метод GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 103768918f67ca695a47c52b9cd97f24fb8d46ce
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081584"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="edcf4-102">ICorDebugDebugEvent::Метод GetThread</span><span class="sxs-lookup"><span data-stu-id="edcf4-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="edcf4-103">Получает поток, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="edcf4-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edcf4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="edcf4-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="edcf4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="edcf4-105">Parameters</span></span>  
 <span data-ttu-id="edcf4-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="edcf4-106">ppThread</span></span>  
 <span data-ttu-id="edcf4-107">[out] Указатель на адрес ICorDebugThread объект, представляющий поток, на котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="edcf4-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edcf4-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="edcf4-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="edcf4-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="edcf4-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edcf4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="edcf4-110">Requirements</span></span>  
 <span data-ttu-id="edcf4-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edcf4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edcf4-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="edcf4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="edcf4-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="edcf4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="edcf4-114">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edcf4-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edcf4-115">См. также</span><span class="sxs-lookup"><span data-stu-id="edcf4-115">See also</span></span>

- [<span data-ttu-id="edcf4-116">Интерфейс ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="edcf4-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="edcf4-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="edcf4-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
