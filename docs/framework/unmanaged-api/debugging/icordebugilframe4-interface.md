---
title: "Интерфейс ICorDebugILFrame4"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame4
api_location: mscordbi.dll
api_type: COM
ms.assetid: 1e739183-3e05-49e5-846f-4075256e41de
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80b42a2ed4e93fd5e4c662bab34b111fe0757890
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilframe4-interface"></a><span data-ttu-id="53471-102">Интерфейс ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="53471-102">ICorDebugILFrame4 Interface</span></span>
<span data-ttu-id="53471-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="53471-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="53471-104">Предоставляет методы, обеспечивающие доступ к локальным переменным и коду в кадре стека кода промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="53471-104">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="53471-105">Параметр показывает, имеет ли отладчик доступ к переменным и коду, добавленным в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="53471-105">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="53471-106">Методы</span><span class="sxs-lookup"><span data-stu-id="53471-106">Methods</span></span>  
  
|<span data-ttu-id="53471-107">Метод</span><span class="sxs-lookup"><span data-stu-id="53471-107">Method</span></span>|<span data-ttu-id="53471-108">Описание</span><span class="sxs-lookup"><span data-stu-id="53471-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="53471-109">Метод EnumerateLocalVariablesEx</span><span class="sxs-lookup"><span data-stu-id="53471-109">EnumerateLocalVariablesEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md)|<span data-ttu-id="53471-110">Возвращает список локальных переменных, доступных в текущем кадре.</span><span class="sxs-lookup"><span data-stu-id="53471-110">Returns a list of the local variables available in the current frame.</span></span>|  
|[<span data-ttu-id="53471-111">Метод GetCodeEx</span><span class="sxs-lookup"><span data-stu-id="53471-111">GetCodeEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md)|<span data-ttu-id="53471-112">Возвращает код, который выполняется этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="53471-112">Returns the code that this stack frame is running.</span></span>|  
|[<span data-ttu-id="53471-113">Метод GetLocalVariableEx</span><span class="sxs-lookup"><span data-stu-id="53471-113">GetLocalVariableEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md)|<span data-ttu-id="53471-114">Возвращает значение локальной переменной в кадре промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="53471-114">Returns the value of a local variable in the IL frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53471-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="53471-115">Remarks</span></span>  
 <span data-ttu-id="53471-116">Эти методы предлагают функциональность, в дополнение к предоставляемым [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md), [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md), и [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) методы.</span><span class="sxs-lookup"><span data-stu-id="53471-116">These methods offer functionality in addition to that provided by the [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md), [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md), and [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) methods.</span></span> <span data-ttu-id="53471-117">Каждый метод включает параметр `flags`, определяющий видимость дополнительных локальных переменных или кода, определенных ReJIT-запросом профилировщика.</span><span class="sxs-lookup"><span data-stu-id="53471-117">Each method includes a `flags` parameter that specifies whether additional local variables or code defined by a profiler's ReJIT request are visible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53471-118">Требования</span><span class="sxs-lookup"><span data-stu-id="53471-118">Requirements</span></span>  
 <span data-ttu-id="53471-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53471-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53471-120">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="53471-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53471-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53471-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53471-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53471-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53471-123">См. также</span><span class="sxs-lookup"><span data-stu-id="53471-123">See Also</span></span>  
 [<span data-ttu-id="53471-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="53471-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="53471-125">Отладка</span><span class="sxs-lookup"><span data-stu-id="53471-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
