---
title: "ICorDebugILFrame интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame
helpviewer_keywords: ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1db53f50e942e70517fc06dfd90e75d04158ea9a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe-interface1"></a><span data-ttu-id="42403-102">ICorDebugILFrame интерфейс1</span><span class="sxs-lookup"><span data-stu-id="42403-102">ICorDebugILFrame Interface1</span></span>
<span data-ttu-id="42403-103">Представляет кадр стека кода промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="42403-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="42403-104">Этот интерфейс является подклассом ICorDebugFrame-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="42403-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="42403-105">Методы</span><span class="sxs-lookup"><span data-stu-id="42403-105">Methods</span></span>  
  
|<span data-ttu-id="42403-106">Метод</span><span class="sxs-lookup"><span data-stu-id="42403-106">Method</span></span>|<span data-ttu-id="42403-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="42403-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="42403-108">Метод CanSetIP</span><span class="sxs-lookup"><span data-stu-id="42403-108">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|<span data-ttu-id="42403-109">Возвращает значение, указывающее, можно ли безопасно значение указателя инструкций заданное расположение смещения.</span><span class="sxs-lookup"><span data-stu-id="42403-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="42403-110">Метод EnumerateArguments</span><span class="sxs-lookup"><span data-stu-id="42403-110">EnumerateArguments Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="42403-111">Получает перечислитель для аргументов в кадре.</span><span class="sxs-lookup"><span data-stu-id="42403-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="42403-112">Метод EnumerateLocalVariables</span><span class="sxs-lookup"><span data-stu-id="42403-112">EnumerateLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="42403-113">Получает перечислитель для локальных переменных в кадре.</span><span class="sxs-lookup"><span data-stu-id="42403-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="42403-114">Метод GetArgument</span><span class="sxs-lookup"><span data-stu-id="42403-114">GetArgument Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|<span data-ttu-id="42403-115">Возвращает значение указанного аргумента в кадре стека MSIL.</span><span class="sxs-lookup"><span data-stu-id="42403-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="42403-116">Метод GetIP</span><span class="sxs-lookup"><span data-stu-id="42403-116">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|<span data-ttu-id="42403-117">Возвращает значение указателя инструкций и битовую комбинацию значение, которое описывает, каким образом было получено значение указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="42403-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="42403-118">Метод GetLocalVariable</span><span class="sxs-lookup"><span data-stu-id="42403-118">GetLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="42403-119">Получает значение указанной локальной переменной в кадре стека MSIL.</span><span class="sxs-lookup"><span data-stu-id="42403-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="42403-120">Метод GetStackDepth</span><span class="sxs-lookup"><span data-stu-id="42403-120">GetStackDepth Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="42403-121">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="42403-121">Not implemented.</span></span>|  
|[<span data-ttu-id="42403-122">Метод GetStackValue</span><span class="sxs-lookup"><span data-stu-id="42403-122">GetStackValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="42403-123">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="42403-123">Not implemented.</span></span>|  
|[<span data-ttu-id="42403-124">Метод SetIP</span><span class="sxs-lookup"><span data-stu-id="42403-124">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|<span data-ttu-id="42403-125">Задает указатель инструкций заданное расположение смещения в MSIL-код.</span><span class="sxs-lookup"><span data-stu-id="42403-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42403-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="42403-126">Remarks</span></span>  
 <span data-ttu-id="42403-127">`ICorDebugILFrame` Специализированный интерфейс ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="42403-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="42403-128">Он используется для фреймов кода MSIL или для just-in-time (JIT) компиляции кадры.</span><span class="sxs-lookup"><span data-stu-id="42403-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="42403-129">Кадры JIT-компиляции реализовывать `ICorDebugILFrame` интерфейс и ICorDebugNativeFrame-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="42403-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42403-130">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="42403-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42403-131">Требования</span><span class="sxs-lookup"><span data-stu-id="42403-131">Requirements</span></span>  
 <span data-ttu-id="42403-132">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42403-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42403-133">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42403-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42403-134">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42403-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42403-135">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42403-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42403-136">См. также</span><span class="sxs-lookup"><span data-stu-id="42403-136">See Also</span></span>  
 [<span data-ttu-id="42403-137">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="42403-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
