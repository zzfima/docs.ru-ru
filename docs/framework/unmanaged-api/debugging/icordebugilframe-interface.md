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
ms.openlocfilehash: 01c247f838f66d1a77831755126a5a1f56870c1e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095148"
---
# <a name="icordebugilframe-interface"></a><span data-ttu-id="dba1b-102">Интерфейс ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="dba1b-102">ICorDebugILFrame Interface</span></span>

<span data-ttu-id="dba1b-103">Представляет кадр стека кода промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="dba1b-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="dba1b-104">Этот интерфейс является подклассом интерфейса ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="dba1b-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dba1b-105">Методы</span><span class="sxs-lookup"><span data-stu-id="dba1b-105">Methods</span></span>  
  
|<span data-ttu-id="dba1b-106">Метод</span><span class="sxs-lookup"><span data-stu-id="dba1b-106">Method</span></span>|<span data-ttu-id="dba1b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="dba1b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dba1b-108">Метод CanSetIP</span><span class="sxs-lookup"><span data-stu-id="dba1b-108">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|<span data-ttu-id="dba1b-109">Возвращает значение, указывающее, можно ли задать для указателя инструкции заданное расположение смещения.</span><span class="sxs-lookup"><span data-stu-id="dba1b-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="dba1b-110">Метод EnumerateArguments</span><span class="sxs-lookup"><span data-stu-id="dba1b-110">EnumerateArguments Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="dba1b-111">Возвращает перечислитель для аргументов в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="dba1b-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="dba1b-112">Метод EnumerateLocalVariables</span><span class="sxs-lookup"><span data-stu-id="dba1b-112">EnumerateLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="dba1b-113">Возвращает перечислитель для локальных переменных в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="dba1b-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="dba1b-114">Метод GetArgument</span><span class="sxs-lookup"><span data-stu-id="dba1b-114">GetArgument Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|<span data-ttu-id="dba1b-115">Возвращает значение указанного аргумента в этом кадре стека MSIL.</span><span class="sxs-lookup"><span data-stu-id="dba1b-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="dba1b-116">Метод GetIP</span><span class="sxs-lookup"><span data-stu-id="dba1b-116">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|<span data-ttu-id="dba1b-117">Возвращает значение указателя инструкции и битовое значение сочетания, которое описывает, как было получено значение указателя инструкции.</span><span class="sxs-lookup"><span data-stu-id="dba1b-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="dba1b-118">Метод GetLocalVariable</span><span class="sxs-lookup"><span data-stu-id="dba1b-118">GetLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="dba1b-119">Возвращает значение указанной локальной переменной в этом кадре стека MSIL.</span><span class="sxs-lookup"><span data-stu-id="dba1b-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="dba1b-120">Метод GetStackDepth</span><span class="sxs-lookup"><span data-stu-id="dba1b-120">GetStackDepth Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="dba1b-121">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="dba1b-121">Not implemented.</span></span>|  
|[<span data-ttu-id="dba1b-122">Метод GetStackValue</span><span class="sxs-lookup"><span data-stu-id="dba1b-122">GetStackValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="dba1b-123">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="dba1b-123">Not implemented.</span></span>|  
|[<span data-ttu-id="dba1b-124">Метод SetIP</span><span class="sxs-lookup"><span data-stu-id="dba1b-124">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|<span data-ttu-id="dba1b-125">Устанавливает указатель инструкции на указанное положение смещения в коде MSIL.</span><span class="sxs-lookup"><span data-stu-id="dba1b-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dba1b-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="dba1b-126">Remarks</span></span>  
 <span data-ttu-id="dba1b-127">Интерфейс `ICorDebugILFrame` является специализированным интерфейсом ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="dba1b-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="dba1b-128">Он используется либо для кадров кода MSIL, либо для кадров, скомпилированных JIT.</span><span class="sxs-lookup"><span data-stu-id="dba1b-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="dba1b-129">JIT-скомпилированные кадры реализуют как интерфейс `ICorDebugILFrame`, так и интерфейс ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="dba1b-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dba1b-130">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="dba1b-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dba1b-131">Требования</span><span class="sxs-lookup"><span data-stu-id="dba1b-131">Requirements</span></span>  
 <span data-ttu-id="dba1b-132">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dba1b-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dba1b-133">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dba1b-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dba1b-134">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dba1b-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dba1b-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dba1b-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dba1b-136">См. также</span><span class="sxs-lookup"><span data-stu-id="dba1b-136">See also</span></span>

- [<span data-ttu-id="dba1b-137">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="dba1b-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
