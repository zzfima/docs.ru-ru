---
title: Метод ICLRDataTarget::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type:
- apiref
ms.openlocfilehash: 3777ad4b12c7d0593c095c470aba81088137a859
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179180"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="0ba84-102">Метод ICLRDataTarget::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="0ba84-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="0ba84-103">Получает текущий контекст выполнения для данного потока в процессе целевого.</span><span class="sxs-lookup"><span data-stu-id="0ba84-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="0ba84-104">Этот метод вызывается службами общего времени выполнения данных.</span><span class="sxs-lookup"><span data-stu-id="0ba84-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ba84-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ba84-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ba84-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0ba84-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="0ba84-107">(в) Идентификатор операционной системы потока в процессе целевого.</span><span class="sxs-lookup"><span data-stu-id="0ba84-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="0ba84-108">(в) Флаги, указывающие, какие части контекста вернуть.</span><span class="sxs-lookup"><span data-stu-id="0ba84-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="0ba84-109">Реализация вернет по крайней мере эти части контекста.</span><span class="sxs-lookup"><span data-stu-id="0ba84-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="0ba84-110">(в) Размер контекста.</span><span class="sxs-lookup"><span data-stu-id="0ba84-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="0ba84-111">(ваут) Указатель на буфер, в котором можно разместить контекст.</span><span class="sxs-lookup"><span data-stu-id="0ba84-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="0ba84-112">Данные в `context` буфере должны быть в формате структуры Win32. `CONTEXT`</span><span class="sxs-lookup"><span data-stu-id="0ba84-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="0ba84-113">Контекст определяет данные регистра для процессоров, поэтому определение `CONTEXT` структуры Win32 зависит от архитектуры процессора.</span><span class="sxs-lookup"><span data-stu-id="0ba84-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="0ba84-114">Обратитесь к файлу заголовка WinNT.h для `CONTEXT` определения структуры Win32.</span><span class="sxs-lookup"><span data-stu-id="0ba84-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ba84-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="0ba84-115">Remarks</span></span>  
 <span data-ttu-id="0ba84-116">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="0ba84-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ba84-117">Требования</span><span class="sxs-lookup"><span data-stu-id="0ba84-117">Requirements</span></span>  
 <span data-ttu-id="0ba84-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ba84-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ba84-119">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="0ba84-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="0ba84-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ba84-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ba84-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ba84-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ba84-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0ba84-122">See also</span></span>

- [<span data-ttu-id="0ba84-123">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="0ba84-123">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
