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
ms.openlocfilehash: 30008d6cc98f7d0d0501d67e18703ed5a344d43a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794365"
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="05711-102">Интерфейс ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="05711-102">ICorDebugILCode2 Interface</span></span>
<span data-ttu-id="05711-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="05711-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="05711-104">Логически расширяет интерфейс [икордебугилкоде](icordebugilcode-interface.md) , чтобы предоставить методы, которые возвращают маркер для сигнатуры локальной переменной функции и сопоставляют смещенные промежуточные языки (IL) профилировщика с исходными смещениями Il метода.</span><span class="sxs-lookup"><span data-stu-id="05711-104">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05711-105">Методы</span><span class="sxs-lookup"><span data-stu-id="05711-105">Methods</span></span>  
  
|<span data-ttu-id="05711-106">Метод</span><span class="sxs-lookup"><span data-stu-id="05711-106">Method</span></span>|<span data-ttu-id="05711-107">Описание</span><span class="sxs-lookup"><span data-stu-id="05711-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="05711-108">Метод GetInstrumentedILMap</span><span class="sxs-lookup"><span data-stu-id="05711-108">GetInstrumentedILMap Method</span></span>](icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="05711-109">Возвращает сопоставление смещений инструментированного профилировщиком промежуточного языка со смещениями промежуточного языка исходного метода для этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="05711-109">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="05711-110">Метод GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="05711-110">GetLocalVarSigToken Method</span></span>](icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="05711-111">Получает маркер метаданных для подписи локальной переменной, предназначенной для представленной этим экземпляром функции.</span><span class="sxs-lookup"><span data-stu-id="05711-111">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="05711-112">Требования</span><span class="sxs-lookup"><span data-stu-id="05711-112">Requirements</span></span>  
 <span data-ttu-id="05711-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05711-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05711-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05711-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05711-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05711-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05711-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05711-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05711-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="05711-117">See also</span></span>

- [<span data-ttu-id="05711-118">Интерфейс ICorDebugILCode</span><span class="sxs-lookup"><span data-stu-id="05711-118">ICorDebugILCode Interface</span></span>](icordebugilcode-interface.md)
- [<span data-ttu-id="05711-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="05711-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="05711-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="05711-120">Debugging</span></span>](index.md)
