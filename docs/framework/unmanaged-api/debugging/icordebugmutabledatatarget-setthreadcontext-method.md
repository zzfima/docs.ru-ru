---
title: 'Метод Икордебугмутабледататаржет:: SetThreadContext'
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
ms.openlocfilehash: 2c9e508c7a4059fee4e1cce6eb28e6de7b2fff6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132707"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="337b9-102">Метод Икордебугмутабледататаржет:: SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="337b9-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="337b9-103">Задает контекст (значения регистра) для потока.</span><span class="sxs-lookup"><span data-stu-id="337b9-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="337b9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="337b9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="337b9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="337b9-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="337b9-106">[in] Идентификатор потока, определяемый операционной системой.</span><span class="sxs-lookup"><span data-stu-id="337b9-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="337b9-107">[in] Размер буфера `pContext` для записи.</span><span class="sxs-lookup"><span data-stu-id="337b9-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="337b9-108">[in] Указатель на байты, которые требуется записать.</span><span class="sxs-lookup"><span data-stu-id="337b9-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="337b9-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="337b9-109">Remarks</span></span>  
 <span data-ttu-id="337b9-110">Метод `SetThreadContext` обновляет текущий контекст для потока, указанного аргументом `dwThreadID`, который задается операционной системой.</span><span class="sxs-lookup"><span data-stu-id="337b9-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="337b9-111">Формат записи контекста определяется платформой, указанной в методе [ICorDebugDataTarget::-Platform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) .</span><span class="sxs-lookup"><span data-stu-id="337b9-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="337b9-112">В Windows это структура [контекста](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) .</span><span class="sxs-lookup"><span data-stu-id="337b9-112">On Windows, this is a [CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="337b9-113">Требования</span><span class="sxs-lookup"><span data-stu-id="337b9-113">Requirements</span></span>  
 <span data-ttu-id="337b9-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="337b9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="337b9-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="337b9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="337b9-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="337b9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="337b9-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="337b9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="337b9-118">См. также</span><span class="sxs-lookup"><span data-stu-id="337b9-118">See also</span></span>

- [<span data-ttu-id="337b9-119">Интерфейс ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="337b9-119">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="337b9-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="337b9-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
