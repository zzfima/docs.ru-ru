---
title: "Метод ICorDebug::CanLaunchOrAttach"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.CanLaunchOrAttach
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::CanLaunchOrAttach
helpviewer_keywords:
- ICorDebug::CanLaunchOrAttach method [.NET Framework debugging]
- CanLaunchOrAttach method [.NET Framework debugging]
ms.assetid: ca7723db-7c07-4cdd-bd92-fba34928b623
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 62ebdb178ef7aaa16bcc163e42662e1d69f1f6f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcanlaunchorattach-method"></a><span data-ttu-id="82cc6-102">Метод ICorDebug::CanLaunchOrAttach</span><span class="sxs-lookup"><span data-stu-id="82cc6-102">ICorDebug::CanLaunchOrAttach Method</span></span>
<span data-ttu-id="82cc6-103">Возвращает значение HRESULT, указывающее, возможна ли запуск нового процесса или вложение указанным существующий процесс в контексте текущей конфигурации компьютера и среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="82cc6-103">Returns an HRESULT that indicates whether launching a new process or attaching to the specified existing process is possible within the context of the current machine and runtime configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82cc6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82cc6-104">Syntax</span></span>  
  
```  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82cc6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="82cc6-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="82cc6-106">[in] Идентификатор существующего процесса.</span><span class="sxs-lookup"><span data-stu-id="82cc6-106">[in] The ID of an existing process.</span></span>  
  
 `win32DebuggingEnabled`  
 <span data-ttu-id="82cc6-107">[in] Передайте `true` Если планируется запускать с включенной отладкой Win32 или присоединение с отладкой Win32; в противном случае, передайте `false`.</span><span class="sxs-lookup"><span data-stu-id="82cc6-107">[in] Pass in `true` if you plan to launch with Win32 debugging enabled, or to attach with Win32 debugging enabled; otherwise, pass `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82cc6-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="82cc6-108">Return Value</span></span>  
 <span data-ttu-id="82cc6-109">Значение S_OK, если службы отладки определения того, что запуск нового процесса или вложение в данный процесс можно, информацию о текущей конфигурации компьютера и среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="82cc6-109">S_OK if the debugging services determine that launching a new process or attaching to the given process is possible, given the information about the current machine and runtime configuration.</span></span> <span data-ttu-id="82cc6-110">Приведены возможные значения HRESULT.</span><span class="sxs-lookup"><span data-stu-id="82cc6-110">Possible HRESULT values are:</span></span>  
  
-   <span data-ttu-id="82cc6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="82cc6-111">S_OK</span></span>  
  
-   <span data-ttu-id="82cc6-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span><span class="sxs-lookup"><span data-stu-id="82cc6-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span></span>  
  
-   <span data-ttu-id="82cc6-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span><span class="sxs-lookup"><span data-stu-id="82cc6-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span></span>  
  
-   <span data-ttu-id="82cc6-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span><span class="sxs-lookup"><span data-stu-id="82cc6-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82cc6-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="82cc6-115">Remarks</span></span>  
 <span data-ttu-id="82cc6-116">Этот метод носит исключительно информационный характер.</span><span class="sxs-lookup"><span data-stu-id="82cc6-116">This method is purely informational.</span></span> <span data-ttu-id="82cc6-117">Интерфейс не будет останавливать можно запускать или присоединение к процессу, независимо от значения, возвращенные `CanLaunchOrAttach`.</span><span class="sxs-lookup"><span data-stu-id="82cc6-117">The interface will not stop you from launching or attaching to a process, regardless of the value returned by `CanLaunchOrAttach`.</span></span>  
  
 <span data-ttu-id="82cc6-118">Если вы планируете запускать с включенной отладкой Win32 или присоединить с включенной отладкой Win32, передает `true` для `win32DebuggingEnabled`.</span><span class="sxs-lookup"><span data-stu-id="82cc6-118">If you plan to launch with Win32 debugging enabled or attach with Win32 debugging enabled, pass `true` for `win32DebuggingEnabled`.</span></span> <span data-ttu-id="82cc6-119">Значение HRESULT, возвращенное `CanLaunchOrAttach` могут отличаться, если этот параметр используется.</span><span class="sxs-lookup"><span data-stu-id="82cc6-119">The HRESULT returned by `CanLaunchOrAttach` might differ if you use this option.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82cc6-120">Требования</span><span class="sxs-lookup"><span data-stu-id="82cc6-120">Requirements</span></span>  
 <span data-ttu-id="82cc6-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82cc6-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82cc6-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="82cc6-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="82cc6-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82cc6-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82cc6-124">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82cc6-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82cc6-125">См. также</span><span class="sxs-lookup"><span data-stu-id="82cc6-125">See Also</span></span>  
 [<span data-ttu-id="82cc6-126">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="82cc6-126">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
