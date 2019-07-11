---
title: Метод ICorDebugProcess2::ClearUnmanagedBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.ClearUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::ClearUnmanagedBreakpoint
helpviewer_keywords:
- ClearUnmanagedBreakpoint method [.NET Framework debugging]
- ICorDebugProcess2::ClearUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 12ed0fff-7f0e-4d7a-bb70-b3376371f36c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9fb566ff2e5e2b0bcb096cead243ed65a904a914
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736977"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a><span data-ttu-id="c21e0-102">Метод ICorDebugProcess2::ClearUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="c21e0-102">ICorDebugProcess2::ClearUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="c21e0-103">Удаляет ранее заданной точки останова по заданному адресу.</span><span class="sxs-lookup"><span data-stu-id="c21e0-103">Removes a previously set breakpoint at the given address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c21e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c21e0-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c21e0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c21e0-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="c21e0-106">[in] Объект `CORDB_ADDRESS` значение, указывающее адрес, по которому была задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="c21e0-106">[in] A `CORDB_ADDRESS` value that specifies the address at which the breakpoint was set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c21e0-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="c21e0-107">Remarks</span></span>  
 <span data-ttu-id="c21e0-108">Указанный точки останова будет ранее заданные предыдущим вызовом [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="c21e0-108">The specified breakpoint would have been previously set by an earlier call to [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="c21e0-109">`ClearUnmanagedBreakpoint` Метод может вызываться во время работы отлаживаемого процесса.</span><span class="sxs-lookup"><span data-stu-id="c21e0-109">The `ClearUnmanagedBreakpoint` method can be called while the process being debugged is running.</span></span>  
  
 <span data-ttu-id="c21e0-110">`ClearUnmanagedBreakpoint` Метод возвращает код ошибки, если присоединен отладчик в режиме только для управляемых или если точка останова не существует по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="c21e0-110">The `ClearUnmanagedBreakpoint` method returns a failure code if the debugger is attached in managed-only mode or if no breakpoint exists at the specified address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c21e0-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c21e0-111">Requirements</span></span>  
 <span data-ttu-id="c21e0-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c21e0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c21e0-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c21e0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c21e0-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c21e0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c21e0-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c21e0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
