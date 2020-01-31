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
ms.openlocfilehash: e2aaf902afd71a4a81f7d64ef3fec046aacc91fc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792533"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a><span data-ttu-id="09295-102">Метод ICorDebugProcess2::ClearUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="09295-102">ICorDebugProcess2::ClearUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="09295-103">Удаляет ранее установленную точку останова по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="09295-103">Removes a previously set breakpoint at the given address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09295-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09295-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09295-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="09295-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="09295-106">окне Значение `CORDB_ADDRESS`, указывающее адрес, по которому была задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="09295-106">[in] A `CORDB_ADDRESS` value that specifies the address at which the breakpoint was set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09295-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="09295-107">Remarks</span></span>  
 <span data-ttu-id="09295-108">Указанная точка останова была ранее задана предыдущим вызовом метода [ICorDebugProcess2:: сетунманажедбреакпоинт](icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="09295-108">The specified breakpoint would have been previously set by an earlier call to [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="09295-109">Метод `ClearUnmanagedBreakpoint` можно вызвать во время выполнения отлаживаемого процесса.</span><span class="sxs-lookup"><span data-stu-id="09295-109">The `ClearUnmanagedBreakpoint` method can be called while the process being debugged is running.</span></span>  
  
 <span data-ttu-id="09295-110">Метод `ClearUnmanagedBreakpoint` возвращает код ошибки, если отладчик присоединен в режиме "только управляемый" или если в указанном адресе не существует точки останова.</span><span class="sxs-lookup"><span data-stu-id="09295-110">The `ClearUnmanagedBreakpoint` method returns a failure code if the debugger is attached in managed-only mode or if no breakpoint exists at the specified address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09295-111">Требования</span><span class="sxs-lookup"><span data-stu-id="09295-111">Requirements</span></span>  
 <span data-ttu-id="09295-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09295-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09295-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09295-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09295-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09295-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09295-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09295-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
