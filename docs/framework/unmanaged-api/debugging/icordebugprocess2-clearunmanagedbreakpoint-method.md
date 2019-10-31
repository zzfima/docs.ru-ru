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
ms.openlocfilehash: 8377ead42c752d8ebe9813d9e00662b94339f8a3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137241"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a><span data-ttu-id="7840e-102">Метод ICorDebugProcess2::ClearUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="7840e-102">ICorDebugProcess2::ClearUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="7840e-103">Удаляет ранее установленную точку останова по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="7840e-103">Removes a previously set breakpoint at the given address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7840e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7840e-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7840e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7840e-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="7840e-106">окне Значение `CORDB_ADDRESS`, указывающее адрес, по которому была задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="7840e-106">[in] A `CORDB_ADDRESS` value that specifies the address at which the breakpoint was set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7840e-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="7840e-107">Remarks</span></span>  
 <span data-ttu-id="7840e-108">Указанная точка останова была ранее задана предыдущим вызовом метода [ICorDebugProcess2:: сетунманажедбреакпоинт](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="7840e-108">The specified breakpoint would have been previously set by an earlier call to [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="7840e-109">Метод `ClearUnmanagedBreakpoint` можно вызвать во время выполнения отлаживаемого процесса.</span><span class="sxs-lookup"><span data-stu-id="7840e-109">The `ClearUnmanagedBreakpoint` method can be called while the process being debugged is running.</span></span>  
  
 <span data-ttu-id="7840e-110">Метод `ClearUnmanagedBreakpoint` возвращает код ошибки, если отладчик присоединен в режиме "только управляемый" или если в указанном адресе не существует точки останова.</span><span class="sxs-lookup"><span data-stu-id="7840e-110">The `ClearUnmanagedBreakpoint` method returns a failure code if the debugger is attached in managed-only mode or if no breakpoint exists at the specified address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7840e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7840e-111">Requirements</span></span>  
 <span data-ttu-id="7840e-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7840e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7840e-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7840e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7840e-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7840e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7840e-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7840e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
