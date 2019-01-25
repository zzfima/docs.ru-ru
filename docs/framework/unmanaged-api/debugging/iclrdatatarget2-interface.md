---
title: Интерфейс ICLRDataTarget2
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2
helpviewer_keywords:
- ICLRDataTarget2 interface [.NET Framework debugging]
ms.assetid: 94249397-861b-4294-a538-cf01466a66d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45f16fd50880b5d2482be365f3c55e1427cc6eaa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701005"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="ddd89-102">Интерфейс ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="ddd89-102">ICLRDataTarget2 Interface</span></span>
<span data-ttu-id="ddd89-103">Подкласс [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) , используемый уровнем служб доступа к данным для управления областями виртуальной памяти в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="ddd89-103">A subclass of [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ddd89-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ddd89-104">Methods</span></span>  
  
|<span data-ttu-id="ddd89-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ddd89-105">Method</span></span>|<span data-ttu-id="ddd89-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ddd89-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ddd89-107">Метод AllocVirtual</span><span class="sxs-lookup"><span data-stu-id="ddd89-107">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="ddd89-108">Выделяет память в адресном пространстве целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="ddd89-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="ddd89-109">Метод FreeVirtual</span><span class="sxs-lookup"><span data-stu-id="ddd89-109">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="ddd89-110">Освобождает память, выделенную ранее в адресном пространстве целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="ddd89-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddd89-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="ddd89-111">Remarks</span></span>  
 <span data-ttu-id="ddd89-112">Клиент API (то есть отладчик) должен реализовывать этот интерфейс для определенного целевого процесса по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="ddd89-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="ddd89-113">Например, реализация активного процесса будет отличаться от реализации дампа памяти.</span><span class="sxs-lookup"><span data-stu-id="ddd89-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="ddd89-114">Целевой объект может не поддерживать изменение областей его памяти.</span><span class="sxs-lookup"><span data-stu-id="ddd89-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddd89-115">Требования</span><span class="sxs-lookup"><span data-stu-id="ddd89-115">Requirements</span></span>  
 <span data-ttu-id="ddd89-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddd89-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddd89-117">**Заголовок.** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="ddd89-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="ddd89-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ddd89-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ddd89-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddd89-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddd89-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ddd89-120">See also</span></span>
- [<span data-ttu-id="ddd89-121">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="ddd89-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
- [<span data-ttu-id="ddd89-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ddd89-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
