---
title: Интерфейс IHostCrst
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 939f100e8ee386642a29c33827a8339caf0467b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967834"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="d59a6-102">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="d59a6-102">IHostCrst Interface</span></span>
<span data-ttu-id="d59a6-103">Служит в качестве представления главного приложения из критических секций для управления потоками.</span><span class="sxs-lookup"><span data-stu-id="d59a6-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d59a6-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d59a6-104">Methods</span></span>  
  
|<span data-ttu-id="d59a6-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d59a6-105">Method</span></span>|<span data-ttu-id="d59a6-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d59a6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d59a6-107">Метод Enter</span><span class="sxs-lookup"><span data-stu-id="d59a6-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="d59a6-108">Войдет в критический раздел.</span><span class="sxs-lookup"><span data-stu-id="d59a6-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="d59a6-109">Метод Leave</span><span class="sxs-lookup"><span data-stu-id="d59a6-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="d59a6-110">Оставляет критический раздел.</span><span class="sxs-lookup"><span data-stu-id="d59a6-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="d59a6-111">Метод SetSpinCount</span><span class="sxs-lookup"><span data-stu-id="d59a6-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="d59a6-112">Задает счетчик прокруток для критической секции.</span><span class="sxs-lookup"><span data-stu-id="d59a6-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="d59a6-113">Метод TryEnter</span><span class="sxs-lookup"><span data-stu-id="d59a6-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="d59a6-114">Пытается ввести критическую секцию и возвращает успех или сбой немедленно.</span><span class="sxs-lookup"><span data-stu-id="d59a6-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d59a6-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="d59a6-115">Remarks</span></span>  
 <span data-ttu-id="d59a6-116">`IHostCrst` позволяет общеязыковой среды выполнения (CLR) для взаимодействия непосредственно с представлением хоста критическую секцию, а не с помощью функций Win32, таких как `EnterCriticalSection` или `LeaveCriticalSection`.</span><span class="sxs-lookup"><span data-stu-id="d59a6-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d59a6-117">Требования</span><span class="sxs-lookup"><span data-stu-id="d59a6-117">Requirements</span></span>  
 <span data-ttu-id="d59a6-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d59a6-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d59a6-119">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d59a6-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d59a6-120">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d59a6-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d59a6-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d59a6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d59a6-122">См. также</span><span class="sxs-lookup"><span data-stu-id="d59a6-122">See also</span></span>

- [<span data-ttu-id="d59a6-123">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="d59a6-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="d59a6-124">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="d59a6-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="d59a6-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="d59a6-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
