---
title: "Метод ICLRDataTarget3::GetExceptionThreadID"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICLRDataTarget3.GetExceptionThreadID
api_location: mscordbi.dll
api_type: COM
ms.assetid: 307d6ac7-4a86-45f3-999d-6b47004a68f2
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f05d264d4bf55de930a07eda6bf369570c8b7fa8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a><span data-ttu-id="bd47f-102">Метод ICLRDataTarget3::GetExceptionThreadID</span><span class="sxs-lookup"><span data-stu-id="bd47f-102">ICLRDataTarget3::GetExceptionThreadID Method</span></span>
<span data-ttu-id="bd47f-103">Вызывается службами доступа к данным среды CLR для получения идентификатора потока, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="bd47f-103">Called by the common language runtime (CLR) data access services to get the ID of the thread that threw the exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd47f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd47f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd47f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bd47f-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="bd47f-106">[из] Идентификатор потока, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="bd47f-106">[out] The ID of the thread that threw the exception.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd47f-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bd47f-107">Return Value</span></span>  
 <span data-ttu-id="bd47f-108">Возвращается значение `S_OK` при успешном выполнении или код ошибки `HRESULT` при сбое.</span><span class="sxs-lookup"><span data-stu-id="bd47f-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="bd47f-109">Коды `HRESULT` могут включать значения, приведенные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="bd47f-109">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="bd47f-110">Код возврата</span><span class="sxs-lookup"><span data-stu-id="bd47f-110">Return code</span></span>|<span data-ttu-id="bd47f-111">Описание</span><span class="sxs-lookup"><span data-stu-id="bd47f-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="bd47f-112">Метод успешно выполнен.</span><span class="sxs-lookup"><span data-stu-id="bd47f-112">Method succeeded.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="bd47f-113">Не удалось найти допустимый идентификатор потока для исключения.</span><span class="sxs-lookup"><span data-stu-id="bd47f-113">Could not find a valid thread ID for the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd47f-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="bd47f-114">Remarks</span></span>  
 <span data-ttu-id="bd47f-115">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="bd47f-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd47f-116">Требования</span><span class="sxs-lookup"><span data-stu-id="bd47f-116">Requirements</span></span>  
 <span data-ttu-id="bd47f-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd47f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd47f-118">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="bd47f-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="bd47f-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd47f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd47f-120">**Версии платформы .NET framework:**[!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd47f-120">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd47f-121">См. также</span><span class="sxs-lookup"><span data-stu-id="bd47f-121">See Also</span></span>  
 [<span data-ttu-id="bd47f-122">Интерфейс ICLRDataTarget3</span><span class="sxs-lookup"><span data-stu-id="bd47f-122">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [<span data-ttu-id="bd47f-123">Метод GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="bd47f-123">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)  
 [<span data-ttu-id="bd47f-124">Метод GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="bd47f-124">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
