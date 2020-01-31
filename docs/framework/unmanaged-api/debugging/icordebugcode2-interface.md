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
ms.openlocfilehash: a9ce778cfa1aed4dcf6117c4fe2eca23ccda37a3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777952"
---
# <a name="icordebugcode2-interface"></a><span data-ttu-id="eeb28-102">Интерфейс ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="eeb28-102">ICorDebugCode2 Interface</span></span>

<span data-ttu-id="eeb28-103">Предоставляет методы, расширяющие возможности "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="eeb28-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eeb28-104">Методы</span><span class="sxs-lookup"><span data-stu-id="eeb28-104">Methods</span></span>  
  
|<span data-ttu-id="eeb28-105">Метод</span><span class="sxs-lookup"><span data-stu-id="eeb28-105">Method</span></span>|<span data-ttu-id="eeb28-106">Описание</span><span class="sxs-lookup"><span data-stu-id="eeb28-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eeb28-107">Метод GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="eeb28-107">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="eeb28-108">Возвращает фрагменты кода, из которого состоит этот объект кода.</span><span class="sxs-lookup"><span data-stu-id="eeb28-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="eeb28-109">Метод GetCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="eeb28-109">GetCompilerFlags Method</span></span>](icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="eeb28-110">Возвращает флаги, указывающие условия, при которых этот объект кода был либо JIT-скомпилирован, либо создан с помощью генератора образов в машинном коде (Ngen. exe).</span><span class="sxs-lookup"><span data-stu-id="eeb28-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eeb28-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="eeb28-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eeb28-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="eeb28-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eeb28-113">Требования</span><span class="sxs-lookup"><span data-stu-id="eeb28-113">Requirements</span></span>  
 <span data-ttu-id="eeb28-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eeb28-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eeb28-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eeb28-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eeb28-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eeb28-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eeb28-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eeb28-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeb28-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="eeb28-118">See also</span></span>

- [<span data-ttu-id="eeb28-119">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="eeb28-119">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="eeb28-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="eeb28-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
