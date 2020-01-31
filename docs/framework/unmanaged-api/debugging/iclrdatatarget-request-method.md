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
ms.openlocfilehash: 0a7e764d89dd42bcaf81da5cf6a16991b6b8a16e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793704"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="d6db8-102">Метод ICLRDataTarget::Request</span><span class="sxs-lookup"><span data-stu-id="d6db8-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="d6db8-103">Вызывается службами доступа к данным среды CLR для запроса операции, как определено в реализации.</span><span class="sxs-lookup"><span data-stu-id="d6db8-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6db8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d6db8-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d6db8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d6db8-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="d6db8-106">окне Определяется пользователем.</span><span class="sxs-lookup"><span data-stu-id="d6db8-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="d6db8-107">окне Размер входного буфера, используемого для входящего запроса.</span><span class="sxs-lookup"><span data-stu-id="d6db8-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="d6db8-108">окне Буфер, содержащий запрос.</span><span class="sxs-lookup"><span data-stu-id="d6db8-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="d6db8-109">окне Размер выходного буфера, используемого для ответа.</span><span class="sxs-lookup"><span data-stu-id="d6db8-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="d6db8-110">заполняет Буфер, содержащий ответ.</span><span class="sxs-lookup"><span data-stu-id="d6db8-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6db8-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="d6db8-111">Remarks</span></span>  
 <span data-ttu-id="d6db8-112">Метод `Request` упрощает добавление неуказанных пользовательских операций.</span><span class="sxs-lookup"><span data-stu-id="d6db8-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="d6db8-113">Это значит, что этот метод обеспечивает расширяемость без необходимости пересмотра определения интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d6db8-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="d6db8-114">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="d6db8-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6db8-115">Требования</span><span class="sxs-lookup"><span data-stu-id="d6db8-115">Requirements</span></span>  
 <span data-ttu-id="d6db8-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6db8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6db8-117">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="d6db8-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d6db8-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6db8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6db8-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6db8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6db8-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="d6db8-120">See also</span></span>

- [<span data-ttu-id="d6db8-121">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="d6db8-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
