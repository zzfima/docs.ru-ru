---
title: Метод ICorDebugVirtualUnwinder::Next
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74be827dc97213507b96da9e025923f859011acd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946150"
---
# <a name="icordebugvirtualunwindernext-method"></a><span data-ttu-id="f0fb9-102">Метод ICorDebugVirtualUnwinder::Next</span><span class="sxs-lookup"><span data-stu-id="f0fb9-102">ICorDebugVirtualUnwinder::Next Method</span></span>
<span data-ttu-id="f0fb9-103">Переходит в контекст вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="f0fb9-103">Advances to the caller's context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0fb9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0fb9-104">Syntax</span></span>  
  
```  
HRESULT Next();  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0fb9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0fb9-105">Parameters</span></span>  
 <span data-ttu-id="f0fb9-106">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f0fb9-106">None.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0fb9-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f0fb9-107">Return Value</span></span>  
 <span data-ttu-id="f0fb9-108">Значение `S_OK`, если очистка произошла успешно, или значение `CORDBG_S_AT_END_OF_STACK`, если не удалось завершить очистку, поскольку больше нет фреймов.</span><span class="sxs-lookup"><span data-stu-id="f0fb9-108">`S_OK` if the unwind occurred successfully, or `CORDBG_S_AT_END_OF_STACK` if the unwind cannot be completed because there are no more frames.</span></span>  
  
 <span data-ttu-id="f0fb9-109">Если возвращается значение HRESULT, указывающее на ошибку, API ICorDebug будут возвращать `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="f0fb9-109">If a failing HRESULT is returned, ICorDebug APIs will return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0fb9-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0fb9-110">Remarks</span></span>  
 <span data-ttu-id="f0fb9-111">Обходчик стека должен проверять, что он продвигается вперед, поэтому в конечном итоге вызов `Next` вернет значение HRESULT, указывающее на ошибку, или значение `CORDBG_S_AT_END_OF_STACK`.</span><span class="sxs-lookup"><span data-stu-id="f0fb9-111">The stack walker should ensure that it makes forward progress, so that eventually a call to `Next` will return a failing HRESULT or `CORDBG_S_AT_END_OF_STACK`.</span></span> <span data-ttu-id="f0fb9-112">Возвращение `S_OK` неограниченное время может привести к бесконечному циклу.</span><span class="sxs-lookup"><span data-stu-id="f0fb9-112">Returning `S_OK` indefinitely may cause an infinite loop.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0fb9-113">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="f0fb9-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0fb9-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f0fb9-114">Requirements</span></span>  
 <span data-ttu-id="f0fb9-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0fb9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0fb9-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0fb9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0fb9-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0fb9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0fb9-118">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0fb9-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0fb9-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f0fb9-119">See also</span></span>

- [<span data-ttu-id="f0fb9-120">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="f0fb9-120">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="f0fb9-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f0fb9-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
