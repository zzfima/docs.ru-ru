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
ms.openlocfilehash: dc79277c75118b11766e66137284bd5655eed091
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405376"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="f3005-102">Метод ICLRDataTarget::Request</span><span class="sxs-lookup"><span data-stu-id="f3005-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="f3005-103">Вызывается службами доступа к данным среды выполнения (CLR) для запроса операции, как определяются реализацией.</span><span class="sxs-lookup"><span data-stu-id="f3005-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3005-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3005-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="f3005-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f3005-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="f3005-106">[in] Определяемые пользователем.</span><span class="sxs-lookup"><span data-stu-id="f3005-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="f3005-107">[in] Размер входного буфера, который используется для входящего запроса.</span><span class="sxs-lookup"><span data-stu-id="f3005-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="f3005-108">[in] Буфер, содержащий запрос.</span><span class="sxs-lookup"><span data-stu-id="f3005-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="f3005-109">[in] Размер выходного буфера, используемого для ответа.</span><span class="sxs-lookup"><span data-stu-id="f3005-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="f3005-110">[out] Буфер, содержащий ответ.</span><span class="sxs-lookup"><span data-stu-id="f3005-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3005-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="f3005-111">Remarks</span></span>  
 <span data-ttu-id="f3005-112">`Request` Метод облегчает процесс добавления незаданных настраиваемых операций.</span><span class="sxs-lookup"><span data-stu-id="f3005-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="f3005-113">То есть этот метод обеспечивает расширяемость, не требуя пересмотра определения интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f3005-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="f3005-114">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="f3005-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3005-115">Требования</span><span class="sxs-lookup"><span data-stu-id="f3005-115">Requirements</span></span>  
 <span data-ttu-id="f3005-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3005-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3005-117">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="f3005-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f3005-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3005-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3005-119">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3005-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3005-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f3005-120">See Also</span></span>  
 [<span data-ttu-id="f3005-121">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="f3005-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
