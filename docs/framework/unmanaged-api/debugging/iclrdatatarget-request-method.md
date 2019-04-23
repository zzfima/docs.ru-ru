---
title: Метод ICLRDataTarget::Request
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e9005dd8fde0d7258bd1dd48b561e4925e87733b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102699"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="0a7b6-102">Метод ICLRDataTarget::Request</span><span class="sxs-lookup"><span data-stu-id="0a7b6-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="0a7b6-103">Вызывается службами доступа к данным среды выполнения (CLR) для запроса операции, как определено в реализации.</span><span class="sxs-lookup"><span data-stu-id="0a7b6-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a7b6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a7b6-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="0a7b6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0a7b6-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="0a7b6-106">[in] Определяемые пользователем.</span><span class="sxs-lookup"><span data-stu-id="0a7b6-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="0a7b6-107">[in] Размер входного буфера, который используется для входящего запроса.</span><span class="sxs-lookup"><span data-stu-id="0a7b6-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="0a7b6-108">[in] Буфер, содержащий запрос.</span><span class="sxs-lookup"><span data-stu-id="0a7b6-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="0a7b6-109">[in] Размер выходного буфера, который используется для ответа.</span><span class="sxs-lookup"><span data-stu-id="0a7b6-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="0a7b6-110">[out] Буфер, содержащий ответ.</span><span class="sxs-lookup"><span data-stu-id="0a7b6-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a7b6-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="0a7b6-111">Remarks</span></span>  
 <span data-ttu-id="0a7b6-112">`Request` Метод облегчает процесс добавления неуказанных пользовательских операций.</span><span class="sxs-lookup"><span data-stu-id="0a7b6-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="0a7b6-113">То есть этот метод обеспечивает расширяемость без необходимости версии определения интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0a7b6-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="0a7b6-114">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="0a7b6-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a7b6-115">Требования</span><span class="sxs-lookup"><span data-stu-id="0a7b6-115">Requirements</span></span>  
 <span data-ttu-id="0a7b6-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a7b6-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a7b6-117">**Заголовок.** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="0a7b6-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="0a7b6-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a7b6-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a7b6-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a7b6-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a7b6-120">См. также</span><span class="sxs-lookup"><span data-stu-id="0a7b6-120">See also</span></span>

- [<span data-ttu-id="0a7b6-121">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="0a7b6-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
