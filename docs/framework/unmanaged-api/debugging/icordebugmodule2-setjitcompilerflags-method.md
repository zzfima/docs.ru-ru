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
ms.openlocfilehash: b28e457ea0b51d320581c0fbe36574698081ea36
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792965"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a><span data-ttu-id="24f3d-102">Метод ICorDebugModule2::SetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="24f3d-102">ICorDebugModule2::SetJITCompilerFlags Method</span></span>
<span data-ttu-id="24f3d-103">Задает флаги, управляющие JIT-компиляцией этого ICorDebugModule2.</span><span class="sxs-lookup"><span data-stu-id="24f3d-103">Sets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24f3d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24f3d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24f3d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="24f3d-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="24f3d-106">окне Побитовое сочетание значений перечисления [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="24f3d-106">[in] A bitwise combination of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24f3d-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="24f3d-107">Remarks</span></span>  
 <span data-ttu-id="24f3d-108">Если `dwFlags` значение недопустимо, метод `SetJITCompilerFlags` завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="24f3d-108">If the `dwFlags` value is invalid, the `SetJITCompilerFlags` method will fail.</span></span>  
  
 <span data-ttu-id="24f3d-109">Метод `SetJITCompilerFlags` можно вызвать только в обратном вызове [ICorDebugManagedCallback:: LoadModule](icordebugmanagedcallback-loadmodule-method.md) для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="24f3d-109">The `SetJITCompilerFlags` method can be called only from within the [ICorDebugManagedCallback::LoadModule](icordebugmanagedcallback-loadmodule-method.md) callback for this module.</span></span> <span data-ttu-id="24f3d-110">Попытки вызвать его после доставки `ICorDebugManagedCallback::LoadModule`ного обратного вызова завершатся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="24f3d-110">Attempts to call it after the `ICorDebugManagedCallback::LoadModule` callback has been delivered will fail.</span></span>  
  
 <span data-ttu-id="24f3d-111">"Изменить и продолжить" не поддерживается на платформах 64-разрядных или Win9x.</span><span class="sxs-lookup"><span data-stu-id="24f3d-111">Edit and Continue is not supported on 64-bit or Win9x platforms.</span></span> <span data-ttu-id="24f3d-112">Поэтому при вызове метода `SetJITCompilerFlags` на любой из этих двух платформ с флагом CORDEBUG_JIT_ENABLE_ENC, установленным в `dwFlags`, метод `SetJITCompilerFlags` и все методы, относящиеся к Edit и Continue, такие как [ICorDebugModule2:: ApplyChanges](icordebugmodule2-applychanges-method.md), завершатся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="24f3d-112">Therefore, if you call the `SetJITCompilerFlags` method on either of these two platforms with the CORDEBUG_JIT_ENABLE_ENC flag set in `dwFlags`, the `SetJITCompilerFlags` method and all methods specific to Edit and Continue, such as [ICorDebugModule2::ApplyChanges](icordebugmodule2-applychanges-method.md), will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24f3d-113">Требования</span><span class="sxs-lookup"><span data-stu-id="24f3d-113">Requirements</span></span>  
 <span data-ttu-id="24f3d-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24f3d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24f3d-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24f3d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24f3d-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24f3d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24f3d-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24f3d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
