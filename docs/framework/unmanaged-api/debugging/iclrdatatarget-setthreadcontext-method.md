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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: edd70dd4cfc2e26b30ee0deec79b7d126d1f76a1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738585"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="b1156-102">Метод ICLRDataTarget::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="b1156-102">ICLRDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="b1156-103">Задает текущий контекст заданного потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="b1156-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="b1156-104">Этот метод вызывается службами доступа к данным среды CLR.</span><span class="sxs-lookup"><span data-stu-id="b1156-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1156-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1156-105">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]   
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1156-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b1156-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="b1156-107">[in] Идентификатор потока в целевом процессе операционной системы.</span><span class="sxs-lookup"><span data-stu-id="b1156-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="b1156-108">[in] Размер контекста.</span><span class="sxs-lookup"><span data-stu-id="b1156-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="b1156-109">[in] Указатель на буфер, содержащий контекст.</span><span class="sxs-lookup"><span data-stu-id="b1156-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="b1156-110">Данные в `context` буфера будет иметь формат для Win32 `CONTEXT` структуры.</span><span class="sxs-lookup"><span data-stu-id="b1156-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="b1156-111">Контекст задает данные конкретного процессора регистра, поэтому определение Win32 `CONTEXT` структура зависит от архитектуры процессора.</span><span class="sxs-lookup"><span data-stu-id="b1156-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="b1156-112">Ссылки на файл заголовка WinNT.h, для определения Win32 `CONTEXT` структуры.</span><span class="sxs-lookup"><span data-stu-id="b1156-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1156-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="b1156-113">Remarks</span></span>  
 <span data-ttu-id="b1156-114">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="b1156-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1156-115">Требования</span><span class="sxs-lookup"><span data-stu-id="b1156-115">Requirements</span></span>  
 <span data-ttu-id="b1156-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1156-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1156-117">**Заголовок.** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="b1156-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b1156-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1156-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1156-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1156-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1156-120">См. также</span><span class="sxs-lookup"><span data-stu-id="b1156-120">See also</span></span>

- [<span data-ttu-id="b1156-121">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="b1156-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
