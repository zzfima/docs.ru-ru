---
title: Метод ICorDebug::CanLaunchOrAttach
ms.date: 03/30/2017
api_name:
- ICorDebug.CanLaunchOrAttach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CanLaunchOrAttach
helpviewer_keywords:
- ICorDebug::CanLaunchOrAttach method [.NET Framework debugging]
- CanLaunchOrAttach method [.NET Framework debugging]
ms.assetid: ca7723db-7c07-4cdd-bd92-fba34928b623
topic_type:
- apiref
ms.openlocfilehash: 805f9a5d1f2590a06bfa929c152bdfd13900531a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134284"
---
# <a name="icordebugcanlaunchorattach-method"></a><span data-ttu-id="a0625-102">Метод ICorDebug::CanLaunchOrAttach</span><span class="sxs-lookup"><span data-stu-id="a0625-102">ICorDebug::CanLaunchOrAttach Method</span></span>
<span data-ttu-id="a0625-103">Возвращает значение HRESULT, указывающее, возможен ли запуск нового процесса или присоединение к указанному существующему процессу в контексте текущего компьютера и конфигурации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a0625-103">Returns an HRESULT that indicates whether launching a new process or attaching to the specified existing process is possible within the context of the current machine and runtime configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0625-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0625-104">Syntax</span></span>  
  
```cpp  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0625-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0625-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="a0625-106">окне Идентификатор существующего процесса.</span><span class="sxs-lookup"><span data-stu-id="a0625-106">[in] The ID of an existing process.</span></span>  
  
 `win32DebuggingEnabled`  
 <span data-ttu-id="a0625-107">окне Передайте `true`, если планируется запуск с отладкой Win32, или для подключения с включенной отладкой Win32. в противном случае передайте `false`.</span><span class="sxs-lookup"><span data-stu-id="a0625-107">[in] Pass in `true` if you plan to launch with Win32 debugging enabled, or to attach with Win32 debugging enabled; otherwise, pass `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0625-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a0625-108">Return Value</span></span>  
 <span data-ttu-id="a0625-109">Значение S_OK, если службы отладки определяют, что можно запустить новый процесс или присоединиться к заданному процессу, учитывая сведения о текущем компьютере и конфигурации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a0625-109">S_OK if the debugging services determine that launching a new process or attaching to the given process is possible, given the information about the current machine and runtime configuration.</span></span> <span data-ttu-id="a0625-110">Возможные значения HRESULT:</span><span class="sxs-lookup"><span data-stu-id="a0625-110">Possible HRESULT values are:</span></span>  
  
- <span data-ttu-id="a0625-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0625-111">S_OK</span></span>  
  
- <span data-ttu-id="a0625-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span><span class="sxs-lookup"><span data-stu-id="a0625-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span></span>  
  
- <span data-ttu-id="a0625-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span><span class="sxs-lookup"><span data-stu-id="a0625-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span></span>  
  
- <span data-ttu-id="a0625-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span><span class="sxs-lookup"><span data-stu-id="a0625-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0625-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="a0625-115">Remarks</span></span>  
 <span data-ttu-id="a0625-116">Этот метод является исключительно информационным.</span><span class="sxs-lookup"><span data-stu-id="a0625-116">This method is purely informational.</span></span> <span data-ttu-id="a0625-117">Интерфейс не будет останавливаться при запуске или присоединении к процессу независимо от значения, возвращаемого `CanLaunchOrAttach`.</span><span class="sxs-lookup"><span data-stu-id="a0625-117">The interface will not stop you from launching or attaching to a process, regardless of the value returned by `CanLaunchOrAttach`.</span></span>  
  
 <span data-ttu-id="a0625-118">Если вы планируете запустить отладчик с включенной отладкой Win32 или присоединиться с включенной отладкой Win32, передайте `true` для `win32DebuggingEnabled`.</span><span class="sxs-lookup"><span data-stu-id="a0625-118">If you plan to launch with Win32 debugging enabled or attach with Win32 debugging enabled, pass `true` for `win32DebuggingEnabled`.</span></span> <span data-ttu-id="a0625-119">Значение HRESULT, возвращаемое `CanLaunchOrAttach`, может отличаться при использовании этого параметра.</span><span class="sxs-lookup"><span data-stu-id="a0625-119">The HRESULT returned by `CanLaunchOrAttach` might differ if you use this option.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0625-120">Требования</span><span class="sxs-lookup"><span data-stu-id="a0625-120">Requirements</span></span>  
 <span data-ttu-id="a0625-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0625-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0625-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0625-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0625-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0625-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0625-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0625-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0625-125">См. также</span><span class="sxs-lookup"><span data-stu-id="a0625-125">See also</span></span>

- [<span data-ttu-id="a0625-126">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="a0625-126">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
