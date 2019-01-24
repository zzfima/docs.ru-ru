---
title: Интерфейс1 ICorDebugCode2
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a5c28ec6c447f3fc3305e0faf51aa868d5a4c17
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499977"
---
# <a name="icordebugcode2-interface1"></a><span data-ttu-id="d3858-102">Интерфейс1 ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="d3858-102">ICorDebugCode2 Interface1</span></span>
<span data-ttu-id="d3858-103">Предоставляет методы, расширяющие возможности «ICorDebugCode».</span><span class="sxs-lookup"><span data-stu-id="d3858-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d3858-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d3858-104">Methods</span></span>  
  
|<span data-ttu-id="d3858-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d3858-105">Method</span></span>|<span data-ttu-id="d3858-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d3858-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d3858-107">Метод GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="d3858-107">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="d3858-108">Возвращает фрагменты кода, который представляет собой этого кода объекта.</span><span class="sxs-lookup"><span data-stu-id="d3858-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="d3858-109">Метод GetCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="d3858-109">GetCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="d3858-110">Получает флаги, задающие условия, при которых этот объект кода был либо just-in-time (JIT) скомпилированы или созданы с помощью генератора образов в машинном коде (Ngen.exe).</span><span class="sxs-lookup"><span data-stu-id="d3858-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3858-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="d3858-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3858-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="d3858-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3858-113">Требования</span><span class="sxs-lookup"><span data-stu-id="d3858-113">Requirements</span></span>  
 <span data-ttu-id="d3858-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3858-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3858-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3858-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3858-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3858-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3858-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3858-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3858-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d3858-118">See also</span></span>

- [<span data-ttu-id="d3858-119">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="d3858-119">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="d3858-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d3858-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
