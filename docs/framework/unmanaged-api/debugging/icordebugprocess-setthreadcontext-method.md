---
title: "Метод ICorDebugProcess::SetThreadContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.SetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7d40d455ea17b8df2acd77a1222ac6b080116c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocesssetthreadcontext-method"></a><span data-ttu-id="6acd0-102">Метод ICorDebugProcess::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="6acd0-102">ICorDebugProcess::SetThreadContext Method</span></span>
<span data-ttu-id="6acd0-103">Задает контекст для данного потока в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="6acd0-103">Sets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6acd0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6acd0-104">Syntax</span></span>  
  
```  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6acd0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6acd0-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="6acd0-106">[in] Идентификатор потока, для которого требуется задать контекст.</span><span class="sxs-lookup"><span data-stu-id="6acd0-106">[in] The ID of the thread for which to set the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="6acd0-107">[in] Размер массива `context`.</span><span class="sxs-lookup"><span data-stu-id="6acd0-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="6acd0-108">[in] Массив байтов, описывающие контекст потока.</span><span class="sxs-lookup"><span data-stu-id="6acd0-108">[in] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="6acd0-109">Контекст задает архитектуру процессора, на котором выполняется поток.</span><span class="sxs-lookup"><span data-stu-id="6acd0-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6acd0-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="6acd0-110">Remarks</span></span>  
 <span data-ttu-id="6acd0-111">Отладчик должен вызвать этот метод вместо Win32 `SetThreadContext` работать, поскольку фактически поток может находиться в состоянии «крадеными», в котором его контекст был временно изменен.</span><span class="sxs-lookup"><span data-stu-id="6acd0-111">The debugger should call this method rather than the Win32 `SetThreadContext` function, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="6acd0-112">Этот метод следует использовать только в том случае, когда поток находится в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="6acd0-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="6acd0-113">Используйте [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) для потоков в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="6acd0-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) for threads in managed code.</span></span> <span data-ttu-id="6acd0-114">Никогда не требуется изменить контекст потока во время события отладки по каналу (OOB).</span><span class="sxs-lookup"><span data-stu-id="6acd0-114">You should never need to modify the context of a thread during an out-of-band (OOB) debug event.</span></span>  
  
 <span data-ttu-id="6acd0-115">Переданные данные должны быть структурой контекста для текущей платформы.</span><span class="sxs-lookup"><span data-stu-id="6acd0-115">The data passed must be a context structure for the current platform.</span></span>  
  
 <span data-ttu-id="6acd0-116">Этот метод может привести к повреждению среды выполнения при неправильном.</span><span class="sxs-lookup"><span data-stu-id="6acd0-116">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6acd0-117">Требования</span><span class="sxs-lookup"><span data-stu-id="6acd0-117">Requirements</span></span>  
 <span data-ttu-id="6acd0-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6acd0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6acd0-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6acd0-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6acd0-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6acd0-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6acd0-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6acd0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
