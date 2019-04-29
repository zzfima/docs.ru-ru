---
title: Перечисление ETaskType
ms.date: 03/30/2017
api_name:
- ETaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ETaskType
helpviewer_keywords:
- ETaskType enumeration [.NET Framework hosting]
ms.assetid: aa527b31-89d4-41f2-ad6f-63b76950b7df
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f256195a4cd5b18f568e05156db867aa5dba9161
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61627967"
---
# <a name="etasktype-enumeration"></a><span data-ttu-id="a6e68-102">Перечисление ETaskType</span><span class="sxs-lookup"><span data-stu-id="a6e68-102">ETaskType Enumeration</span></span>
<span data-ttu-id="a6e68-103">Содержит значения, указывающие тип задачи, представленного либо [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) или [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="a6e68-103">Contains values that indicate the type of task that is represented by either an [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) or an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6e68-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6e68-104">Syntax</span></span>  
  
```  
typedef enum ETaskType {  
    TT_DEBUGGERHELPER           = 0x1,  
    TT_GC                       = 0x2,  
    TT_FINALIZER                = 0x4,  
    TT_THREADPOOL_TIMER         = 0x8,  
    TT_THREADPOOL_GATE          = 0x10,  
    TT_THREADPOOL_WORKER        = 0x20,  
    TT_THREADPOOL_IOCOMPLETION  = 0x40,  
    TT_ADUNLOAD                 = 0x80,  
    TT_USER                     = 0x100,  
    TT_THREADPOOL_WAIT          = 0x200,  
    TT_UNKNOWN                  = 0x80000000  
} ETaskType;  
```  
  
## <a name="members"></a><span data-ttu-id="a6e68-105">Участники</span><span class="sxs-lookup"><span data-stu-id="a6e68-105">Members</span></span>  
  
|<span data-ttu-id="a6e68-106">Член</span><span class="sxs-lookup"><span data-stu-id="a6e68-106">Member</span></span>|<span data-ttu-id="a6e68-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a6e68-107">Description</span></span>|  
|------------|-----------------|  
|`TT_ADUNLOAD`|<span data-ttu-id="a6e68-108">Интерфейс представляет задачу выгрузки домена приложения.</span><span class="sxs-lookup"><span data-stu-id="a6e68-108">The interface represents an application domain unloading task.</span></span>|  
|`TT_DEBUGGERHELPER`|<span data-ttu-id="a6e68-109">Интерфейс представляет вспомогательную задачу отладчика.</span><span class="sxs-lookup"><span data-stu-id="a6e68-109">The interface represents a debugger helper task.</span></span>|  
|`TT_FINALIZER`|<span data-ttu-id="a6e68-110">Интерфейс представляет задачу метода завершения.</span><span class="sxs-lookup"><span data-stu-id="a6e68-110">The interface represents a finalizer task.</span></span>|  
|`TT_GC`|<span data-ttu-id="a6e68-111">Интерфейс представляет задачу сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="a6e68-111">The interface represents a garbage collection task.</span></span>|  
|`TT_THREADPOOL_GATE`|<span data-ttu-id="a6e68-112">Интерфейс представляет задачу потока логического.</span><span class="sxs-lookup"><span data-stu-id="a6e68-112">The interface represents a gate thread task.</span></span>|  
|`TT_THREADPOOL_IOCOMPLETION`|<span data-ttu-id="a6e68-113">Интерфейс представляет задачу потока ввода-вывода или задачу потока порта завершения.</span><span class="sxs-lookup"><span data-stu-id="a6e68-113">The interface represents an I/O thread task or a completion port thread task.</span></span>|  
|`TT_THREADPOOL_TIMER`|<span data-ttu-id="a6e68-114">Интерфейс представляет задачу потока таймера.</span><span class="sxs-lookup"><span data-stu-id="a6e68-114">The interface represents a timer thread task.</span></span>|  
|`TT_THREADPOOL_WAIT`|<span data-ttu-id="a6e68-115">Интерфейс представляет задачу потока ожидания.</span><span class="sxs-lookup"><span data-stu-id="a6e68-115">The interface represents a wait thread task.</span></span>|  
|`TT_THREADPOOL_WORKER`|<span data-ttu-id="a6e68-116">Интерфейс представляет задачу рабочего потока.</span><span class="sxs-lookup"><span data-stu-id="a6e68-116">The interface represents a worker thread task.</span></span>|  
|`TT_UNKNOWN`|<span data-ttu-id="a6e68-117">Задача неизвестна.</span><span class="sxs-lookup"><span data-stu-id="a6e68-117">The task is unknown.</span></span>|  
|`TT_USER`|<span data-ttu-id="a6e68-118">Интерфейс представляет задачу пользователя.</span><span class="sxs-lookup"><span data-stu-id="a6e68-118">The interface represents a user task.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a6e68-119">Требования</span><span class="sxs-lookup"><span data-stu-id="a6e68-119">Requirements</span></span>  
 <span data-ttu-id="a6e68-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6e68-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6e68-121">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a6e68-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a6e68-122">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a6e68-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a6e68-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6e68-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6e68-124">См. также</span><span class="sxs-lookup"><span data-stu-id="a6e68-124">See also</span></span>

- [<span data-ttu-id="a6e68-125">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="a6e68-125">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
