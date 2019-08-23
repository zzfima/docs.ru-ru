---
title: ICorDebugDebugEvent::Метод GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f85dccd5b59610c52adcf685828984c9344fd49
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911286"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="55c36-102">ICorDebugDebugEvent::Метод GetThread</span><span class="sxs-lookup"><span data-stu-id="55c36-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="55c36-103">Получает поток, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="55c36-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55c36-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55c36-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55c36-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="55c36-105">Parameters</span></span>  
 <span data-ttu-id="55c36-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="55c36-106">ppThread</span></span>  
 <span data-ttu-id="55c36-107">заполняет Указатель на адрес объекта ICorDebugThread, представляющий поток, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="55c36-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55c36-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="55c36-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55c36-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="55c36-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55c36-110">Требования</span><span class="sxs-lookup"><span data-stu-id="55c36-110">Requirements</span></span>  
 <span data-ttu-id="55c36-111">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55c36-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55c36-112">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="55c36-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55c36-113">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="55c36-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55c36-114">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55c36-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c36-115">См. также</span><span class="sxs-lookup"><span data-stu-id="55c36-115">See also</span></span>

- [<span data-ttu-id="55c36-116">Интерфейс ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="55c36-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="55c36-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="55c36-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
