---
title: Метод ICLRDataTarget::SetThreadContext
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetThreadContext
helpviewer_keywords:
- SetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::SetThreadContext method [.NET Framework debugging]
ms.assetid: 103c8502-81fe-40d7-9c1e-9008d8fb19e1
topic_type:
- apiref
ms.openlocfilehash: d76a907434b12b85aaedeef169390ec6f0df724a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179132"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="48b97-102">Метод ICLRDataTarget::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="48b97-102">ICLRDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="48b97-103">Устанавливает текущий контекст заданного потока в процессе целевого.</span><span class="sxs-lookup"><span data-stu-id="48b97-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="48b97-104">Этот метод вызывается службами общего времени выполнения языка (CLR).</span><span class="sxs-lookup"><span data-stu-id="48b97-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48b97-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48b97-105">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48b97-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="48b97-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="48b97-107">(в) Идентификатор операционной системы потока в процессе целевого.</span><span class="sxs-lookup"><span data-stu-id="48b97-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="48b97-108">(в) Размер контекста.</span><span class="sxs-lookup"><span data-stu-id="48b97-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="48b97-109">(в) Указатель на буфер, содержащий контекст.</span><span class="sxs-lookup"><span data-stu-id="48b97-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="48b97-110">Данные в `context` буфере будут находиться в `CONTEXT` формате структуры Win32.</span><span class="sxs-lookup"><span data-stu-id="48b97-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="48b97-111">Контекст определяет данные регистра для процессоров, поэтому определение `CONTEXT` структуры Win32 зависит от архитектуры процессора.</span><span class="sxs-lookup"><span data-stu-id="48b97-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="48b97-112">Обратитесь к файлу заголовка WinNT.h для `CONTEXT` определения структуры Win32.</span><span class="sxs-lookup"><span data-stu-id="48b97-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48b97-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="48b97-113">Remarks</span></span>  
 <span data-ttu-id="48b97-114">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="48b97-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48b97-115">Требования</span><span class="sxs-lookup"><span data-stu-id="48b97-115">Requirements</span></span>  
 <span data-ttu-id="48b97-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48b97-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48b97-117">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="48b97-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="48b97-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48b97-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48b97-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48b97-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48b97-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="48b97-120">See also</span></span>

- [<span data-ttu-id="48b97-121">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="48b97-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
