---
title: Метод ICorDebugMutableDataTarget::SetThreadContext
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05f0c0d23b4885f2d6fd351fdf845a25c899228e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418422"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="606e2-102">Метод ICorDebugMutableDataTarget::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="606e2-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="606e2-103">Задает контекст (значения регистра) для потока.</span><span class="sxs-lookup"><span data-stu-id="606e2-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="606e2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="606e2-104">Syntax</span></span>  
  
```  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="606e2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="606e2-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="606e2-106">[in] Идентификатор потока, определяемый операционной системой.</span><span class="sxs-lookup"><span data-stu-id="606e2-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="606e2-107">[in] Размер буфера `pContext` для записи.</span><span class="sxs-lookup"><span data-stu-id="606e2-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="606e2-108">[in] Указатель на байты, которые требуется записать.</span><span class="sxs-lookup"><span data-stu-id="606e2-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="606e2-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="606e2-109">Remarks</span></span>  
 <span data-ttu-id="606e2-110">Метод `SetThreadContext` обновляет текущий контекст для потока, указанного аргументом `dwThreadID`, который задается операционной системой.</span><span class="sxs-lookup"><span data-stu-id="606e2-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="606e2-111">Формат записи контекста, определяется платформой, указанной методом [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="606e2-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="606e2-112">В Windows это [КОНТЕКСТА](http://msdn.microsoft.com/library/windows/desktop/ms679284.aspx) структуры.</span><span class="sxs-lookup"><span data-stu-id="606e2-112">On Windows, this is a [CONTEXT](http://msdn.microsoft.com/library/windows/desktop/ms679284.aspx) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="606e2-113">Требования</span><span class="sxs-lookup"><span data-stu-id="606e2-113">Requirements</span></span>  
 <span data-ttu-id="606e2-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="606e2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="606e2-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="606e2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="606e2-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="606e2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="606e2-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="606e2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="606e2-118">См. также</span><span class="sxs-lookup"><span data-stu-id="606e2-118">See Also</span></span>  
 [<span data-ttu-id="606e2-119">Интерфейс ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="606e2-119">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [<span data-ttu-id="606e2-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="606e2-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
