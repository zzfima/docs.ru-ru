---
title: Интерфейс ICorDebugILFrame4
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame4
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1e739183-3e05-49e5-846f-4075256e41de
topic_type:
- apiref
ms.openlocfilehash: 7f1c5d7a6fdae3e4c5a66c9aa4a82911105f4597
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788504"
---
# <a name="icordebugilframe4-interface"></a><span data-ttu-id="040e6-102">Интерфейс ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="040e6-102">ICorDebugILFrame4 Interface</span></span>
<span data-ttu-id="040e6-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="040e6-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="040e6-104">Предоставляет методы, обеспечивающие доступ к локальным переменным и коду в кадре стека кода промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="040e6-104">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="040e6-105">Параметр показывает, имеет ли отладчик доступ к переменным и коду, добавленным в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="040e6-105">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="040e6-106">Методы</span><span class="sxs-lookup"><span data-stu-id="040e6-106">Methods</span></span>  
  
|<span data-ttu-id="040e6-107">Метод</span><span class="sxs-lookup"><span data-stu-id="040e6-107">Method</span></span>|<span data-ttu-id="040e6-108">Описание</span><span class="sxs-lookup"><span data-stu-id="040e6-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="040e6-109">Метод EnumerateLocalVariablesEx</span><span class="sxs-lookup"><span data-stu-id="040e6-109">EnumerateLocalVariablesEx Method</span></span>](icordebugilframe4-enumeratelocalvariablesex-method.md)|<span data-ttu-id="040e6-110">Возвращает список локальных переменных, доступных в текущем кадре.</span><span class="sxs-lookup"><span data-stu-id="040e6-110">Returns a list of the local variables available in the current frame.</span></span>|  
|[<span data-ttu-id="040e6-111">Метод GetCodeEx</span><span class="sxs-lookup"><span data-stu-id="040e6-111">GetCodeEx Method</span></span>](icordebugilframe4-getcodeex-method.md)|<span data-ttu-id="040e6-112">Возвращает код, который выполняется этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="040e6-112">Returns the code that this stack frame is running.</span></span>|  
|[<span data-ttu-id="040e6-113">Метод GetLocalVariableEx</span><span class="sxs-lookup"><span data-stu-id="040e6-113">GetLocalVariableEx Method</span></span>](icordebugilframe4-getlocalvariableex-method.md)|<span data-ttu-id="040e6-114">Возвращает значение локальной переменной в кадре промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="040e6-114">Returns the value of a local variable in the IL frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="040e6-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="040e6-115">Remarks</span></span>  
 <span data-ttu-id="040e6-116">Эти методы предоставляют функциональные возможности в дополнение к [возможностям,](icordebugframe-getcode-method.md)предоставляемым методами [енумерателокалвариаблес](icordebugilframe-enumeratelocalvariables-method.md), [жетлокалвариабле](icordebugilframe-getlocalvariable-method.md) и.</span><span class="sxs-lookup"><span data-stu-id="040e6-116">These methods offer functionality in addition to that provided by the [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md), [GetCode](icordebugframe-getcode-method.md), and [GetLocalVariable](icordebugilframe-getlocalvariable-method.md) methods.</span></span> <span data-ttu-id="040e6-117">Каждый метод включает параметр `flags`, определяющий видимость дополнительных локальных переменных или кода, определенных ReJIT-запросом профилировщика.</span><span class="sxs-lookup"><span data-stu-id="040e6-117">Each method includes a `flags` parameter that specifies whether additional local variables or code defined by a profiler's ReJIT request are visible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="040e6-118">Требования</span><span class="sxs-lookup"><span data-stu-id="040e6-118">Requirements</span></span>  
 <span data-ttu-id="040e6-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="040e6-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="040e6-120">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="040e6-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="040e6-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="040e6-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="040e6-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="040e6-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="040e6-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="040e6-123">See also</span></span>

- [<span data-ttu-id="040e6-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="040e6-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="040e6-125">Отладка</span><span class="sxs-lookup"><span data-stu-id="040e6-125">Debugging</span></span>](index.md)
