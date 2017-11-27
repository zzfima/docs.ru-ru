---
title: "ICorDebugCode интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode
helpviewer_keywords: ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7813381c345db3d14318dddd93df1b491b46549e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcode-interface1"></a><span data-ttu-id="0946c-102">ICorDebugCode интерфейс1</span><span class="sxs-lookup"><span data-stu-id="0946c-102">ICorDebugCode Interface1</span></span>
<span data-ttu-id="0946c-103">Представляет сегмент кода на языке MSIL или сегмент машинного кода.</span><span class="sxs-lookup"><span data-stu-id="0946c-103">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0946c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0946c-104">Methods</span></span>  
  
|<span data-ttu-id="0946c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0946c-105">Method</span></span>|<span data-ttu-id="0946c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0946c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0946c-107">Метод CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="0946c-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|<span data-ttu-id="0946c-108">Создает точку останова с указанным смещением.</span><span class="sxs-lookup"><span data-stu-id="0946c-108">Creates a breakpoint at the specified offset.</span></span>|  
|[<span data-ttu-id="0946c-109">GetAddress-метод</span><span class="sxs-lookup"><span data-stu-id="0946c-109">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|<span data-ttu-id="0946c-110">Получает относительный виртуальный адрес (RVA) сегмента кода, это `ICorDebugCode` представляет.</span><span class="sxs-lookup"><span data-stu-id="0946c-110">Gets the relative virtual address (RVA) of the code segment that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="0946c-111">Метод GetCode</span><span class="sxs-lookup"><span data-stu-id="0946c-111">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|<span data-ttu-id="0946c-112">Возвращает весь код для заданной функции, отформатированной для дизассемблирования.</span><span class="sxs-lookup"><span data-stu-id="0946c-112">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="0946c-113">Этот метод является устаревшим; Используйте [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) вместо него.</span><span class="sxs-lookup"><span data-stu-id="0946c-113">This method has been deprecated; use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>|  
|[<span data-ttu-id="0946c-114">Метод GetEnCRemapSequencePoints</span><span class="sxs-lookup"><span data-stu-id="0946c-114">GetEnCRemapSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|<span data-ttu-id="0946c-115">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="0946c-115">Not implemented.</span></span>|  
|[<span data-ttu-id="0946c-116">Метод GetFunction</span><span class="sxs-lookup"><span data-stu-id="0946c-116">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|<span data-ttu-id="0946c-117">Возвращает «ICorDebugFunction», связанный с этим `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="0946c-117">Gets the "ICorDebugFunction" associated with this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="0946c-118">Метод GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="0946c-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|<span data-ttu-id="0946c-119">Возвращает массив экземпляров «COR_DEBUG_IL_TO_NATIVE_MAP», представляющих сопоставления из смещений MSIL в собственные смещения.</span><span class="sxs-lookup"><span data-stu-id="0946c-119">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from MSIL offsets to native offsets.</span></span>|  
|[<span data-ttu-id="0946c-120">GetSize-метод</span><span class="sxs-lookup"><span data-stu-id="0946c-120">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|<span data-ttu-id="0946c-121">Возвращает размер в байтах двоичного кода, представленный этим `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="0946c-121">Gets the size, in bytes, of the binary code represented by this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="0946c-122">Метод GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="0946c-122">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|<span data-ttu-id="0946c-123">Возвращает число от единицы, определяющее версию кода этим `ICorDebugCode` представляет.</span><span class="sxs-lookup"><span data-stu-id="0946c-123">Gets the one-based number that identifies the version of the code that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="0946c-124">Метод IsIL</span><span class="sxs-lookup"><span data-stu-id="0946c-124">IsIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|<span data-ttu-id="0946c-125">Возвращает значение, указывающее, является ли это `ICorDebugCode` скомпилированные в MSIL.</span><span class="sxs-lookup"><span data-stu-id="0946c-125">Gets a value that indicates whether this `ICorDebugCode` is compiled in MSIL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0946c-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="0946c-126">Remarks</span></span>  
 <span data-ttu-id="0946c-127">`ICorDebugCode`может представлять MSIL или машинный код.</span><span class="sxs-lookup"><span data-stu-id="0946c-127">`ICorDebugCode` can represent either MSIL or native code.</span></span> <span data-ttu-id="0946c-128">Объект «ICorDebugFunction», который представляет код MSIL может иметь ноль или один `ICorDebugCode` связанные с ним объекты.</span><span class="sxs-lookup"><span data-stu-id="0946c-128">An "ICorDebugFunction" object that represents MSIL code can have either zero or one `ICorDebugCode` objects associated with it.</span></span> <span data-ttu-id="0946c-129">Объект «ICorDebugFunction», который представляет машинный код может иметь любое количество `ICorDebugCode` связанные с ним объекты.</span><span class="sxs-lookup"><span data-stu-id="0946c-129">An "ICorDebugFunction" object that represents native code can have any number of `ICorDebugCode` objects associated with it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0946c-130">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="0946c-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0946c-131">Требования</span><span class="sxs-lookup"><span data-stu-id="0946c-131">Requirements</span></span>  
 <span data-ttu-id="0946c-132">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0946c-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0946c-133">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0946c-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0946c-134">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0946c-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0946c-135">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0946c-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0946c-136">См. также</span><span class="sxs-lookup"><span data-stu-id="0946c-136">See Also</span></span>  
    
 [<span data-ttu-id="0946c-137">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="0946c-137">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [<span data-ttu-id="0946c-138">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0946c-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
