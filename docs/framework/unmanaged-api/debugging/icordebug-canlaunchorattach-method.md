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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c29859a54b89956e017f06b8eeb97a6171eabbb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476221"
---
# <a name="icordebugcanlaunchorattach-method"></a><span data-ttu-id="18bde-102">Метод ICorDebug::CanLaunchOrAttach</span><span class="sxs-lookup"><span data-stu-id="18bde-102">ICorDebug::CanLaunchOrAttach Method</span></span>
<span data-ttu-id="18bde-103">Возвращает значение HRESULT, указывающее, возможна ли запуск нового процесса или вложение указанным существующий процесс в контексте текущей конфигурации компьютера и среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="18bde-103">Returns an HRESULT that indicates whether launching a new process or attaching to the specified existing process is possible within the context of the current machine and runtime configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18bde-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18bde-104">Syntax</span></span>  
  
```  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18bde-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="18bde-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="18bde-106">[in] Идентификатор существующего процесса.</span><span class="sxs-lookup"><span data-stu-id="18bde-106">[in] The ID of an existing process.</span></span>  
  
 `win32DebuggingEnabled`  
 <span data-ttu-id="18bde-107">[in] Передайте `true` Если вы планируете запустить в режиме отладки Win32 или для присоединения с помощью Win32 отладка включена; в противном случае передайте `false`.</span><span class="sxs-lookup"><span data-stu-id="18bde-107">[in] Pass in `true` if you plan to launch with Win32 debugging enabled, or to attach with Win32 debugging enabled; otherwise, pass `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18bde-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="18bde-108">Return Value</span></span>  
 <span data-ttu-id="18bde-109">Значение S_OK, если службы отладки выяснилось, что запуск нового процесса или вложение в данный процесс можно, учитывая сведения о текущей конфигурации компьютера и среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="18bde-109">S_OK if the debugging services determine that launching a new process or attaching to the given process is possible, given the information about the current machine and runtime configuration.</span></span> <span data-ttu-id="18bde-110">Ниже приведены возможные значения HRESULT.</span><span class="sxs-lookup"><span data-stu-id="18bde-110">Possible HRESULT values are:</span></span>  
  
-   <span data-ttu-id="18bde-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="18bde-111">S_OK</span></span>  
  
-   <span data-ttu-id="18bde-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span><span class="sxs-lookup"><span data-stu-id="18bde-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span></span>  
  
-   <span data-ttu-id="18bde-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span><span class="sxs-lookup"><span data-stu-id="18bde-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span></span>  
  
-   <span data-ttu-id="18bde-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span><span class="sxs-lookup"><span data-stu-id="18bde-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18bde-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="18bde-115">Remarks</span></span>  
 <span data-ttu-id="18bde-116">Этот метод носит исключительно информационный характер.</span><span class="sxs-lookup"><span data-stu-id="18bde-116">This method is purely informational.</span></span> <span data-ttu-id="18bde-117">Интерфейс не помешает вам запуск или присоединение к процессу, независимо от значения, возвращенные `CanLaunchOrAttach`.</span><span class="sxs-lookup"><span data-stu-id="18bde-117">The interface will not stop you from launching or attaching to a process, regardless of the value returned by `CanLaunchOrAttach`.</span></span>  
  
 <span data-ttu-id="18bde-118">Если вы планируете запустить в режиме отладки Win32 или присоединить с включенной отладкой Win32, передайте `true` для `win32DebuggingEnabled`.</span><span class="sxs-lookup"><span data-stu-id="18bde-118">If you plan to launch with Win32 debugging enabled or attach with Win32 debugging enabled, pass `true` for `win32DebuggingEnabled`.</span></span> <span data-ttu-id="18bde-119">Значение HRESULT, возвращаемые `CanLaunchOrAttach` могут отличаться, если вы используете этот параметр.</span><span class="sxs-lookup"><span data-stu-id="18bde-119">The HRESULT returned by `CanLaunchOrAttach` might differ if you use this option.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18bde-120">Требования</span><span class="sxs-lookup"><span data-stu-id="18bde-120">Requirements</span></span>  
 <span data-ttu-id="18bde-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18bde-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18bde-122">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18bde-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18bde-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18bde-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18bde-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18bde-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18bde-125">См. также</span><span class="sxs-lookup"><span data-stu-id="18bde-125">See also</span></span>
- [<span data-ttu-id="18bde-126">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="18bde-126">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
