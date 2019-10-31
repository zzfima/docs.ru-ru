---
title: Интерфейс ICorDebugCode2
ms.date: 03/30/2017
api_name:
- ICorDebugCode2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2
helpviewer_keywords:
- ICorDebugCode2 interface [.NET Framework debugging]
ms.assetid: 9321903b-7dea-40d8-ba32-99016c00cc46
topic_type:
- apiref
ms.openlocfilehash: 7f0570b668cc33ca509c8522d1ba35ebcfca2453
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125576"
---
# <a name="icordebugcode2-interface"></a><span data-ttu-id="72510-102">Интерфейс ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="72510-102">ICorDebugCode2 Interface</span></span>

<span data-ttu-id="72510-103">Предоставляет методы, расширяющие возможности "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="72510-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="72510-104">Методы</span><span class="sxs-lookup"><span data-stu-id="72510-104">Methods</span></span>  
  
|<span data-ttu-id="72510-105">Метод</span><span class="sxs-lookup"><span data-stu-id="72510-105">Method</span></span>|<span data-ttu-id="72510-106">Описание</span><span class="sxs-lookup"><span data-stu-id="72510-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="72510-107">Метод GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="72510-107">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="72510-108">Возвращает фрагменты кода, из которого состоит этот объект кода.</span><span class="sxs-lookup"><span data-stu-id="72510-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="72510-109">Метод GetCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="72510-109">GetCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="72510-110">Возвращает флаги, указывающие условия, при которых этот объект кода был либо JIT-скомпилирован, либо создан с помощью генератора образов в машинном коде (Ngen. exe).</span><span class="sxs-lookup"><span data-stu-id="72510-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72510-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="72510-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="72510-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="72510-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72510-113">Требования</span><span class="sxs-lookup"><span data-stu-id="72510-113">Requirements</span></span>  
 <span data-ttu-id="72510-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72510-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72510-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72510-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72510-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72510-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72510-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72510-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72510-118">См. также</span><span class="sxs-lookup"><span data-stu-id="72510-118">See also</span></span>

- [<span data-ttu-id="72510-119">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="72510-119">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="72510-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="72510-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
