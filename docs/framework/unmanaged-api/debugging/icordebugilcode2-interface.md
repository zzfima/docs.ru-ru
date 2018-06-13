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
ms.openlocfilehash: 1982226e90792d4bbda1cb023d80dec96fcb2060
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418110"
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="bc735-102">Интерфейс ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="bc735-102">ICorDebugILCode2 Interface</span></span>
<span data-ttu-id="bc735-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="bc735-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="bc735-104">Логически расширяет [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) смещений интерфейс предоставлять методы, возвращающие маркер для подписи локальной переменной функции и инструментированного профилировщиком промежуточного языка (IL), которые отображаются в исходный метод IL смещения.</span><span class="sxs-lookup"><span data-stu-id="bc735-104">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bc735-105">Методы</span><span class="sxs-lookup"><span data-stu-id="bc735-105">Methods</span></span>  
  
|<span data-ttu-id="bc735-106">Метод</span><span class="sxs-lookup"><span data-stu-id="bc735-106">Method</span></span>|<span data-ttu-id="bc735-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bc735-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bc735-108">Метод GetInstrumentedILMap</span><span class="sxs-lookup"><span data-stu-id="bc735-108">GetInstrumentedILMap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="bc735-109">Возвращает сопоставление смещений инструментированного профилировщиком промежуточного языка со смещениями промежуточного языка исходного метода для этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="bc735-109">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="bc735-110">Метод GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="bc735-110">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="bc735-111">Получает маркер метаданных для подписи локальной переменной, предназначенной для представленной этим экземпляром функции.</span><span class="sxs-lookup"><span data-stu-id="bc735-111">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bc735-112">Требования</span><span class="sxs-lookup"><span data-stu-id="bc735-112">Requirements</span></span>  
 <span data-ttu-id="bc735-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc735-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc735-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc735-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc735-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc735-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc735-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc735-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc735-117">См. также</span><span class="sxs-lookup"><span data-stu-id="bc735-117">See Also</span></span>  
 [<span data-ttu-id="bc735-118">Интерфейс ICorDebugILCode</span><span class="sxs-lookup"><span data-stu-id="bc735-118">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 [<span data-ttu-id="bc735-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="bc735-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="bc735-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="bc735-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
