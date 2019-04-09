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
ms.openlocfilehash: d3f98ab65512a380ebd4dc0ecd50e36f94a6d6b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104160"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="6c216-102">Метод ICLRDataTarget::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="6c216-102">ICLRDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="6c216-103">Задает текущий контекст заданного потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="6c216-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="6c216-104">Этот метод вызывается службами доступа к данным среды CLR.</span><span class="sxs-lookup"><span data-stu-id="6c216-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c216-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c216-105">Syntax</span></span>  
  
```  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]   
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c216-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6c216-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="6c216-107">[in] Идентификатор потока в целевом процессе операционной системы.</span><span class="sxs-lookup"><span data-stu-id="6c216-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="6c216-108">[in] Размер контекста.</span><span class="sxs-lookup"><span data-stu-id="6c216-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="6c216-109">[in] Указатель на буфер, содержащий контекст.</span><span class="sxs-lookup"><span data-stu-id="6c216-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="6c216-110">Данные в `context` буфера будет иметь формат для Win32 `CONTEXT` структуры.</span><span class="sxs-lookup"><span data-stu-id="6c216-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="6c216-111">Контекст задает данные конкретного процессора регистра, поэтому определение Win32 `CONTEXT` структура зависит от архитектуры процессора.</span><span class="sxs-lookup"><span data-stu-id="6c216-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="6c216-112">Ссылки на файл заголовка WinNT.h, для определения Win32 `CONTEXT` структуры.</span><span class="sxs-lookup"><span data-stu-id="6c216-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c216-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="6c216-113">Remarks</span></span>  
 <span data-ttu-id="6c216-114">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="6c216-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c216-115">Требования</span><span class="sxs-lookup"><span data-stu-id="6c216-115">Requirements</span></span>  
 <span data-ttu-id="6c216-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c216-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c216-117">**Заголовок.** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="6c216-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="6c216-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c216-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6c216-119">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6c216-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6c216-120">См. также</span><span class="sxs-lookup"><span data-stu-id="6c216-120">See also</span></span>

- [<span data-ttu-id="6c216-121">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="6c216-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
