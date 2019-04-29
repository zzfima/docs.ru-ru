---
title: Интерфейс ICorDebugILCode2
ms.date: 03/30/2017
api_name:
- ICorDebugILCode2
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: f9dc2afd-df8a-464d-bdbf-5af0a1d4bf85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a27dbd8b5013937bb97f37113687405c988c1fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645232"
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="ac36a-102">Интерфейс ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="ac36a-102">ICorDebugILCode2 Interface</span></span>
<span data-ttu-id="ac36a-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="ac36a-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="ac36a-104">Логически расширяет [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) интерфейс, чтобы предоставить методы, возвращающие маркер для подписи локальной переменной функции и сопоставлены инструментированного профилировщиком промежуточного языка (IL) смещений в исходный метод IL смещения.</span><span class="sxs-lookup"><span data-stu-id="ac36a-104">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ac36a-105">Методы</span><span class="sxs-lookup"><span data-stu-id="ac36a-105">Methods</span></span>  
  
|<span data-ttu-id="ac36a-106">Метод</span><span class="sxs-lookup"><span data-stu-id="ac36a-106">Method</span></span>|<span data-ttu-id="ac36a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ac36a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ac36a-108">Метод GetInstrumentedILMap</span><span class="sxs-lookup"><span data-stu-id="ac36a-108">GetInstrumentedILMap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="ac36a-109">Возвращает сопоставление смещений инструментированного профилировщиком промежуточного языка со смещениями промежуточного языка исходного метода для этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="ac36a-109">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="ac36a-110">Метод GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="ac36a-110">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="ac36a-111">Получает маркер метаданных для подписи локальной переменной, предназначенной для представленной этим экземпляром функции.</span><span class="sxs-lookup"><span data-stu-id="ac36a-111">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ac36a-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ac36a-112">Requirements</span></span>  
 <span data-ttu-id="ac36a-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac36a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac36a-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac36a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac36a-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac36a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac36a-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac36a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac36a-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ac36a-117">See also</span></span>

- [<span data-ttu-id="ac36a-118">Интерфейс ICorDebugILCode</span><span class="sxs-lookup"><span data-stu-id="ac36a-118">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)
- [<span data-ttu-id="ac36a-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ac36a-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ac36a-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="ac36a-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
