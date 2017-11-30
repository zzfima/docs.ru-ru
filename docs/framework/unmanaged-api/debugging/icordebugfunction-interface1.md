---
title: "ICorDebugFunction интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction
helpviewer_keywords: ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 327ef9f74e94e3b1b20e78eb6a833038b5bfe16d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunction-interface1"></a><span data-ttu-id="b9012-102">ICorDebugFunction интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b9012-102">ICorDebugFunction Interface1</span></span>
<span data-ttu-id="b9012-103">Представляет управляемую функцию или метод.</span><span class="sxs-lookup"><span data-stu-id="b9012-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b9012-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b9012-104">Methods</span></span>  
  
|<span data-ttu-id="b9012-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b9012-105">Method</span></span>|<span data-ttu-id="b9012-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b9012-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b9012-107">Метод CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="b9012-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="b9012-108">Создает точку останова в начале этой функции.</span><span class="sxs-lookup"><span data-stu-id="b9012-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="b9012-109">Метод GetClass</span><span class="sxs-lookup"><span data-stu-id="b9012-109">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|<span data-ttu-id="b9012-110">Возвращает объект ICorDebugClass, представляющий класс, членом которых является эта функция.</span><span class="sxs-lookup"><span data-stu-id="b9012-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="b9012-111">Метод GetCurrentVersionNumber</span><span class="sxs-lookup"><span data-stu-id="b9012-111">GetCurrentVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="b9012-112">Получает номер версии последней правки этой функции.</span><span class="sxs-lookup"><span data-stu-id="b9012-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="b9012-113">Метод GetILCode</span><span class="sxs-lookup"><span data-stu-id="b9012-113">GetILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|<span data-ttu-id="b9012-114">Возвращает код на промежуточном языке (MSIL) для этой функции.</span><span class="sxs-lookup"><span data-stu-id="b9012-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="b9012-115">Метод GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="b9012-115">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="b9012-116">Получает маркер метаданных для подписи локальной переменной функции, представленный этим `ICorDebugFunction` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b9012-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="b9012-117">GetModule-метод</span><span class="sxs-lookup"><span data-stu-id="b9012-117">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|<span data-ttu-id="b9012-118">Возвращает модуль, в котором определена эта функция.</span><span class="sxs-lookup"><span data-stu-id="b9012-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="b9012-119">Метод GetNativeCode</span><span class="sxs-lookup"><span data-stu-id="b9012-119">GetNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|<span data-ttu-id="b9012-120">Получает машинный код для этой функции.</span><span class="sxs-lookup"><span data-stu-id="b9012-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="b9012-121">Метод GetToken</span><span class="sxs-lookup"><span data-stu-id="b9012-121">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|<span data-ttu-id="b9012-122">Получает маркер метаданных для этой функции.</span><span class="sxs-lookup"><span data-stu-id="b9012-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9012-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="b9012-123">Remarks</span></span>  
 <span data-ttu-id="b9012-124">`ICorDebugFunction` Интерфейса не представляет функцию с параметрами универсального типа.</span><span class="sxs-lookup"><span data-stu-id="b9012-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="b9012-125">Например `ICorDebugFunction` представляет экземпляр `Func<T>` , но не `Func<string>`.</span><span class="sxs-lookup"><span data-stu-id="b9012-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="b9012-126">Вызовите [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) для получения параметров универсального типа.</span><span class="sxs-lookup"><span data-stu-id="b9012-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="b9012-127">Связь между токен метаданных метода, `mdMethodDef`, а также метод `ICorDebugFunction` объекта зависит от того, разрешено ли на функцию Изменить и продолжить:</span><span class="sxs-lookup"><span data-stu-id="b9012-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
-   <span data-ttu-id="b9012-128">Если изменить и продолжить не разрешен в функции, между существует однозначное `ICorDebugFunction` объекта и `mdMethodDef` маркеров.</span><span class="sxs-lookup"><span data-stu-id="b9012-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="b9012-129">То есть функция имеет один `ICorDebugFunction` объекта и один `mdMethodDef` токена.</span><span class="sxs-lookup"><span data-stu-id="b9012-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
-   <span data-ttu-id="b9012-130">Если на функцию может изменить и продолжить, многие к одному связь существует между `ICorDebugFunction` объекта и `mdMethodDef` маркеров.</span><span class="sxs-lookup"><span data-stu-id="b9012-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="b9012-131">То есть функция может иметь много экземпляров `ICorDebugFunction`, один для каждой версии функции, но только один `mdMethodDef` токена.</span><span class="sxs-lookup"><span data-stu-id="b9012-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b9012-132">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="b9012-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9012-133">Требования</span><span class="sxs-lookup"><span data-stu-id="b9012-133">Requirements</span></span>  
 <span data-ttu-id="b9012-134">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9012-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9012-135">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9012-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9012-136">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9012-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9012-137">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9012-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9012-138">См. также</span><span class="sxs-lookup"><span data-stu-id="b9012-138">See Also</span></span>  
 [<span data-ttu-id="b9012-139">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b9012-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
