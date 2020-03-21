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
ms.openlocfilehash: 336ba38bc80fcb2649a12c78691e52c5e4d70bfe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179117"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="f4b43-102">Метод ICLRDataTarget::Request</span><span class="sxs-lookup"><span data-stu-id="f4b43-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="f4b43-103">Вызывается службами общего времени выполнения языка (CLR) для запроса операции, как это определено в реализации.</span><span class="sxs-lookup"><span data-stu-id="f4b43-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4b43-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4b43-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="f4b43-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f4b43-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="f4b43-106">(в) Определяется пользователями.</span><span class="sxs-lookup"><span data-stu-id="f4b43-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="f4b43-107">(в) Размер буфера ввода, который используется для входящего запроса.</span><span class="sxs-lookup"><span data-stu-id="f4b43-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="f4b43-108">(в) Буфер, содержащий запрос.</span><span class="sxs-lookup"><span data-stu-id="f4b43-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="f4b43-109">(в) Размер буфера вывода, который используется для ответа.</span><span class="sxs-lookup"><span data-stu-id="f4b43-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="f4b43-110">(ваут) Буфер, содержащий ответ.</span><span class="sxs-lookup"><span data-stu-id="f4b43-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4b43-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="f4b43-111">Remarks</span></span>  
 <span data-ttu-id="f4b43-112">Метод `Request` облегчает добавление неопределенных пользовательских операций.</span><span class="sxs-lookup"><span data-stu-id="f4b43-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="f4b43-113">То есть этот метод обеспечивает расширяемость, не требуя пересмотра определения интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f4b43-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="f4b43-114">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="f4b43-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4b43-115">Требования</span><span class="sxs-lookup"><span data-stu-id="f4b43-115">Requirements</span></span>  
 <span data-ttu-id="f4b43-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4b43-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4b43-117">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="f4b43-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f4b43-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4b43-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4b43-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4b43-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4b43-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f4b43-120">See also</span></span>

- [<span data-ttu-id="f4b43-121">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="f4b43-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
