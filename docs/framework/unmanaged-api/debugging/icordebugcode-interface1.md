---
title: ICorDebugCode интерфейс1
ms.date: 03/30/2017
api_name:
- ICorDebugCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode
helpviewer_keywords:
- ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37917577c802514fcebc3ea0792cbce9bb8a7345
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugcode-interface1"></a><span data-ttu-id="3c3bf-102">ICorDebugCode интерфейс1</span><span class="sxs-lookup"><span data-stu-id="3c3bf-102">ICorDebugCode Interface1</span></span>
<span data-ttu-id="3c3bf-103">Представляет сегмент кода на языке MSIL или сегмент машинного кода.</span><span class="sxs-lookup"><span data-stu-id="3c3bf-103">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3c3bf-104">Методы</span><span class="sxs-lookup"><span data-stu-id="3c3bf-104">Methods</span></span>  
  
|<span data-ttu-id="3c3bf-105">Метод</span><span class="sxs-lookup"><span data-stu-id="3c3bf-105">Method</span></span>|<span data-ttu-id="3c3bf-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3c3bf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3c3bf-107">Метод CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="3c3bf-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|<span data-ttu-id="3c3bf-108">Создает точку останова с указанным смещением.</span><span class="sxs-lookup"><span data-stu-id="3c3bf-108">Creates a breakpoint at the specified offset.</span></span>|  
|[<span data-ttu-id="3c3bf-109">Метод GetAddress</span><span class="sxs-lookup"><span data-stu-id="3c3bf-109">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|<span data-ttu-id="3c3bf-110">Получает относительный виртуальный адрес (RVA) сегмента кода, это `ICorDebugCode` представляет.</span><span class="sxs-lookup"><span data-stu-id="3c3bf-110">Gets the relative virtual address (RVA) of the code segment that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="3c3bf-111">Метод GetCode</span><span class="sxs-lookup"><span data-stu-id="3c3bf-111">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|<span data-ttu-id="3c3bf-112">Возвращает весь код для заданной функции, отформатированной для дизассемблирования.</span><span class="sxs-lookup"><span data-stu-id="3c3bf-112">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="3c3bf-113">Этот метод является устаревшим; Используйте [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) вместо него.</span><span class="sxs-lookup"><span data-stu-id="3c3bf-113">This method has been deprecated; use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>|  
|[<span data-ttu-id="3c3bf-114">Метод GetEnCRemapSequencePoints</span><span class="sxs-lookup"><span data-stu-id="3c3bf-114">GetEnCRemapSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|<span data-ttu-id="3c3bf-115">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="3c3bf-115">Not implemented.</span></span>|  
|[<span data-ttu-id="3c3bf-116">Метод GetFunction</span><span class="sxs-lookup"><span data-stu-id="3c3bf-116">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|<span data-ttu-id="3c3bf-117">Возвращает «ICorDebugFunction», связанный с этим `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="3c3bf-117">Gets the "ICorDebugFunction" associated with this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="3c3bf-118">Метод GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="3c3bf-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|<span data-ttu-id="3c3bf-119">Возвращает массив экземпляров «COR_DEBUG_IL_TO_NATIVE_MAP», представляющих сопоставления из смещений MSIL в собственные смещения.</span><span class="sxs-lookup"><span data-stu-id="3c3bf-119">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from MSIL offsets to native offsets.</span></span>|  
|[<span data-ttu-id="3c3bf-120">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="3c3bf-120">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|<span data-ttu-id="3c3bf-121">Возвращает размер в байтах двоичного кода, представленный этим `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="3c3bf-121">Gets the size, in bytes, of the binary code represented by this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="3c3bf-122">Метод GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="3c3bf-122">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|<span data-ttu-id="3c3bf-123">Возвращает число от единицы, определяющее версию кода этим `ICorDebugCode` представляет.</span><span class="sxs-lookup"><span data-stu-id="3c3bf-123">Gets the one-based number that identifies the version of the code that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="3c3bf-124">Метод IsIL</span><span class="sxs-lookup"><span data-stu-id="3c3bf-124">IsIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|<span data-ttu-id="3c3bf-125">Возвращает значение, указывающее, является ли это `ICorDebugCode` скомпилированные в MSIL.</span><span class="sxs-lookup"><span data-stu-id="3c3bf-125">Gets a value that indicates whether this `ICorDebugCode` is compiled in MSIL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c3bf-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="3c3bf-126">Remarks</span></span>  
 <span data-ttu-id="3c3bf-127">`ICorDebugCode` может представлять MSIL или машинный код.</span><span class="sxs-lookup"><span data-stu-id="3c3bf-127">`ICorDebugCode` can represent either MSIL or native code.</span></span> <span data-ttu-id="3c3bf-128">Объект «ICorDebugFunction», который представляет код MSIL может иметь ноль или один `ICorDebugCode` связанные с ним объекты.</span><span class="sxs-lookup"><span data-stu-id="3c3bf-128">An "ICorDebugFunction" object that represents MSIL code can have either zero or one `ICorDebugCode` objects associated with it.</span></span> <span data-ttu-id="3c3bf-129">Объект «ICorDebugFunction», который представляет машинный код может иметь любое количество `ICorDebugCode` связанные с ним объекты.</span><span class="sxs-lookup"><span data-stu-id="3c3bf-129">An "ICorDebugFunction" object that represents native code can have any number of `ICorDebugCode` objects associated with it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c3bf-130">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="3c3bf-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c3bf-131">Требования</span><span class="sxs-lookup"><span data-stu-id="3c3bf-131">Requirements</span></span>  
 <span data-ttu-id="3c3bf-132">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c3bf-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c3bf-133">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c3bf-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c3bf-134">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c3bf-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c3bf-135">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c3bf-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c3bf-136">См. также</span><span class="sxs-lookup"><span data-stu-id="3c3bf-136">See Also</span></span>  
    
 [<span data-ttu-id="3c3bf-137">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="3c3bf-137">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [<span data-ttu-id="3c3bf-138">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3c3bf-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
