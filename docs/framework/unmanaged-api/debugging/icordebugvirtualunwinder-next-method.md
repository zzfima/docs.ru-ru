---
title: "Метод ICorDebugVirtualUnwinder::Next"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61f7e5afc65019f1817b15ae84ca3f7b42e3ece9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvirtualunwindernext-method"></a><span data-ttu-id="1f9a5-102">Метод ICorDebugVirtualUnwinder::Next</span><span class="sxs-lookup"><span data-stu-id="1f9a5-102">ICorDebugVirtualUnwinder::Next Method</span></span>
<span data-ttu-id="1f9a5-103">Переходит в контекст вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-103">Advances to the caller's context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f9a5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f9a5-104">Syntax</span></span>  
  
```  
HRESULT Next();  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1f9a5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1f9a5-105">Parameters</span></span>  
 <span data-ttu-id="1f9a5-106">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-106">None.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f9a5-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1f9a5-107">Return Value</span></span>  
 <span data-ttu-id="1f9a5-108">Значение `S_OK`, если очистка произошла успешно, или значение `CORDBG_S_AT_END_OF_STACK`, если не удалось завершить очистку, поскольку больше нет фреймов.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-108">`S_OK` if the unwind occurred successfully, or `CORDBG_S_AT_END_OF_STACK` if the unwind cannot be completed because there are no more frames.</span></span>  
  
 <span data-ttu-id="1f9a5-109">Если возвращается значение HRESULT, указывающее на ошибку, API ICorDebug будут возвращать `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-109">If a failing HRESULT is returned, ICorDebug APIs will return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f9a5-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="1f9a5-110">Remarks</span></span>  
 <span data-ttu-id="1f9a5-111">Обходчик стека должен проверять, что он продвигается вперед, поэтому в конечном итоге вызов `Next` вернет значение HRESULT, указывающее на ошибку, или значение `CORDBG_S_AT_END_OF_STACK`.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-111">The stack walker should ensure that it makes forward progress, so that eventually a call to `Next` will return a failing HRESULT or `CORDBG_S_AT_END_OF_STACK`.</span></span> <span data-ttu-id="1f9a5-112">Возвращение `S_OK` неограниченного времени может привести к бесконечному циклу.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-112">Returning `S_OK` indefinitely may cause an infinite loop.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f9a5-113">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="1f9a5-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f9a5-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1f9a5-114">Requirements</span></span>  
 <span data-ttu-id="1f9a5-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f9a5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f9a5-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f9a5-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f9a5-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f9a5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f9a5-118">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f9a5-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f9a5-119">См. также</span><span class="sxs-lookup"><span data-stu-id="1f9a5-119">See Also</span></span>  
 [<span data-ttu-id="1f9a5-120">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="1f9a5-120">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="1f9a5-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1f9a5-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
