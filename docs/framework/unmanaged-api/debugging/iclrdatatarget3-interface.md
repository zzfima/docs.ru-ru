---
title: "Интерфейс ICLRDataTarget3"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget3
api_location: mscordbi.dll
api_type: COM
ms.assetid: d2711bdf-64b3-404c-a0c3-01ba4907f703
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 16e2d2aa1a2626f4124e1b43ff85abcdd17f6990
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget3-interface"></a><span data-ttu-id="4a0b7-102">Интерфейс ICLRDataTarget3</span><span class="sxs-lookup"><span data-stu-id="4a0b7-102">ICLRDataTarget3 Interface</span></span>
<span data-ttu-id="4a0b7-103">Подкласс [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) , предоставляющий доступ к информации об исключении.</span><span class="sxs-lookup"><span data-stu-id="4a0b7-103">A subclass of [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4a0b7-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4a0b7-104">Methods</span></span>  
  
|<span data-ttu-id="4a0b7-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4a0b7-105">Method</span></span>|<span data-ttu-id="4a0b7-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4a0b7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4a0b7-107">Метод GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="4a0b7-107">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)|<span data-ttu-id="4a0b7-108">Вызывается службами доступа к данным среды CLR для извлечения записи исключения, связанной с целевым процессом.</span><span class="sxs-lookup"><span data-stu-id="4a0b7-108">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span>|  
|[<span data-ttu-id="4a0b7-109">Метод GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="4a0b7-109">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)|<span data-ttu-id="4a0b7-110">Вызывается службами доступа к данным среды CLR для извлечения записи контекста, связанной с целевым процессом.</span><span class="sxs-lookup"><span data-stu-id="4a0b7-110">Called by the CLR data access services to retrieve the context record associated with the target process.</span></span>|  
|[<span data-ttu-id="4a0b7-111">Метод GetExceptionThreadID</span><span class="sxs-lookup"><span data-stu-id="4a0b7-111">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)|<span data-ttu-id="4a0b7-112">Вызывается службами доступа к данным среды CLR для получения идентификатора потока, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="4a0b7-112">Called by the CLR data access services to get the ID of the thread that threw the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a0b7-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="4a0b7-113">Remarks</span></span>  
 <span data-ttu-id="4a0b7-114">Клиент API (то есть отладчик) должен реализовывать этот интерфейс для определенного целевого процесса по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="4a0b7-114">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="4a0b7-115">Например, реализация активного процесса будет отличаться от реализации дампа памяти.</span><span class="sxs-lookup"><span data-stu-id="4a0b7-115">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="4a0b7-116">Целевой объект может не поддерживать изменение областей его памяти.</span><span class="sxs-lookup"><span data-stu-id="4a0b7-116">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a0b7-117">Требования</span><span class="sxs-lookup"><span data-stu-id="4a0b7-117">Requirements</span></span>  
 <span data-ttu-id="4a0b7-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a0b7-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a0b7-119">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="4a0b7-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="4a0b7-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a0b7-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a0b7-121">**Версии платформы .NET framework:**[!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a0b7-121">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a0b7-122">См. также</span><span class="sxs-lookup"><span data-stu-id="4a0b7-122">See Also</span></span>  
 [<span data-ttu-id="4a0b7-123">ICLRDataTarget-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4a0b7-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 [<span data-ttu-id="4a0b7-124">Интерфейс ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="4a0b7-124">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="4a0b7-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4a0b7-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
