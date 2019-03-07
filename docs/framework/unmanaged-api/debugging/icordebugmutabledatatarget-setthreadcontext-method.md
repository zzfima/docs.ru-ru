---
title: Метод ICorDebugMutableDataTarget::SetThreadContext
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbbe4dcec29ba85c64b6e22a4348c56e80daf623
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479198"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="f8368-102">Метод ICorDebugMutableDataTarget::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="f8368-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="f8368-103">Задает контекст (значения регистра) для потока.</span><span class="sxs-lookup"><span data-stu-id="f8368-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8368-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8368-104">Syntax</span></span>  
  
```  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8368-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f8368-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="f8368-106">[in] Идентификатор потока, определяемый операционной системой.</span><span class="sxs-lookup"><span data-stu-id="f8368-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="f8368-107">[in] Размер буфера `pContext` для записи.</span><span class="sxs-lookup"><span data-stu-id="f8368-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="f8368-108">[in] Указатель на байты, которые требуется записать.</span><span class="sxs-lookup"><span data-stu-id="f8368-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8368-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f8368-109">Remarks</span></span>  
 <span data-ttu-id="f8368-110">Метод `SetThreadContext` обновляет текущий контекст для потока, указанного аргументом `dwThreadID`, который задается операционной системой.</span><span class="sxs-lookup"><span data-stu-id="f8368-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="f8368-111">Формат записи контекста, определяется платформой, указанной методом [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="f8368-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="f8368-112">В Windows, это [контекст](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) структуры.</span><span class="sxs-lookup"><span data-stu-id="f8368-112">On Windows, this is a [CONTEXT](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8368-113">Требования</span><span class="sxs-lookup"><span data-stu-id="f8368-113">Requirements</span></span>  
 <span data-ttu-id="f8368-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8368-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8368-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8368-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8368-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8368-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8368-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8368-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8368-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f8368-118">See also</span></span>
- [<span data-ttu-id="f8368-119">Интерфейс ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="f8368-119">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="f8368-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f8368-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
