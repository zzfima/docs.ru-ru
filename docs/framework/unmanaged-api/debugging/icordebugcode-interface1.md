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
ms.openlocfilehash: 4b24b3dfe6a931866acd7eba966811071ff39ea5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788930"
---
# <a name="icordebugcode-interface"></a><span data-ttu-id="26984-102">Интерфейс ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="26984-102">ICorDebugCode Interface</span></span>

<span data-ttu-id="26984-103">Представляет сегмент кода на языке MSIL или сегмент машинного кода.</span><span class="sxs-lookup"><span data-stu-id="26984-103">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="26984-104">Методы</span><span class="sxs-lookup"><span data-stu-id="26984-104">Methods</span></span>  
  
|<span data-ttu-id="26984-105">Метод</span><span class="sxs-lookup"><span data-stu-id="26984-105">Method</span></span>|<span data-ttu-id="26984-106">Описание</span><span class="sxs-lookup"><span data-stu-id="26984-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="26984-107">Метод CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="26984-107">CreateBreakpoint Method</span></span>](icordebugcode-createbreakpoint-method.md)|<span data-ttu-id="26984-108">Создает точку останова по указанному смещению.</span><span class="sxs-lookup"><span data-stu-id="26984-108">Creates a breakpoint at the specified offset.</span></span>|  
|[<span data-ttu-id="26984-109">Метод GetAddress</span><span class="sxs-lookup"><span data-stu-id="26984-109">GetAddress Method</span></span>](icordebugcode-getaddress-method.md)|<span data-ttu-id="26984-110">Возвращает относительный виртуальный адрес (RVA) сегмента кода, который представляет этот `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="26984-110">Gets the relative virtual address (RVA) of the code segment that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="26984-111">Метод GetCode</span><span class="sxs-lookup"><span data-stu-id="26984-111">GetCode Method</span></span>](icordebugcode-getcode-method.md)|<span data-ttu-id="26984-112">Возвращает весь код для указанной функции, отформатированный для дизассемблирования.</span><span class="sxs-lookup"><span data-stu-id="26984-112">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="26984-113">Этот метод не рекомендуется к использованию. Вместо этого используйте [ICorDebugCode2:: жеткодечункс](icordebugcode2-getcodechunks-method.md) .</span><span class="sxs-lookup"><span data-stu-id="26984-113">This method has been deprecated; use [ICorDebugCode2::GetCodeChunks](icordebugcode2-getcodechunks-method.md) instead.</span></span>|  
|[<span data-ttu-id="26984-114">Метод GetEnCRemapSequencePoints</span><span class="sxs-lookup"><span data-stu-id="26984-114">GetEnCRemapSequencePoints Method</span></span>](icordebugcode-getencremapsequencepoints-method.md)|<span data-ttu-id="26984-115">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="26984-115">Not implemented.</span></span>|  
|[<span data-ttu-id="26984-116">Метод GetFunction</span><span class="sxs-lookup"><span data-stu-id="26984-116">GetFunction Method</span></span>](icordebugcode-getfunction-method.md)|<span data-ttu-id="26984-117">Возвращает "ICorDebugFunction", связанный с этим `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="26984-117">Gets the "ICorDebugFunction" associated with this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="26984-118">Метод GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="26984-118">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)|<span data-ttu-id="26984-119">Возвращает массив экземпляров "COR_DEBUG_IL_TO_NATIVE_MAP", которые представляют сопоставления от смещений MSIL до собственных смещений.</span><span class="sxs-lookup"><span data-stu-id="26984-119">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from MSIL offsets to native offsets.</span></span>|  
|[<span data-ttu-id="26984-120">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="26984-120">GetSize Method</span></span>](icordebugcode-getsize-method.md)|<span data-ttu-id="26984-121">Возвращает размер двоичного кода (в байтах), представленного этим `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="26984-121">Gets the size, in bytes, of the binary code represented by this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="26984-122">Метод GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="26984-122">GetVersionNumber Method</span></span>](icordebugcode-getversionnumber-method.md)|<span data-ttu-id="26984-123">Возвращает номер, отсчитываемый от единицы, определяющий версию кода, который представляет этот `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="26984-123">Gets the one-based number that identifies the version of the code that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="26984-124">Метод IsIL</span><span class="sxs-lookup"><span data-stu-id="26984-124">IsIL Method</span></span>](icordebugcode-isil-method.md)|<span data-ttu-id="26984-125">Возвращает значение, указывающее, компилируется ли этот `ICorDebugCode` в MSIL.</span><span class="sxs-lookup"><span data-stu-id="26984-125">Gets a value that indicates whether this `ICorDebugCode` is compiled in MSIL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26984-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="26984-126">Remarks</span></span>  
 <span data-ttu-id="26984-127">`ICorDebugCode` может представлять MSIL или машинный код.</span><span class="sxs-lookup"><span data-stu-id="26984-127">`ICorDebugCode` can represent either MSIL or native code.</span></span> <span data-ttu-id="26984-128">Объект "ICorDebugFunction", представляющий код MSIL, может иметь либо ноль, либо один `ICorDebugCode` связанных с ним объектов.</span><span class="sxs-lookup"><span data-stu-id="26984-128">An "ICorDebugFunction" object that represents MSIL code can have either zero or one `ICorDebugCode` objects associated with it.</span></span> <span data-ttu-id="26984-129">Объект "ICorDebugFunction", представляющий машинный код, может содержать любое количество `ICorDebugCode` объектов, связанных с ним.</span><span class="sxs-lookup"><span data-stu-id="26984-129">An "ICorDebugFunction" object that represents native code can have any number of `ICorDebugCode` objects associated with it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="26984-130">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="26984-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26984-131">Требования</span><span class="sxs-lookup"><span data-stu-id="26984-131">Requirements</span></span>  
 <span data-ttu-id="26984-132">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26984-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26984-133">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26984-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26984-134">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26984-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26984-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26984-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26984-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="26984-136">See also</span></span>

- [<span data-ttu-id="26984-137">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="26984-137">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="26984-138">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="26984-138">Debugging Interfaces</span></span>](debugging-interfaces.md)
