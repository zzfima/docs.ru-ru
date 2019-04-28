---
title: Интерфейс ICorDebugCode
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
ms.openlocfilehash: 9ca47eb5508907297a78dba1ab2b0a6d2b8ece0d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750258"
---
# <a name="icordebugcode-interface"></a><span data-ttu-id="ed596-102">Интерфейс ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="ed596-102">ICorDebugCode Interface</span></span>

<span data-ttu-id="ed596-103">Представляет сегмент кода на языке MSIL или сегмент машинного кода.</span><span class="sxs-lookup"><span data-stu-id="ed596-103">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ed596-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ed596-104">Methods</span></span>  
  
|<span data-ttu-id="ed596-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ed596-105">Method</span></span>|<span data-ttu-id="ed596-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ed596-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ed596-107">Метод CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ed596-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|<span data-ttu-id="ed596-108">Создает точку останова с указанным смещением.</span><span class="sxs-lookup"><span data-stu-id="ed596-108">Creates a breakpoint at the specified offset.</span></span>|  
|[<span data-ttu-id="ed596-109">Метод GetAddress</span><span class="sxs-lookup"><span data-stu-id="ed596-109">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|<span data-ttu-id="ed596-110">Возвращает относительный виртуальный адрес (RVA) в фрагменте кода, это `ICorDebugCode` представляет.</span><span class="sxs-lookup"><span data-stu-id="ed596-110">Gets the relative virtual address (RVA) of the code segment that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="ed596-111">Метод GetCode</span><span class="sxs-lookup"><span data-stu-id="ed596-111">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|<span data-ttu-id="ed596-112">Получает весь код для указанной функции, отформатированных для Дизассемблированный код.</span><span class="sxs-lookup"><span data-stu-id="ed596-112">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="ed596-113">Этот метод является устаревшим; Используйте [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) вместо этого.</span><span class="sxs-lookup"><span data-stu-id="ed596-113">This method has been deprecated; use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>|  
|[<span data-ttu-id="ed596-114">Метод GetEnCRemapSequencePoints</span><span class="sxs-lookup"><span data-stu-id="ed596-114">GetEnCRemapSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|<span data-ttu-id="ed596-115">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="ed596-115">Not implemented.</span></span>|  
|[<span data-ttu-id="ed596-116">Метод GetFunction</span><span class="sxs-lookup"><span data-stu-id="ed596-116">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|<span data-ttu-id="ed596-117">Возвращает «ICorDebugFunction», связанный с данным `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="ed596-117">Gets the "ICorDebugFunction" associated with this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="ed596-118">Метод GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="ed596-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|<span data-ttu-id="ed596-119">Возвращает массив экземпляров «COR_DEBUG_IL_TO_NATIVE_MAP», которые представляют сопоставление из смещений MSIL в собственные смещения.</span><span class="sxs-lookup"><span data-stu-id="ed596-119">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from MSIL offsets to native offsets.</span></span>|  
|[<span data-ttu-id="ed596-120">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="ed596-120">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|<span data-ttu-id="ed596-121">Получает размер в байтах двоичного кода, представленного данным `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="ed596-121">Gets the size, in bytes, of the binary code represented by this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="ed596-122">Метод GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="ed596-122">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|<span data-ttu-id="ed596-123">Возвращает число от единицы, которое определяет версию кода, `ICorDebugCode` представляет.</span><span class="sxs-lookup"><span data-stu-id="ed596-123">Gets the one-based number that identifies the version of the code that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="ed596-124">Метод IsIL</span><span class="sxs-lookup"><span data-stu-id="ed596-124">IsIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|<span data-ttu-id="ed596-125">Получает значение, указывающее, является ли это `ICorDebugCode` компилируется в код MSIL.</span><span class="sxs-lookup"><span data-stu-id="ed596-125">Gets a value that indicates whether this `ICorDebugCode` is compiled in MSIL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed596-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="ed596-126">Remarks</span></span>  
 <span data-ttu-id="ed596-127">`ICorDebugCode` может представлять MSIL или машинный код.</span><span class="sxs-lookup"><span data-stu-id="ed596-127">`ICorDebugCode` can represent either MSIL or native code.</span></span> <span data-ttu-id="ed596-128">Объект «ICorDebugFunction», который представляет код MSIL может иметь ноль или один `ICorDebugCode` объекты, связанные с ним.</span><span class="sxs-lookup"><span data-stu-id="ed596-128">An "ICorDebugFunction" object that represents MSIL code can have either zero or one `ICorDebugCode` objects associated with it.</span></span> <span data-ttu-id="ed596-129">Объект «ICorDebugFunction», который представляет машинный код может иметь любое количество `ICorDebugCode` объекты, связанные с ним.</span><span class="sxs-lookup"><span data-stu-id="ed596-129">An "ICorDebugFunction" object that represents native code can have any number of `ICorDebugCode` objects associated with it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed596-130">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="ed596-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed596-131">Требования</span><span class="sxs-lookup"><span data-stu-id="ed596-131">Requirements</span></span>  
 <span data-ttu-id="ed596-132">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed596-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed596-133">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed596-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed596-134">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed596-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed596-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed596-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed596-136">См. также</span><span class="sxs-lookup"><span data-stu-id="ed596-136">See also</span></span>

- [<span data-ttu-id="ed596-137">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="ed596-137">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="ed596-138">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ed596-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
