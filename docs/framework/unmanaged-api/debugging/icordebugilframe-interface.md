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
ms.openlocfilehash: 1c60d7685de1e9a1d4f631ad1fba53b981829f58
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159806"
---
# <a name="icordebugilframe-interface"></a><span data-ttu-id="c6788-102">Интерфейс ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="c6788-102">ICorDebugILFrame Interface</span></span>

<span data-ttu-id="c6788-103">Представляет кадр стека кода промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="c6788-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="c6788-104">Этот интерфейс является подклассом ICorDebugFrame-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="c6788-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c6788-105">Методы</span><span class="sxs-lookup"><span data-stu-id="c6788-105">Methods</span></span>  
  
|<span data-ttu-id="c6788-106">Метод</span><span class="sxs-lookup"><span data-stu-id="c6788-106">Method</span></span>|<span data-ttu-id="c6788-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c6788-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c6788-108">Метод CanSetIP</span><span class="sxs-lookup"><span data-stu-id="c6788-108">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|<span data-ttu-id="c6788-109">Получает значение, указывающее, является ли он безопасным задать указатель инструкций в указанное расположение смещения.</span><span class="sxs-lookup"><span data-stu-id="c6788-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="c6788-110">Метод EnumerateArguments</span><span class="sxs-lookup"><span data-stu-id="c6788-110">EnumerateArguments Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="c6788-111">Получает перечислитель для аргументов в кадре.</span><span class="sxs-lookup"><span data-stu-id="c6788-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="c6788-112">Метод EnumerateLocalVariables</span><span class="sxs-lookup"><span data-stu-id="c6788-112">EnumerateLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="c6788-113">Получает перечислитель для локальных переменных в кадре.</span><span class="sxs-lookup"><span data-stu-id="c6788-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="c6788-114">Метод GetArgument</span><span class="sxs-lookup"><span data-stu-id="c6788-114">GetArgument Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|<span data-ttu-id="c6788-115">Получает значение указанного аргумента в кадре стека MSIL.</span><span class="sxs-lookup"><span data-stu-id="c6788-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="c6788-116">Метод GetIP</span><span class="sxs-lookup"><span data-stu-id="c6788-116">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|<span data-ttu-id="c6788-117">Возвращает значение указателя инструкций и битовую комбинацию значение, которое описывает, как было получено значение указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="c6788-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="c6788-118">Метод GetLocalVariable</span><span class="sxs-lookup"><span data-stu-id="c6788-118">GetLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="c6788-119">Получает значение указанной локальной переменной в кадре стека MSIL.</span><span class="sxs-lookup"><span data-stu-id="c6788-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="c6788-120">Метод GetStackDepth</span><span class="sxs-lookup"><span data-stu-id="c6788-120">GetStackDepth Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="c6788-121">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="c6788-121">Not implemented.</span></span>|  
|[<span data-ttu-id="c6788-122">Метод GetStackValue</span><span class="sxs-lookup"><span data-stu-id="c6788-122">GetStackValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="c6788-123">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="c6788-123">Not implemented.</span></span>|  
|[<span data-ttu-id="c6788-124">Метод SetIP</span><span class="sxs-lookup"><span data-stu-id="c6788-124">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|<span data-ttu-id="c6788-125">Задает указатель инструкций в указанное расположение смещения в MSIL-код.</span><span class="sxs-lookup"><span data-stu-id="c6788-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6788-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="c6788-126">Remarks</span></span>  
 <span data-ttu-id="c6788-127">`ICorDebugILFrame` Это специализированный интерфейс ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="c6788-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="c6788-128">Он используется для фреймов кода MSIL или just-in-time (JIT) компиляции кадров.</span><span class="sxs-lookup"><span data-stu-id="c6788-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="c6788-129">Кадры JIT-компиляции реализовывать `ICorDebugILFrame` интерфейс и интерфейс ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="c6788-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6788-130">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="c6788-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6788-131">Требования</span><span class="sxs-lookup"><span data-stu-id="c6788-131">Requirements</span></span>  
 <span data-ttu-id="c6788-132">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6788-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6788-133">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6788-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6788-134">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6788-134">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c6788-135">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c6788-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c6788-136">См. также</span><span class="sxs-lookup"><span data-stu-id="c6788-136">See also</span></span>

- [<span data-ttu-id="c6788-137">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c6788-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
