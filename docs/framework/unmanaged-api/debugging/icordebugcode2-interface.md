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
ms.openlocfilehash: 13803a8cc292da602b1b920a3879120c3e754ca4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414562"
---
# <a name="icordebugcode2-interface1"></a><span data-ttu-id="7b226-102">Интерфейс1 ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="7b226-102">ICorDebugCode2 Interface1</span></span>
<span data-ttu-id="7b226-103">Предоставляет методы, расширяющие возможности «ICorDebugCode».</span><span class="sxs-lookup"><span data-stu-id="7b226-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7b226-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7b226-104">Methods</span></span>  
  
|<span data-ttu-id="7b226-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7b226-105">Method</span></span>|<span data-ttu-id="7b226-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7b226-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7b226-107">Метод GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="7b226-107">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="7b226-108">Возвращает фрагменты кода, состоящий из этого объекта кода.</span><span class="sxs-lookup"><span data-stu-id="7b226-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="7b226-109">Метод GetCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="7b226-109">GetCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="7b226-110">Получает флаги, задающие условия, при которых объект код был либо just-in-time (JIT) компилируется или созданы с помощью генератора образов в машинном коде (Ngen.exe).</span><span class="sxs-lookup"><span data-stu-id="7b226-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b226-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="7b226-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b226-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="7b226-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b226-113">Требования</span><span class="sxs-lookup"><span data-stu-id="7b226-113">Requirements</span></span>  
 <span data-ttu-id="7b226-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b226-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b226-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b226-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b226-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b226-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b226-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b226-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b226-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7b226-118">See Also</span></span>  
    
 [<span data-ttu-id="7b226-119">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="7b226-119">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [<span data-ttu-id="7b226-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7b226-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
