---
title: Метод ICorDebugProcess::SetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type:
- apiref
ms.openlocfilehash: 66d544bbc0511ea76565376c8f10294f1758026b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792576"
---
# <a name="icordebugprocesssetthreadcontext-method"></a><span data-ttu-id="89751-102">Метод ICorDebugProcess::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="89751-102">ICorDebugProcess::SetThreadContext Method</span></span>
<span data-ttu-id="89751-103">Задает контекст для данного потока в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="89751-103">Sets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89751-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89751-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89751-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="89751-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="89751-106">окне Идентификатор потока, для которого задается контекст.</span><span class="sxs-lookup"><span data-stu-id="89751-106">[in] The ID of the thread for which to set the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="89751-107">[in] Размер массива `context`.</span><span class="sxs-lookup"><span data-stu-id="89751-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="89751-108">окне Массив байтов, описывающих контекст потока.</span><span class="sxs-lookup"><span data-stu-id="89751-108">[in] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="89751-109">Контекст указывает архитектуру процессора, на котором работает поток.</span><span class="sxs-lookup"><span data-stu-id="89751-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89751-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="89751-110">Remarks</span></span>  
 <span data-ttu-id="89751-111">Отладчик должен вызывать этот метод вместо функции Win32 `SetThreadContext`, так как поток может находиться в состоянии "перехвачено", в котором его контекст был временно изменен.</span><span class="sxs-lookup"><span data-stu-id="89751-111">The debugger should call this method rather than the Win32 `SetThreadContext` function, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="89751-112">Этот метод следует использовать только в том случае, если поток находится в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="89751-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="89751-113">Используйте [ICorDebugRegisterSet](icordebugregisterset-interface.md) для потоков в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="89751-113">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) for threads in managed code.</span></span> <span data-ttu-id="89751-114">Никогда не нужно изменять контекст потока во время события нестандартного управления (OOB).</span><span class="sxs-lookup"><span data-stu-id="89751-114">You should never need to modify the context of a thread during an out-of-band (OOB) debug event.</span></span>  
  
 <span data-ttu-id="89751-115">Передаваемые данные должны быть структурой контекста для текущей платформы.</span><span class="sxs-lookup"><span data-stu-id="89751-115">The data passed must be a context structure for the current platform.</span></span>  
  
 <span data-ttu-id="89751-116">Этот метод может повредить среду выполнения при неправильном использовании.</span><span class="sxs-lookup"><span data-stu-id="89751-116">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89751-117">Требования</span><span class="sxs-lookup"><span data-stu-id="89751-117">Requirements</span></span>  
 <span data-ttu-id="89751-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89751-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89751-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89751-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89751-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89751-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89751-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89751-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
