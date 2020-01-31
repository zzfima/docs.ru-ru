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
ms.openlocfilehash: 7a27b8ec512498c7bf817aca36267c37d8070a4c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788583"
---
# <a name="icordebugilframe-interface"></a><span data-ttu-id="1b922-102">Интерфейс ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="1b922-102">ICorDebugILFrame Interface</span></span>

<span data-ttu-id="1b922-103">Представляет кадр стека кода промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="1b922-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="1b922-104">Этот интерфейс является подклассом интерфейса ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="1b922-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1b922-105">Методы</span><span class="sxs-lookup"><span data-stu-id="1b922-105">Methods</span></span>  
  
|<span data-ttu-id="1b922-106">Метод</span><span class="sxs-lookup"><span data-stu-id="1b922-106">Method</span></span>|<span data-ttu-id="1b922-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1b922-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1b922-108">Метод CanSetIP</span><span class="sxs-lookup"><span data-stu-id="1b922-108">CanSetIP Method</span></span>](icordebugilframe-cansetip-method.md)|<span data-ttu-id="1b922-109">Возвращает значение, указывающее, можно ли задать для указателя инструкции заданное расположение смещения.</span><span class="sxs-lookup"><span data-stu-id="1b922-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="1b922-110">Метод EnumerateArguments</span><span class="sxs-lookup"><span data-stu-id="1b922-110">EnumerateArguments Method</span></span>](icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="1b922-111">Возвращает перечислитель для аргументов в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="1b922-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="1b922-112">Метод EnumerateLocalVariables</span><span class="sxs-lookup"><span data-stu-id="1b922-112">EnumerateLocalVariables Method</span></span>](icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="1b922-113">Возвращает перечислитель для локальных переменных в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="1b922-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="1b922-114">Метод GetArgument</span><span class="sxs-lookup"><span data-stu-id="1b922-114">GetArgument Method</span></span>](icordebugilframe-getargument-method.md)|<span data-ttu-id="1b922-115">Возвращает значение указанного аргумента в этом кадре стека MSIL.</span><span class="sxs-lookup"><span data-stu-id="1b922-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="1b922-116">Метод GetIP</span><span class="sxs-lookup"><span data-stu-id="1b922-116">GetIP Method</span></span>](icordebugilframe-getip-method.md)|<span data-ttu-id="1b922-117">Возвращает значение указателя инструкции и битовое значение сочетания, которое описывает, как было получено значение указателя инструкции.</span><span class="sxs-lookup"><span data-stu-id="1b922-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="1b922-118">Метод GetLocalVariable</span><span class="sxs-lookup"><span data-stu-id="1b922-118">GetLocalVariable Method</span></span>](icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="1b922-119">Возвращает значение указанной локальной переменной в этом кадре стека MSIL.</span><span class="sxs-lookup"><span data-stu-id="1b922-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="1b922-120">Метод GetStackDepth</span><span class="sxs-lookup"><span data-stu-id="1b922-120">GetStackDepth Method</span></span>](icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="1b922-121">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="1b922-121">Not implemented.</span></span>|  
|[<span data-ttu-id="1b922-122">Метод GetStackValue</span><span class="sxs-lookup"><span data-stu-id="1b922-122">GetStackValue Method</span></span>](icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="1b922-123">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="1b922-123">Not implemented.</span></span>|  
|[<span data-ttu-id="1b922-124">Метод SetIP</span><span class="sxs-lookup"><span data-stu-id="1b922-124">SetIP Method</span></span>](icordebugilframe-setip-method.md)|<span data-ttu-id="1b922-125">Устанавливает указатель инструкции на указанное положение смещения в коде MSIL.</span><span class="sxs-lookup"><span data-stu-id="1b922-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b922-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="1b922-126">Remarks</span></span>  
 <span data-ttu-id="1b922-127">Интерфейс `ICorDebugILFrame` является специализированным интерфейсом ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="1b922-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="1b922-128">Он используется либо для кадров кода MSIL, либо для кадров, скомпилированных JIT.</span><span class="sxs-lookup"><span data-stu-id="1b922-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="1b922-129">JIT-скомпилированные кадры реализуют как интерфейс `ICorDebugILFrame`, так и интерфейс ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="1b922-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1b922-130">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="1b922-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b922-131">Требования</span><span class="sxs-lookup"><span data-stu-id="1b922-131">Requirements</span></span>  
 <span data-ttu-id="1b922-132">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b922-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b922-133">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b922-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b922-134">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b922-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b922-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b922-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b922-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="1b922-136">See also</span></span>

- [<span data-ttu-id="1b922-137">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1b922-137">Debugging Interfaces</span></span>](debugging-interfaces.md)
