---
title: Метод ICorDebugVirtualUnwinder::Next
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74be827dc97213507b96da9e025923f859011acd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076891"
---
# <a name="icordebugvirtualunwindernext-method"></a><span data-ttu-id="a90de-102">Метод ICorDebugVirtualUnwinder::Next</span><span class="sxs-lookup"><span data-stu-id="a90de-102">ICorDebugVirtualUnwinder::Next Method</span></span>
<span data-ttu-id="a90de-103">Переходит в контекст вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="a90de-103">Advances to the caller's context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a90de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a90de-104">Syntax</span></span>  
  
```  
HRESULT Next();  
```  
  
## <a name="parameters"></a><span data-ttu-id="a90de-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a90de-105">Parameters</span></span>  
 <span data-ttu-id="a90de-106">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a90de-106">None.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a90de-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a90de-107">Return Value</span></span>  
 `S_OK` <span data-ttu-id="a90de-108">Если очистка произошла успешно, или `CORDBG_S_AT_END_OF_STACK` если очистка не удалось завершить, так как отсутствуют дополнительные кадры.</span><span class="sxs-lookup"><span data-stu-id="a90de-108">if the unwind occurred successfully, or `CORDBG_S_AT_END_OF_STACK` if the unwind cannot be completed because there are no more frames.</span></span>  
  
 <span data-ttu-id="a90de-109">Если возвращается значение HRESULT, указывающее на ошибку, API ICorDebug будут возвращать `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="a90de-109">If a failing HRESULT is returned, ICorDebug APIs will return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a90de-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="a90de-110">Remarks</span></span>  
 <span data-ttu-id="a90de-111">Обходчик стека должен проверять, что он продвигается вперед, поэтому в конечном итоге вызов `Next` вернет значение HRESULT, указывающее на ошибку, или значение `CORDBG_S_AT_END_OF_STACK`.</span><span class="sxs-lookup"><span data-stu-id="a90de-111">The stack walker should ensure that it makes forward progress, so that eventually a call to `Next` will return a failing HRESULT or `CORDBG_S_AT_END_OF_STACK`.</span></span> <span data-ttu-id="a90de-112">Возвращение `S_OK` неограниченное время может привести к бесконечному циклу.</span><span class="sxs-lookup"><span data-stu-id="a90de-112">Returning `S_OK` indefinitely may cause an infinite loop.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a90de-113">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="a90de-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a90de-114">Требования</span><span class="sxs-lookup"><span data-stu-id="a90de-114">Requirements</span></span>  
 <span data-ttu-id="a90de-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a90de-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a90de-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a90de-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a90de-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a90de-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a90de-118">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a90de-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a90de-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a90de-119">See also</span></span>

- [<span data-ttu-id="a90de-120">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="a90de-120">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="a90de-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a90de-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
