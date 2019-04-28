---
title: Интерфейс ICorDebugFunction
ms.date: 03/30/2017
api_name:
- ICorDebugFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction
helpviewer_keywords:
- ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca21911f3d16b79887b9d6d8185f8fab17651321
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61672995"
---
# <a name="icordebugfunction-interface"></a><span data-ttu-id="53147-102">Интерфейс ICorDebugFunction</span><span class="sxs-lookup"><span data-stu-id="53147-102">ICorDebugFunction Interface</span></span>

<span data-ttu-id="53147-103">Представляет управляемую функцию или метод.</span><span class="sxs-lookup"><span data-stu-id="53147-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="53147-104">Методы</span><span class="sxs-lookup"><span data-stu-id="53147-104">Methods</span></span>  
  
|<span data-ttu-id="53147-105">Метод</span><span class="sxs-lookup"><span data-stu-id="53147-105">Method</span></span>|<span data-ttu-id="53147-106">Описание</span><span class="sxs-lookup"><span data-stu-id="53147-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="53147-107">Метод CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="53147-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="53147-108">Создает точку останова в начале этой функции.</span><span class="sxs-lookup"><span data-stu-id="53147-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="53147-109">Метод GetClass</span><span class="sxs-lookup"><span data-stu-id="53147-109">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|<span data-ttu-id="53147-110">Возвращает объект, представляющий класс, членом которых является эта функция ICorDebugClass.</span><span class="sxs-lookup"><span data-stu-id="53147-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="53147-111">Метод GetCurrentVersionNumber</span><span class="sxs-lookup"><span data-stu-id="53147-111">GetCurrentVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="53147-112">Получает номер версии последней правки этой функции.</span><span class="sxs-lookup"><span data-stu-id="53147-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="53147-113">Метод GetILCode</span><span class="sxs-lookup"><span data-stu-id="53147-113">GetILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|<span data-ttu-id="53147-114">Получает код на промежуточном языке (MSIL) для этой функции.</span><span class="sxs-lookup"><span data-stu-id="53147-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="53147-115">Метод GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="53147-115">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="53147-116">Получает токен метаданных для подписи локальной переменной функции, представленный этим `ICorDebugFunction` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="53147-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="53147-117">Метод GetModule</span><span class="sxs-lookup"><span data-stu-id="53147-117">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|<span data-ttu-id="53147-118">Возвращает модуль, в котором определена эта функция.</span><span class="sxs-lookup"><span data-stu-id="53147-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="53147-119">Метод GetNativeCode</span><span class="sxs-lookup"><span data-stu-id="53147-119">GetNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|<span data-ttu-id="53147-120">Получает машинный код для этой функции.</span><span class="sxs-lookup"><span data-stu-id="53147-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="53147-121">Метод GetToken</span><span class="sxs-lookup"><span data-stu-id="53147-121">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|<span data-ttu-id="53147-122">Получает маркер метаданных для этой функции.</span><span class="sxs-lookup"><span data-stu-id="53147-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53147-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="53147-123">Remarks</span></span>  
 <span data-ttu-id="53147-124">`ICorDebugFunction` Интерфейса не представляет функцию с параметрами универсального типа.</span><span class="sxs-lookup"><span data-stu-id="53147-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="53147-125">Например `ICorDebugFunction` представляет экземпляр `Func<T>` , но не `Func<string>`.</span><span class="sxs-lookup"><span data-stu-id="53147-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="53147-126">Вызовите [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) для получения параметров универсального типа.</span><span class="sxs-lookup"><span data-stu-id="53147-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="53147-127">Связь между токен метаданных метода, `mdMethodDef`, а также метод `ICorDebugFunction` зависит изменить и продолжить разрешена ли функция объект:</span><span class="sxs-lookup"><span data-stu-id="53147-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
- <span data-ttu-id="53147-128">Если изменить и продолжить не допускается в функции, взаимно-однозначной связи межу `ICorDebugFunction` объекта и `mdMethodDef` маркеров.</span><span class="sxs-lookup"><span data-stu-id="53147-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="53147-129">То есть функция имеет один `ICorDebugFunction` объекта и один `mdMethodDef` токена.</span><span class="sxs-lookup"><span data-stu-id="53147-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
- <span data-ttu-id="53147-130">Если на функцию может изменить и продолжить, существует связь многие к одному между `ICorDebugFunction` объекта и `mdMethodDef` маркеров.</span><span class="sxs-lookup"><span data-stu-id="53147-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="53147-131">То есть функция может иметь несколько экземпляров `ICorDebugFunction`, один для каждой версии функции, но только один `mdMethodDef` токена.</span><span class="sxs-lookup"><span data-stu-id="53147-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53147-132">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="53147-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53147-133">Требования</span><span class="sxs-lookup"><span data-stu-id="53147-133">Requirements</span></span>  
 <span data-ttu-id="53147-134">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53147-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53147-135">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="53147-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53147-136">**Библиотека:**  CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53147-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="53147-137">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53147-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53147-138">См. также</span><span class="sxs-lookup"><span data-stu-id="53147-138">See also</span></span>

- [<span data-ttu-id="53147-139">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="53147-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
