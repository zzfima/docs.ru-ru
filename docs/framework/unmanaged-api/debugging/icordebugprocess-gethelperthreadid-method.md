---
title: Метод ICorDebugProcess::GetHelperThreadID
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHelperThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad62b267eb0c49ff8fbefeb45b523c21edc705fe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766041"
---
# <a name="icordebugprocessgethelperthreadid-method"></a><span data-ttu-id="7b647-102">Метод ICorDebugProcess::GetHelperThreadID</span><span class="sxs-lookup"><span data-stu-id="7b647-102">ICorDebugProcess::GetHelperThreadID Method</span></span>
<span data-ttu-id="7b647-103">Получает идентификатор потока операционной системы (ОС) внутреннего вспомогательного потока отладчика.</span><span class="sxs-lookup"><span data-stu-id="7b647-103">Gets the operating system (OS) thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b647-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b647-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b647-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7b647-105">Parameters</span></span>  
 `pThreadID`  
 <span data-ttu-id="7b647-106">[out] Идентификатор внутреннего вспомогательного потока отладчика потока в указатель на ОС.</span><span class="sxs-lookup"><span data-stu-id="7b647-106">[out] A pointer to the OS thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b647-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="7b647-107">Remarks</span></span>  
 <span data-ttu-id="7b647-108">Во время отладки управляемых и неуправляемых отвечает за отладчика убедитесь, что непрерывное выполнение потока с указанным Идентификатором при его попадании в точку останова, размещенную отладчиком.</span><span class="sxs-lookup"><span data-stu-id="7b647-108">During managed and unmanaged debugging, it is the debugger's responsibility to ensure that the thread with the specified ID remains running if it hits a breakpoint placed by the debugger.</span></span> <span data-ttu-id="7b647-109">Отладчик может возникнуть необходимость скрыть этот поток от пользователя.</span><span class="sxs-lookup"><span data-stu-id="7b647-109">A debugger may also wish to hide this thread from the user.</span></span> <span data-ttu-id="7b647-110">Если существует вспомогательного потока в процессе, тем не менее, `GetHelperThreadID` метод возвращает нуль в \*`pThreadID`.</span><span class="sxs-lookup"><span data-stu-id="7b647-110">If no helper thread exists in the process yet, the `GetHelperThreadID` method returns zero in \*`pThreadID`.</span></span>  
  
 <span data-ttu-id="7b647-111">Идентификатор потока вспомогательного потока кэшировать нельзя, поскольку со временем может меняться.</span><span class="sxs-lookup"><span data-stu-id="7b647-111">You cannot cache the thread ID of the helper thread, because it may change over time.</span></span> <span data-ttu-id="7b647-112">Необходимо повторно запрашивать идентификатор потока при каждом событии остановки.</span><span class="sxs-lookup"><span data-stu-id="7b647-112">You must re-query the thread ID at every stopping event.</span></span>  
  
 <span data-ttu-id="7b647-113">Идентификатор вспомогательного потока отладчика будет корректироваться при каждой неуправляемой [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) событий, что позволяет отладчику определить идентификатор вспомогательного потока и скрыть его от пользователя.</span><span class="sxs-lookup"><span data-stu-id="7b647-113">The thread ID of the debugger's helper thread will be correct on every unmanaged [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) event, thus allowing a debugger to determine the thread ID of its helper thread and hide it from the user.</span></span> <span data-ttu-id="7b647-114">Поток, который указан в качестве вспомогательного потока во время неуправляемую `ICorDebugManagedCallback::CreateThread` событие никогда не будет выполняться управляемый пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="7b647-114">A thread that is identified as a helper thread during an unmanaged `ICorDebugManagedCallback::CreateThread` event will never run managed user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b647-115">Требования</span><span class="sxs-lookup"><span data-stu-id="7b647-115">Requirements</span></span>  
 <span data-ttu-id="7b647-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b647-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b647-117">**Заголовок.** CorDebug.idl.</span><span class="sxs-lookup"><span data-stu-id="7b647-117">**Header:** CorDebug.idl.</span></span> <span data-ttu-id="7b647-118">CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b647-118">CorDebug.h</span></span>  
  
 <span data-ttu-id="7b647-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b647-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b647-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b647-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
