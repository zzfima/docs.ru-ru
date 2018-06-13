---
title: Метод ICorDebugProcess::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThreadContext
helpviewer_keywords:
- ICorDebugProcess::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: 5b132ef1-8d4b-4525-89b3-54123596c194
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea977b1ccecf9de5a04e1f1127658ca6c15043a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416544"
---
# <a name="icordebugprocessgetthreadcontext-method"></a><span data-ttu-id="29109-102">Метод ICorDebugProcess::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="29109-102">ICorDebugProcess::GetThreadContext Method</span></span>
<span data-ttu-id="29109-103">Возвращает контекст для данного потока в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="29109-103">Gets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29109-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29109-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="29109-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="29109-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="29109-106">[in] Идентификатор потока, для которого нужно получить контекст.</span><span class="sxs-lookup"><span data-stu-id="29109-106">[in] The ID of the thread for which to retrieve the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="29109-107">[in] Размер массива `context`.</span><span class="sxs-lookup"><span data-stu-id="29109-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="29109-108">[in, out] Массив байтов, описывающие контекст потока.</span><span class="sxs-lookup"><span data-stu-id="29109-108">[in, out] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="29109-109">Контекст задает архитектуру процессора, на котором выполняется поток.</span><span class="sxs-lookup"><span data-stu-id="29109-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29109-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="29109-110">Remarks</span></span>  
 <span data-ttu-id="29109-111">Отладчик должен вызвать этот метод вместо Win32 `GetThreadContext` метод, поскольку фактически поток может находиться в состоянии «крадеными», в котором его контекст был временно изменен.</span><span class="sxs-lookup"><span data-stu-id="29109-111">The debugger should call this method rather than the Win32 `GetThreadContext` method, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="29109-112">Этот метод следует использовать только в том случае, когда поток находится в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="29109-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="29109-113">Используйте [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) для потоков в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="29109-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) for threads in managed code.</span></span>  
  
 <span data-ttu-id="29109-114">Возвращаемые данные — это структура контекста для текущей платформы.</span><span class="sxs-lookup"><span data-stu-id="29109-114">The data returned is a context structure for the current platform.</span></span> <span data-ttu-id="29109-115">Как и в Win32 `GetThreadContext` метод, вызывающий объект должен инициализировать `context` параметра перед вызовом этого метода.</span><span class="sxs-lookup"><span data-stu-id="29109-115">Just as with the Win32 `GetThreadContext` method, the caller should initialize the `context` parameter before calling this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29109-116">Требования</span><span class="sxs-lookup"><span data-stu-id="29109-116">Requirements</span></span>  
 <span data-ttu-id="29109-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29109-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29109-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29109-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29109-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29109-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29109-120">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29109-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
