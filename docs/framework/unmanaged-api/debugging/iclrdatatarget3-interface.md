---
title: Интерфейс ICLRDataTarget3
ms.date: 03/30/2017
api_name:
- ICLRDataTarget3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d2711bdf-64b3-404c-a0c3-01ba4907f703
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54d6535e2b2c4761eb3c67a990c62f2c311cf133
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406868"
---
# <a name="iclrdatatarget3-interface"></a><span data-ttu-id="8e7dd-102">Интерфейс ICLRDataTarget3</span><span class="sxs-lookup"><span data-stu-id="8e7dd-102">ICLRDataTarget3 Interface</span></span>
<span data-ttu-id="8e7dd-103">Подкласс [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) , предоставляющий доступ к информации об исключении.</span><span class="sxs-lookup"><span data-stu-id="8e7dd-103">A subclass of [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8e7dd-104">Методы</span><span class="sxs-lookup"><span data-stu-id="8e7dd-104">Methods</span></span>  
  
|<span data-ttu-id="8e7dd-105">Метод</span><span class="sxs-lookup"><span data-stu-id="8e7dd-105">Method</span></span>|<span data-ttu-id="8e7dd-106">Описание</span><span class="sxs-lookup"><span data-stu-id="8e7dd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8e7dd-107">Метод GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="8e7dd-107">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)|<span data-ttu-id="8e7dd-108">Вызывается службами доступа к данным среды CLR для извлечения записи исключения, связанной с целевым процессом.</span><span class="sxs-lookup"><span data-stu-id="8e7dd-108">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span>|  
|[<span data-ttu-id="8e7dd-109">Метод GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="8e7dd-109">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)|<span data-ttu-id="8e7dd-110">Вызывается службами доступа к данным среды CLR для извлечения записи контекста, связанной с целевым процессом.</span><span class="sxs-lookup"><span data-stu-id="8e7dd-110">Called by the CLR data access services to retrieve the context record associated with the target process.</span></span>|  
|[<span data-ttu-id="8e7dd-111">Метод GetExceptionThreadID</span><span class="sxs-lookup"><span data-stu-id="8e7dd-111">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)|<span data-ttu-id="8e7dd-112">Вызывается службами доступа к данным среды CLR для получения идентификатора потока, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="8e7dd-112">Called by the CLR data access services to get the ID of the thread that threw the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e7dd-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="8e7dd-113">Remarks</span></span>  
 <span data-ttu-id="8e7dd-114">Клиент API (то есть отладчик) должен реализовывать этот интерфейс для определенного целевого процесса по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="8e7dd-114">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="8e7dd-115">Например, реализация активного процесса будет отличаться от реализации дампа памяти.</span><span class="sxs-lookup"><span data-stu-id="8e7dd-115">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="8e7dd-116">Целевой объект может не поддерживать изменение областей его памяти.</span><span class="sxs-lookup"><span data-stu-id="8e7dd-116">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e7dd-117">Требования</span><span class="sxs-lookup"><span data-stu-id="8e7dd-117">Requirements</span></span>  
 <span data-ttu-id="8e7dd-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e7dd-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e7dd-119">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="8e7dd-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="8e7dd-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e7dd-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e7dd-121">**Версии платформы .NET framework:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e7dd-121">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e7dd-122">См. также</span><span class="sxs-lookup"><span data-stu-id="8e7dd-122">See Also</span></span>  
 [<span data-ttu-id="8e7dd-123">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="8e7dd-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 [<span data-ttu-id="8e7dd-124">Интерфейс ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="8e7dd-124">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="8e7dd-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8e7dd-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
