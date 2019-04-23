---
title: Метод ICorDebugProcess2::SetDesiredNGENCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e061c3f3dc95e63339d6fd5f82b3cb4d38a4b6c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206711"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a><span data-ttu-id="e2895-102">Метод ICorDebugProcess2::SetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="e2895-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="e2895-103">Задает флаги, которые должны быть внедрены в компилируемый образ загрузки в текущий процесс в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="e2895-103">Sets the flags that must be embedded in a precompiled image in order for the runtime to load that image into the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2895-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2895-104">Syntax</span></span>  
  
```  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2895-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e2895-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="e2895-106">[in] Значение [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) перечисление, указывающее флаги компилятора, используемый для выбора нужного предварительно скомпилированного образа.</span><span class="sxs-lookup"><span data-stu-id="e2895-106">[in] A value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the compiler flags used to select the correct pre-compiled image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2895-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="e2895-107">Remarks</span></span>  
 <span data-ttu-id="e2895-108">`SetDesiredNGENCompilerFlags` Метод задает флаги, которые должны быть внедрены в предварительно скомпилированный образ, чтобы среда выполнения будет загружать этот образ в этот процесс.</span><span class="sxs-lookup"><span data-stu-id="e2895-108">The `SetDesiredNGENCompilerFlags` method specifies the flags that must be embedded in a precompiled image so that the runtime will load that image into this process.</span></span> <span data-ttu-id="e2895-109">Флаги, установленные с помощью данного метода используются только для выбора нужного предварительно скомпилированного образа.</span><span class="sxs-lookup"><span data-stu-id="e2895-109">The flags set by this method are used only to select the correct precompiled image.</span></span> <span data-ttu-id="e2895-110">Если изображение отсутствует, среда выполнения загрузит образ Microsoft промежуточного языка MSIL и компилятор just-in-time (JIT) вместо этого.</span><span class="sxs-lookup"><span data-stu-id="e2895-110">If no such image exists, the runtime will load the Microsoft intermediate language (MSIL) image and the just-in-time (JIT) compiler instead.</span></span> <span data-ttu-id="e2895-111">В этом случае отладчик по-прежнему необходимо использовать [ICorDebugModule2::SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) метод, чтобы задать флаги для JIT-компиляцию полей.</span><span class="sxs-lookup"><span data-stu-id="e2895-111">In that case, the debugger must still use the [ICorDebugModule2::SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) method to set the flags as desired for the JIT compilation.</span></span>  
  
 <span data-ttu-id="e2895-112">Если загрузить образ, но определенную JIT-компиляцию необходимо выполнить для него (который будет в случае, если изображение содержит универсальные шаблоны), определяемое флаги компилятора `SetDesiredNGENCompilerFlags` метода будут применяться к дополнительной JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="e2895-112">If an image is loaded, but some JIT compiling must take place for that image (which will be the case if the image contains generics), the compiler flags specified by the `SetDesiredNGENCompilerFlags` method will apply to the extra JIT compilation.</span></span>  
  
 <span data-ttu-id="e2895-113">`SetDesiredNGENCompilerFlags` Метод должен вызываться во время [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="e2895-113">The `SetDesiredNGENCompilerFlags` method must be called during the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="e2895-114">Пытается вызвать `SetDesiredNGENCompilerFlags` метод впоследствии завершится с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="e2895-114">Attempts to call the `SetDesiredNGENCompilerFlags` method afterwards will fail.</span></span> <span data-ttu-id="e2895-115">Кроме того, попытки задать флаги, которые либо не определены в `CorDebugJITCompilerFlags` перечисления являются недопустим для указанного процесса, произойдет сбой.</span><span class="sxs-lookup"><span data-stu-id="e2895-115">Also, attempts to set flags that are either not defined in the `CorDebugJITCompilerFlags` enumeration or are not legal for the given process will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2895-116">Требования</span><span class="sxs-lookup"><span data-stu-id="e2895-116">Requirements</span></span>  
 <span data-ttu-id="e2895-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2895-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2895-118">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2895-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2895-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2895-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2895-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2895-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2895-121">См. также</span><span class="sxs-lookup"><span data-stu-id="e2895-121">See also</span></span>

- [<span data-ttu-id="e2895-122">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="e2895-122">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="e2895-123">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="e2895-123">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
