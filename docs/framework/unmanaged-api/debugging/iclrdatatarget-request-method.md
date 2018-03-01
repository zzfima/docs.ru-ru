---
title: "Метод ICLRDataTarget::Request"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRDataTarget.Request
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7e7bde3a0bc26a6bc93124fa835c4203cd596906
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="72c50-102">Метод ICLRDataTarget::Request</span><span class="sxs-lookup"><span data-stu-id="72c50-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="72c50-103">Вызывается службами доступа к данным среды выполнения (CLR) для запроса операции, как определяются реализацией.</span><span class="sxs-lookup"><span data-stu-id="72c50-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72c50-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72c50-104">Syntax</span></span>  
  
```  
HRESULT Request (  
    [in] ULONG32            reqCode,  
    [in] ULONG32            inBufferSize,  
    [in, size_is(inBufferSize)]   
        BYTE                *inBuffer,  
    [in] ULONG32            outBufferSize,  
    [out, size_is(outBufferSize)]   
        BYTE                *outBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72c50-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="72c50-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="72c50-106">[in] Определяемые пользователем.</span><span class="sxs-lookup"><span data-stu-id="72c50-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="72c50-107">[in] Размер входного буфера, который используется для входящего запроса.</span><span class="sxs-lookup"><span data-stu-id="72c50-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="72c50-108">[in] Буфер, содержащий запрос.</span><span class="sxs-lookup"><span data-stu-id="72c50-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="72c50-109">[in] Размер выходного буфера, используемого для ответа.</span><span class="sxs-lookup"><span data-stu-id="72c50-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="72c50-110">[out] Буфер, содержащий ответ.</span><span class="sxs-lookup"><span data-stu-id="72c50-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72c50-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="72c50-111">Remarks</span></span>  
 <span data-ttu-id="72c50-112">`Request` Метод облегчает процесс добавления незаданных настраиваемых операций.</span><span class="sxs-lookup"><span data-stu-id="72c50-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="72c50-113">То есть этот метод обеспечивает расширяемость, не требуя пересмотра определения интерфейса.</span><span class="sxs-lookup"><span data-stu-id="72c50-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="72c50-114">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="72c50-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72c50-115">Требования</span><span class="sxs-lookup"><span data-stu-id="72c50-115">Requirements</span></span>  
 <span data-ttu-id="72c50-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72c50-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72c50-117">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="72c50-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="72c50-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72c50-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72c50-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72c50-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72c50-120">См. также</span><span class="sxs-lookup"><span data-stu-id="72c50-120">See Also</span></span>  
 [<span data-ttu-id="72c50-121">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="72c50-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
