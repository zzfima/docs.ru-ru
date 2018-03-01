---
title: "Метод ICLRDataTarget3::GetExceptionThreadID"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionThreadID
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 307d6ac7-4a86-45f3-999d-6b47004a68f2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0f8b2e7c764eb5d7694633be7fb095b3d19be6e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a><span data-ttu-id="72914-102">Метод ICLRDataTarget3::GetExceptionThreadID</span><span class="sxs-lookup"><span data-stu-id="72914-102">ICLRDataTarget3::GetExceptionThreadID Method</span></span>
<span data-ttu-id="72914-103">Вызывается службами доступа к данным среды CLR для получения идентификатора потока, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="72914-103">Called by the common language runtime (CLR) data access services to get the ID of the thread that threw the exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72914-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72914-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72914-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="72914-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="72914-106">[из] Идентификатор потока, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="72914-106">[out] The ID of the thread that threw the exception.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72914-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="72914-107">Return Value</span></span>  
 <span data-ttu-id="72914-108">Возвращается значение `S_OK` при успешном выполнении или код ошибки `HRESULT` при сбое.</span><span class="sxs-lookup"><span data-stu-id="72914-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="72914-109">Коды `HRESULT` могут включать значения, приведенные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="72914-109">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="72914-110">Код возврата</span><span class="sxs-lookup"><span data-stu-id="72914-110">Return code</span></span>|<span data-ttu-id="72914-111">Описание</span><span class="sxs-lookup"><span data-stu-id="72914-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="72914-112">Метод успешно выполнен.</span><span class="sxs-lookup"><span data-stu-id="72914-112">Method succeeded.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="72914-113">Не удалось найти допустимый идентификатор потока для исключения.</span><span class="sxs-lookup"><span data-stu-id="72914-113">Could not find a valid thread ID for the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72914-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="72914-114">Remarks</span></span>  
 <span data-ttu-id="72914-115">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="72914-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72914-116">Требования</span><span class="sxs-lookup"><span data-stu-id="72914-116">Requirements</span></span>  
 <span data-ttu-id="72914-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72914-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72914-118">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="72914-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="72914-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72914-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72914-120">**Версии платформы .NET framework:**[!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72914-120">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72914-121">См. также</span><span class="sxs-lookup"><span data-stu-id="72914-121">See Also</span></span>  
 [<span data-ttu-id="72914-122">Интерфейс ICLRDataTarget3</span><span class="sxs-lookup"><span data-stu-id="72914-122">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [<span data-ttu-id="72914-123">Метод GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="72914-123">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)  
 [<span data-ttu-id="72914-124">Метод GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="72914-124">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
