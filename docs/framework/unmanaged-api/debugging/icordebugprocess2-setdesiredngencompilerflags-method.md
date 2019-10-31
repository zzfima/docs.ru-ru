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
ms.openlocfilehash: 9313fc58dec8099f42dbff07685ca14791fa324f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137161"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a><span data-ttu-id="c4f18-102">Метод ICorDebugProcess2::SetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="c4f18-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="c4f18-103">Задает флаги, которые должны быть внедрены в предкомпилированное изображение, чтобы среда выполнения загружала этот образ в текущий процесс.</span><span class="sxs-lookup"><span data-stu-id="c4f18-103">Sets the flags that must be embedded in a precompiled image in order for the runtime to load that image into the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4f18-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4f18-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4f18-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c4f18-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="c4f18-106">окне Значение перечисления [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) , указывающее флаги компилятора, используемые для выбора правильного предварительно скомпилированного изображения.</span><span class="sxs-lookup"><span data-stu-id="c4f18-106">[in] A value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the compiler flags used to select the correct pre-compiled image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4f18-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="c4f18-107">Remarks</span></span>  
 <span data-ttu-id="c4f18-108">Метод `SetDesiredNGENCompilerFlags` задает флаги, которые должны быть внедрены в предкомпилированное изображение, чтобы среда выполнения загружала этот образ в этот процесс.</span><span class="sxs-lookup"><span data-stu-id="c4f18-108">The `SetDesiredNGENCompilerFlags` method specifies the flags that must be embedded in a precompiled image so that the runtime will load that image into this process.</span></span> <span data-ttu-id="c4f18-109">Флаги, заданные этим методом, используются только для выбора правильного предкомпилированного изображения.</span><span class="sxs-lookup"><span data-stu-id="c4f18-109">The flags set by this method are used only to select the correct precompiled image.</span></span> <span data-ttu-id="c4f18-110">Если такого образа не существует, среда выполнения загрузит образ MSIL и JIT-компилятор, вместо этого.</span><span class="sxs-lookup"><span data-stu-id="c4f18-110">If no such image exists, the runtime will load the Microsoft intermediate language (MSIL) image and the just-in-time (JIT) compiler instead.</span></span> <span data-ttu-id="c4f18-111">В этом случае отладчик должен по-прежнему использовать метод [ICorDebugModule2:: SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) , чтобы установить флаги для JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="c4f18-111">In that case, the debugger must still use the [ICorDebugModule2::SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) method to set the flags as desired for the JIT compilation.</span></span>  
  
 <span data-ttu-id="c4f18-112">Если изображение загружено, но для этого образа необходимо выполнить некоторые JIT-компиляции (что будет так, если изображение содержит универсальные шаблоны), то флаги компилятора, заданные в методе `SetDesiredNGENCompilerFlags`, будут применяться к дополнительной JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="c4f18-112">If an image is loaded, but some JIT compiling must take place for that image (which will be the case if the image contains generics), the compiler flags specified by the `SetDesiredNGENCompilerFlags` method will apply to the extra JIT compilation.</span></span>  
  
 <span data-ttu-id="c4f18-113">Метод `SetDesiredNGENCompilerFlags` должен вызываться во время обратного вызова [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c4f18-113">The `SetDesiredNGENCompilerFlags` method must be called during the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="c4f18-114">Попытка вызвать метод `SetDesiredNGENCompilerFlags` впоследствии завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c4f18-114">Attempts to call the `SetDesiredNGENCompilerFlags` method afterwards will fail.</span></span> <span data-ttu-id="c4f18-115">Кроме того, попытки установить флаги, которые либо не определены в перечислении `CorDebugJITCompilerFlags`, либо не являются допустимыми для данного процесса, завершатся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c4f18-115">Also, attempts to set flags that are either not defined in the `CorDebugJITCompilerFlags` enumeration or are not legal for the given process will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4f18-116">Требования</span><span class="sxs-lookup"><span data-stu-id="c4f18-116">Requirements</span></span>  
 <span data-ttu-id="c4f18-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4f18-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4f18-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4f18-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4f18-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4f18-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4f18-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4f18-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4f18-121">См. также</span><span class="sxs-lookup"><span data-stu-id="c4f18-121">See also</span></span>

- [<span data-ttu-id="c4f18-122">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="c4f18-122">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="c4f18-123">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="c4f18-123">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
