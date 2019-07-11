---
title: Метод ICorDebugModule2::SetJITCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJITCompilerFlags
helpviewer_keywords:
- ICorDebugModule2::SetJITCompilerFlags method [.NET Framework debugging]
- SetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: ea574c84-c622-4589-9a14-b55771af5e06
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 114f4ff261d9612a81d17bf5b3df2f87323f77f2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764201"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a><span data-ttu-id="caac4-102">Метод ICorDebugModule2::SetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="caac4-102">ICorDebugModule2::SetJITCompilerFlags Method</span></span>
<span data-ttu-id="caac4-103">Задает флаги, определяющие компиляции этого ICorDebugModule2 just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="caac4-103">Sets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caac4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="caac4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="caac4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="caac4-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="caac4-106">[in] Побитовое сочетание [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="caac4-106">[in] A bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="caac4-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="caac4-107">Remarks</span></span>  
 <span data-ttu-id="caac4-108">Если `dwFlags` значение является недопустимым, `SetJITCompilerFlags` метод завершится с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="caac4-108">If the `dwFlags` value is invalid, the `SetJITCompilerFlags` method will fail.</span></span>  
  
 <span data-ttu-id="caac4-109">`SetJITCompilerFlags` Метод может вызываться только в пределах [ICorDebugManagedCallback::LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) обратного вызова для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="caac4-109">The `SetJITCompilerFlags` method can be called only from within the [ICorDebugManagedCallback::LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) callback for this module.</span></span> <span data-ttu-id="caac4-110">Пытается вызвать его после `ICorDebugManagedCallback::LoadModule` обратного вызова доставки будет ошибкой.</span><span class="sxs-lookup"><span data-stu-id="caac4-110">Attempts to call it after the `ICorDebugManagedCallback::LoadModule` callback has been delivered will fail.</span></span>  
  
 <span data-ttu-id="caac4-111">Изменить и продолжить в 64-разрядной или платформах операционных системах Win9x не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="caac4-111">Edit and Continue is not supported on 64-bit or Win9x platforms.</span></span> <span data-ttu-id="caac4-112">Таким образом при вызове метода `SetJITCompilerFlags` метод на любой из этих двух платформ с флагом CORDEBUG_JIT_ENABLE_ENC, установленным `dwFlags`, `SetJITCompilerFlags` метод и всех методах, используемых для изменения и продолжить, такие как [ICorDebugModule2:: Метод ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="caac4-112">Therefore, if you call the `SetJITCompilerFlags` method on either of these two platforms with the CORDEBUG_JIT_ENABLE_ENC flag set in `dwFlags`, the `SetJITCompilerFlags` method and all methods specific to Edit and Continue, such as [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caac4-113">Требования</span><span class="sxs-lookup"><span data-stu-id="caac4-113">Requirements</span></span>  
 <span data-ttu-id="caac4-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="caac4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caac4-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="caac4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="caac4-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="caac4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="caac4-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caac4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
