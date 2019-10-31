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
ms.openlocfilehash: 0d34577f0f785bc851646423b8cd732ab4d1dae0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73113854"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="738e1-102">Метод ICLRDataTarget::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="738e1-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="738e1-103">Возвращает текущий контекст выполнения для данного потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="738e1-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="738e1-104">Этот метод вызывается службами доступа к данным среды CLR.</span><span class="sxs-lookup"><span data-stu-id="738e1-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="738e1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="738e1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]   
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="738e1-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="738e1-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="738e1-107">окне Идентификатор операционной системы потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="738e1-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="738e1-108">окне Флаги, указывающие, какие части контекста должны быть возвращены.</span><span class="sxs-lookup"><span data-stu-id="738e1-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="738e1-109">Реализация возвратит по крайней мере эти части контекста.</span><span class="sxs-lookup"><span data-stu-id="738e1-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="738e1-110">окне Размер контекста.</span><span class="sxs-lookup"><span data-stu-id="738e1-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="738e1-111">заполняет Указатель на буфер, в который будет помещен контекст.</span><span class="sxs-lookup"><span data-stu-id="738e1-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="738e1-112">Данные в буфере `context` должны быть в формате структуры `CONTEXT` Win32.</span><span class="sxs-lookup"><span data-stu-id="738e1-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="738e1-113">Контекст задает зависящие от процессора данные регистра, поэтому определение структуры `CONTEXT` Win32 зависит от архитектуры процессора.</span><span class="sxs-lookup"><span data-stu-id="738e1-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="738e1-114">Описание структуры `CONTEXT` Win32 см. в файле заголовка WinNT. h.</span><span class="sxs-lookup"><span data-stu-id="738e1-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="738e1-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="738e1-115">Remarks</span></span>  
 <span data-ttu-id="738e1-116">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="738e1-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="738e1-117">Требования</span><span class="sxs-lookup"><span data-stu-id="738e1-117">Requirements</span></span>  
 <span data-ttu-id="738e1-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="738e1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="738e1-119">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="738e1-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="738e1-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="738e1-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="738e1-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="738e1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="738e1-122">См. также</span><span class="sxs-lookup"><span data-stu-id="738e1-122">See also</span></span>

- [<span data-ttu-id="738e1-123">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="738e1-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
