---
title: Метод ICorDebug::DebugActiveProcess
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9cdee0d111c18d7bdf8c91ed4cbb368504ca3b2d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538314"
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="e0f13-102">Метод ICorDebug::DebugActiveProcess</span><span class="sxs-lookup"><span data-stu-id="e0f13-102">ICorDebug::DebugActiveProcess Method</span></span>
<span data-ttu-id="e0f13-103">Присоединяет отладчик к существующему процессу.</span><span class="sxs-lookup"><span data-stu-id="e0f13-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0f13-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0f13-104">Syntax</span></span>  
  
```  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0f13-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e0f13-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="e0f13-106">[in] Идентификатор процесса, к которому отладчик должен быть связан.</span><span class="sxs-lookup"><span data-stu-id="e0f13-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="e0f13-107">[in] Логическое значение, которое будет присвоено `true` Если отладчик должен вести себя как отладчик Win32 для процесса и отправки неуправляемых обратных вызовов; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="e0f13-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="e0f13-108">[out] Указатель на адрес объекта «ICorDebugProcess», представляющий процесс, к которому присоединен отладчик.</span><span class="sxs-lookup"><span data-stu-id="e0f13-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0f13-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="e0f13-109">Remarks</span></span>  
 <span data-ttu-id="e0f13-110">Отладки взаимодействия не поддерживается в операционных системах Win9x и не — x86 платформ, таких как основе AMD64 и IA-64-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="e0f13-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0f13-111">Требования</span><span class="sxs-lookup"><span data-stu-id="e0f13-111">Requirements</span></span>  
 <span data-ttu-id="e0f13-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0f13-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0f13-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0f13-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0f13-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0f13-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0f13-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0f13-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0f13-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e0f13-116">See also</span></span>
- [<span data-ttu-id="e0f13-117">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="e0f13-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
