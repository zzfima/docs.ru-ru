---
title: ICorDebugDebugEvent::Метод GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: 66b4abc4bebfbbde2e6a6b25d2bc0e88839a363f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136649"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="15d7d-102">ICorDebugDebugEvent::Метод GetThread</span><span class="sxs-lookup"><span data-stu-id="15d7d-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="15d7d-103">Получает поток, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="15d7d-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15d7d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15d7d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15d7d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="15d7d-105">Parameters</span></span>  
 <span data-ttu-id="15d7d-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="15d7d-106">ppThread</span></span>  
 <span data-ttu-id="15d7d-107">заполняет Указатель на адрес объекта ICorDebugThread, представляющий поток, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="15d7d-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15d7d-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="15d7d-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="15d7d-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="15d7d-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15d7d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="15d7d-110">Requirements</span></span>  
 <span data-ttu-id="15d7d-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15d7d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15d7d-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15d7d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15d7d-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15d7d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15d7d-114">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15d7d-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15d7d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="15d7d-115">See also</span></span>

- [<span data-ttu-id="15d7d-116">Интерфейс ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="15d7d-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="15d7d-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="15d7d-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
