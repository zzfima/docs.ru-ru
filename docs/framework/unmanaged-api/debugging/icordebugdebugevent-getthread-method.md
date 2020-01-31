---
title: Метод ICorDebugDebugEvent::GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: 0900ac2ae5bcf2141e720dad6efdf68d4fafaccc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793534"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="e6c2b-102">Метод ICorDebugDebugEvent::GetThread</span><span class="sxs-lookup"><span data-stu-id="e6c2b-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="e6c2b-103">Получает поток, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6c2b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6c2b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6c2b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e6c2b-105">Parameters</span></span>  
 <span data-ttu-id="e6c2b-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="e6c2b-106">ppThread</span></span>  
 <span data-ttu-id="e6c2b-107">[выходной] Указатель на адрес объекта ICorDebugThread, представляющего поток, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6c2b-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="e6c2b-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6c2b-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6c2b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e6c2b-110">Requirements</span></span>  
 <span data-ttu-id="e6c2b-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6c2b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6c2b-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6c2b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6c2b-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6c2b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6c2b-114">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6c2b-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6c2b-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="e6c2b-115">See also</span></span>

- [<span data-ttu-id="e6c2b-116">Интерфейс ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="e6c2b-116">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="e6c2b-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e6c2b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
