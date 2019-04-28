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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dce3e3e4baeaa351c5ed1d9e5ca2c03631c3fce4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750115"
---
# <a name="icordebugcode2-interface"></a><span data-ttu-id="353a0-102">Интерфейс ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="353a0-102">ICorDebugCode2 Interface</span></span>

<span data-ttu-id="353a0-103">Предоставляет методы, расширяющие возможности «ICorDebugCode».</span><span class="sxs-lookup"><span data-stu-id="353a0-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="353a0-104">Методы</span><span class="sxs-lookup"><span data-stu-id="353a0-104">Methods</span></span>  
  
|<span data-ttu-id="353a0-105">Метод</span><span class="sxs-lookup"><span data-stu-id="353a0-105">Method</span></span>|<span data-ttu-id="353a0-106">Описание</span><span class="sxs-lookup"><span data-stu-id="353a0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="353a0-107">Метод GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="353a0-107">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="353a0-108">Возвращает фрагменты кода, который представляет собой этого кода объекта.</span><span class="sxs-lookup"><span data-stu-id="353a0-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="353a0-109">Метод GetCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="353a0-109">GetCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="353a0-110">Получает флаги, задающие условия, при которых этот объект кода был либо just-in-time (JIT) скомпилированы или созданы с помощью генератора образов в машинном коде (Ngen.exe).</span><span class="sxs-lookup"><span data-stu-id="353a0-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="353a0-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="353a0-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="353a0-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="353a0-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="353a0-113">Требования</span><span class="sxs-lookup"><span data-stu-id="353a0-113">Requirements</span></span>  
 <span data-ttu-id="353a0-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="353a0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="353a0-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="353a0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="353a0-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="353a0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="353a0-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="353a0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="353a0-118">См. также</span><span class="sxs-lookup"><span data-stu-id="353a0-118">See also</span></span>

- [<span data-ttu-id="353a0-119">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="353a0-119">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="353a0-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="353a0-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
