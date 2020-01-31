---
title: Метод ICorDebugMutableDataTarget::SetThreadContext
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
ms.openlocfilehash: 063c7954543174caece6f3dcbe005a4b2d059c64
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792848"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="0692f-102">Метод ICorDebugMutableDataTarget::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="0692f-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="0692f-103">Задает контекст (значения регистра) для потока.</span><span class="sxs-lookup"><span data-stu-id="0692f-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0692f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0692f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0692f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0692f-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="0692f-106">[in] Идентификатор потока, определяемый операционной системой.</span><span class="sxs-lookup"><span data-stu-id="0692f-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="0692f-107">[in] Размер буфера `pContext` для записи.</span><span class="sxs-lookup"><span data-stu-id="0692f-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="0692f-108">[in] Указатель на байты, которые требуется записать.</span><span class="sxs-lookup"><span data-stu-id="0692f-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0692f-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="0692f-109">Remarks</span></span>  
 <span data-ttu-id="0692f-110">Метод `SetThreadContext` обновляет текущий контекст для потока, указанного аргументом `dwThreadID`, который задается операционной системой.</span><span class="sxs-lookup"><span data-stu-id="0692f-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="0692f-111">Формат записи контекста определяется платформой, указанной в методе [ICorDebugDataTarget::-Platform](icordebugdatatarget-getplatform-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0692f-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="0692f-112">В Windows это структура [контекста](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) .</span><span class="sxs-lookup"><span data-stu-id="0692f-112">On Windows, this is a [CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0692f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0692f-113">Requirements</span></span>  
 <span data-ttu-id="0692f-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0692f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0692f-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0692f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0692f-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0692f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0692f-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0692f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0692f-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="0692f-118">See also</span></span>

- [<span data-ttu-id="0692f-119">Интерфейс ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="0692f-119">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="0692f-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0692f-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
