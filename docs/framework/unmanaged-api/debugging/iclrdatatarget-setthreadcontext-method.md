---
title: "Метод ICLRDataTarget::SetThreadContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.SetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::SetThreadContext
helpviewer_keywords:
- SetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::SetThreadContext method [.NET Framework debugging]
ms.assetid: 103c8502-81fe-40d7-9c1e-9008d8fb19e1
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e51cbafda76933d58bd60be8db7dd163a2dd59d3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="12e69-102">Метод ICLRDataTarget::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="12e69-102">ICLRDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="12e69-103">Задает текущий контекст заданного потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="12e69-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="12e69-104">Этот метод вызывается службами доступа к данным среды CLR.</span><span class="sxs-lookup"><span data-stu-id="12e69-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12e69-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12e69-105">Syntax</span></span>  
  
```  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]   
         BYTE               *context  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="12e69-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="12e69-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="12e69-107">[in] Идентификатор потока в целевом процессе операционной системы.</span><span class="sxs-lookup"><span data-stu-id="12e69-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="12e69-108">[in] Размер контекста.</span><span class="sxs-lookup"><span data-stu-id="12e69-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="12e69-109">[in] Указатель на буфер, содержащий контекст.</span><span class="sxs-lookup"><span data-stu-id="12e69-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="12e69-110">Данные в `context` буфера будет в формате Win32 `CONTEXT` структуры.</span><span class="sxs-lookup"><span data-stu-id="12e69-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="12e69-111">Контекст задает данные от процессора регистра, поэтому определение Win32 `CONTEXT` структура зависит от архитектуры процессора.</span><span class="sxs-lookup"><span data-stu-id="12e69-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="12e69-112">Ссылаться на файл заголовка WinNT.h, для определения Win32 `CONTEXT` структуры.</span><span class="sxs-lookup"><span data-stu-id="12e69-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12e69-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="12e69-113">Remarks</span></span>  
 <span data-ttu-id="12e69-114">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="12e69-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12e69-115">Требования</span><span class="sxs-lookup"><span data-stu-id="12e69-115">Requirements</span></span>  
 <span data-ttu-id="12e69-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12e69-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12e69-117">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="12e69-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="12e69-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12e69-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12e69-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12e69-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12e69-120">См. также</span><span class="sxs-lookup"><span data-stu-id="12e69-120">See Also</span></span>  
 [<span data-ttu-id="12e69-121">ICLRDataTarget-интерфейс</span><span class="sxs-lookup"><span data-stu-id="12e69-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
