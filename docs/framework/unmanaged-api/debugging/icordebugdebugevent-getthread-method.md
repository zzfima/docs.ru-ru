---
title: ICorDebugDebugEvent::Метод GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c5b4a15f637526cd2faadd2d9d3da143c40140f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414909"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="57c15-102">ICorDebugDebugEvent::Метод GetThread</span><span class="sxs-lookup"><span data-stu-id="57c15-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="57c15-103">Получает поток, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="57c15-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57c15-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57c15-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="57c15-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="57c15-105">Parameters</span></span>  
 <span data-ttu-id="57c15-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="57c15-106">ppThread</span></span>  
 <span data-ttu-id="57c15-107">[out] Указатель на адрес объекта ICorDebugThread, который представляет поток, на котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="57c15-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57c15-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="57c15-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57c15-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="57c15-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57c15-110">Требования</span><span class="sxs-lookup"><span data-stu-id="57c15-110">Requirements</span></span>  
 <span data-ttu-id="57c15-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57c15-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57c15-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57c15-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57c15-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57c15-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57c15-114">**Версии платформы .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57c15-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57c15-115">См. также</span><span class="sxs-lookup"><span data-stu-id="57c15-115">See Also</span></span>  
 [<span data-ttu-id="57c15-116">Интерфейс ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="57c15-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 [<span data-ttu-id="57c15-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="57c15-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
