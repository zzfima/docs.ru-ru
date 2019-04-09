---
title: Метод ICorDebugMutableDataTarget::SetThreadContext
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d8b3fd9940bd11c3d026b46247e0657c82b18099
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120007"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="14c08-102">Метод ICorDebugMutableDataTarget::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="14c08-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="14c08-103">Задает контекст (значения регистра) для потока.</span><span class="sxs-lookup"><span data-stu-id="14c08-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14c08-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14c08-104">Syntax</span></span>  
  
```  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14c08-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="14c08-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="14c08-106">[in] Идентификатор потока, определяемый операционной системой.</span><span class="sxs-lookup"><span data-stu-id="14c08-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="14c08-107">[in] Размер буфера `pContext` для записи.</span><span class="sxs-lookup"><span data-stu-id="14c08-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="14c08-108">[in] Указатель на байты, которые требуется записать.</span><span class="sxs-lookup"><span data-stu-id="14c08-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14c08-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="14c08-109">Remarks</span></span>  
 <span data-ttu-id="14c08-110">Метод `SetThreadContext` обновляет текущий контекст для потока, указанного аргументом `dwThreadID`, который задается операционной системой.</span><span class="sxs-lookup"><span data-stu-id="14c08-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="14c08-111">Формат записи контекста, определяется платформой, указанной методом [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="14c08-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="14c08-112">В Windows, это [контекст](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) структуры.</span><span class="sxs-lookup"><span data-stu-id="14c08-112">On Windows, this is a [CONTEXT](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14c08-113">Требования</span><span class="sxs-lookup"><span data-stu-id="14c08-113">Requirements</span></span>  
 <span data-ttu-id="14c08-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14c08-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14c08-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14c08-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14c08-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14c08-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="14c08-117">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="14c08-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="14c08-118">См. также</span><span class="sxs-lookup"><span data-stu-id="14c08-118">See also</span></span>

- [<span data-ttu-id="14c08-119">Интерфейс ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="14c08-119">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="14c08-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="14c08-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
