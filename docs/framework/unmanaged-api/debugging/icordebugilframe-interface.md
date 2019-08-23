---
title: Интерфейс ICorDebugILFrame
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame
helpviewer_keywords:
- ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a40436fcf1485c5d08d175b0396af2b6870c19a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917019"
---
# <a name="icordebugilframe-interface"></a><span data-ttu-id="f32af-102">Интерфейс ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="f32af-102">ICorDebugILFrame Interface</span></span>

<span data-ttu-id="f32af-103">Представляет кадр стека кода промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="f32af-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="f32af-104">Этот интерфейс является подклассом интерфейса ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="f32af-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f32af-105">Методы</span><span class="sxs-lookup"><span data-stu-id="f32af-105">Methods</span></span>  
  
|<span data-ttu-id="f32af-106">Метод</span><span class="sxs-lookup"><span data-stu-id="f32af-106">Method</span></span>|<span data-ttu-id="f32af-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f32af-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f32af-108">Метод CanSetIP</span><span class="sxs-lookup"><span data-stu-id="f32af-108">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|<span data-ttu-id="f32af-109">Возвращает значение, указывающее, можно ли задать для указателя инструкции заданное расположение смещения.</span><span class="sxs-lookup"><span data-stu-id="f32af-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="f32af-110">Метод EnumerateArguments</span><span class="sxs-lookup"><span data-stu-id="f32af-110">EnumerateArguments Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="f32af-111">Возвращает перечислитель для аргументов в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="f32af-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="f32af-112">Метод EnumerateLocalVariables</span><span class="sxs-lookup"><span data-stu-id="f32af-112">EnumerateLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="f32af-113">Возвращает перечислитель для локальных переменных в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="f32af-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="f32af-114">Метод GetArgument</span><span class="sxs-lookup"><span data-stu-id="f32af-114">GetArgument Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|<span data-ttu-id="f32af-115">Возвращает значение указанного аргумента в этом кадре стека MSIL.</span><span class="sxs-lookup"><span data-stu-id="f32af-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="f32af-116">Метод GetIP</span><span class="sxs-lookup"><span data-stu-id="f32af-116">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|<span data-ttu-id="f32af-117">Возвращает значение указателя инструкции и битовое значение сочетания, которое описывает, как было получено значение указателя инструкции.</span><span class="sxs-lookup"><span data-stu-id="f32af-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="f32af-118">Метод GetLocalVariable</span><span class="sxs-lookup"><span data-stu-id="f32af-118">GetLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="f32af-119">Возвращает значение указанной локальной переменной в этом кадре стека MSIL.</span><span class="sxs-lookup"><span data-stu-id="f32af-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="f32af-120">Метод GetStackDepth</span><span class="sxs-lookup"><span data-stu-id="f32af-120">GetStackDepth Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="f32af-121">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="f32af-121">Not implemented.</span></span>|  
|[<span data-ttu-id="f32af-122">Метод GetStackValue</span><span class="sxs-lookup"><span data-stu-id="f32af-122">GetStackValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="f32af-123">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="f32af-123">Not implemented.</span></span>|  
|[<span data-ttu-id="f32af-124">Метод SetIP</span><span class="sxs-lookup"><span data-stu-id="f32af-124">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|<span data-ttu-id="f32af-125">Устанавливает указатель инструкции на указанное положение смещения в коде MSIL.</span><span class="sxs-lookup"><span data-stu-id="f32af-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f32af-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="f32af-126">Remarks</span></span>  
 <span data-ttu-id="f32af-127">`ICorDebugILFrame` Интерфейс является специализированным интерфейсом ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="f32af-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="f32af-128">Он используется либо для кадров кода MSIL, либо для кадров, скомпилированных JIT.</span><span class="sxs-lookup"><span data-stu-id="f32af-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="f32af-129">JIT-скомпилированные кадры реализуют `ICorDebugILFrame` интерфейс и интерфейс ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="f32af-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f32af-130">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="f32af-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f32af-131">Требования</span><span class="sxs-lookup"><span data-stu-id="f32af-131">Requirements</span></span>  
 <span data-ttu-id="f32af-132">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f32af-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f32af-133">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f32af-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f32af-134">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="f32af-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f32af-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f32af-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f32af-136">См. также</span><span class="sxs-lookup"><span data-stu-id="f32af-136">See also</span></span>

- [<span data-ttu-id="f32af-137">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f32af-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
