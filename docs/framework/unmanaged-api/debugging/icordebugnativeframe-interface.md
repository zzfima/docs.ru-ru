---
title: "ICorDebugNativeFrame интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame
helpviewer_keywords: ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 63d631dec00e63d6ee383cd36d79382a529d9ddb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframe-interface1"></a><span data-ttu-id="db152-102">ICorDebugNativeFrame интерфейс1</span><span class="sxs-lookup"><span data-stu-id="db152-102">ICorDebugNativeFrame Interface1</span></span>
<span data-ttu-id="db152-103">Специализированная реализация ICorDebugFrame, используемый для кадров машинного кода.</span><span class="sxs-lookup"><span data-stu-id="db152-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="db152-104">Методы</span><span class="sxs-lookup"><span data-stu-id="db152-104">Methods</span></span>  
  
|<span data-ttu-id="db152-105">Метод</span><span class="sxs-lookup"><span data-stu-id="db152-105">Method</span></span>|<span data-ttu-id="db152-106">Описание</span><span class="sxs-lookup"><span data-stu-id="db152-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="db152-107">Метод CanSetIP</span><span class="sxs-lookup"><span data-stu-id="db152-107">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="db152-108">Возвращает значение, указывающее, можно ли безопасно значение указателя инструкций заданное расположение смещения в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="db152-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="db152-109">Метод GetIP</span><span class="sxs-lookup"><span data-stu-id="db152-109">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|<span data-ttu-id="db152-110">Возвращает смещение кадра стека в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="db152-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="db152-111">Метод GetLocalDoubleRegisterValue</span><span class="sxs-lookup"><span data-stu-id="db152-111">GetLocalDoubleRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="db152-112">Возвращает указатель на интерфейс ICorDebugValue, представляющее значение аргумента или локальной переменной, хранящихся в двух регистрах памяти фрейм машинного кода.</span><span class="sxs-lookup"><span data-stu-id="db152-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="db152-113">Метод GetLocalMemoryRegisterValue</span><span class="sxs-lookup"><span data-stu-id="db152-113">GetLocalMemoryRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="db152-114">Возвращает указатель на `ICorDebugValue` , представляющий значение локальной переменной, которой младшие бита хранятся в указанном регистре, а старшие бита хранятся по указанному адресу памяти.</span><span class="sxs-lookup"><span data-stu-id="db152-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="db152-115">Метод GetLocalMemoryValue</span><span class="sxs-lookup"><span data-stu-id="db152-115">GetLocalMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="db152-116">Возвращает указатель на `ICorDebugValue` , представляющий значение локальной переменной, хранящейся по указанному адресу памяти.</span><span class="sxs-lookup"><span data-stu-id="db152-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="db152-117">Метод GetLocalRegisterMemoryValue</span><span class="sxs-lookup"><span data-stu-id="db152-117">GetLocalRegisterMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="db152-118">Возвращает указатель на `ICorDebugValue` , представляющий значение локальной переменной, которой верхних бита хранятся в указанном регистре, а младшие бита хранятся по указанному адресу памяти</span><span class="sxs-lookup"><span data-stu-id="db152-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="db152-119">Метод GetLocalRegisterValue</span><span class="sxs-lookup"><span data-stu-id="db152-119">GetLocalRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="db152-120">Возвращает указатель на `ICorDebugValue` , представляющий значение аргумента или локальной переменной, хранящейся в указанном машинном регистре.</span><span class="sxs-lookup"><span data-stu-id="db152-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="db152-121">Метод GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="db152-121">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="db152-122">Возвращает указатель на [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) , представляющий набор для этого регистров `ICorDebugNativeFrame`.</span><span class="sxs-lookup"><span data-stu-id="db152-122">Gets a pointer to an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="db152-123">SetIP-метод</span><span class="sxs-lookup"><span data-stu-id="db152-123">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|<span data-ttu-id="db152-124">Задает указатель инструкций заданное расположение смещения в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="db152-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db152-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="db152-125">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db152-126">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="db152-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db152-127">Требования</span><span class="sxs-lookup"><span data-stu-id="db152-127">Requirements</span></span>  
 <span data-ttu-id="db152-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db152-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db152-129">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db152-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db152-130">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db152-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db152-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db152-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db152-132">См. также</span><span class="sxs-lookup"><span data-stu-id="db152-132">See Also</span></span>  
 [<span data-ttu-id="db152-133">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="db152-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
