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
ms.openlocfilehash: bc956827ad59fc655137e4147e6d98b6d097d470
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138190"
---
# <a name="etasktype-enumeration"></a><span data-ttu-id="f2905-102">Перечисление ETaskType</span><span class="sxs-lookup"><span data-stu-id="f2905-102">ETaskType Enumeration</span></span>
<span data-ttu-id="f2905-103">Содержит значения, указывающие тип задачи, представленной интерфейсом [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) или [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f2905-103">Contains values that indicate the type of task that is represented by either an [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) or an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2905-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2905-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="f2905-105">Члены</span><span class="sxs-lookup"><span data-stu-id="f2905-105">Members</span></span>  
  
|<span data-ttu-id="f2905-106">Член</span><span class="sxs-lookup"><span data-stu-id="f2905-106">Member</span></span>|<span data-ttu-id="f2905-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f2905-107">Description</span></span>|  
|------------|-----------------|  
|`TT_ADUNLOAD`|<span data-ttu-id="f2905-108">Интерфейс представляет задачу выгрузки домена приложения.</span><span class="sxs-lookup"><span data-stu-id="f2905-108">The interface represents an application domain unloading task.</span></span>|  
|`TT_DEBUGGERHELPER`|<span data-ttu-id="f2905-109">Интерфейс представляет вспомогательную задачу отладчика.</span><span class="sxs-lookup"><span data-stu-id="f2905-109">The interface represents a debugger helper task.</span></span>|  
|`TT_FINALIZER`|<span data-ttu-id="f2905-110">Интерфейс представляет задачу финализатора.</span><span class="sxs-lookup"><span data-stu-id="f2905-110">The interface represents a finalizer task.</span></span>|  
|`TT_GC`|<span data-ttu-id="f2905-111">Интерфейс представляет задачу сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f2905-111">The interface represents a garbage collection task.</span></span>|  
|`TT_THREADPOOL_GATE`|<span data-ttu-id="f2905-112">Интерфейс представляет задачу потока шлюза.</span><span class="sxs-lookup"><span data-stu-id="f2905-112">The interface represents a gate thread task.</span></span>|  
|`TT_THREADPOOL_IOCOMPLETION`|<span data-ttu-id="f2905-113">Интерфейс представляет задачу потока ввода-вывода или задачи потока порта завершения.</span><span class="sxs-lookup"><span data-stu-id="f2905-113">The interface represents an I/O thread task or a completion port thread task.</span></span>|  
|`TT_THREADPOOL_TIMER`|<span data-ttu-id="f2905-114">Интерфейс представляет задачу потока таймера.</span><span class="sxs-lookup"><span data-stu-id="f2905-114">The interface represents a timer thread task.</span></span>|  
|`TT_THREADPOOL_WAIT`|<span data-ttu-id="f2905-115">Интерфейс представляет задачу потока ожидания.</span><span class="sxs-lookup"><span data-stu-id="f2905-115">The interface represents a wait thread task.</span></span>|  
|`TT_THREADPOOL_WORKER`|<span data-ttu-id="f2905-116">Интерфейс представляет задачу рабочего потока.</span><span class="sxs-lookup"><span data-stu-id="f2905-116">The interface represents a worker thread task.</span></span>|  
|`TT_UNKNOWN`|<span data-ttu-id="f2905-117">Задача неизвестна.</span><span class="sxs-lookup"><span data-stu-id="f2905-117">The task is unknown.</span></span>|  
|`TT_USER`|<span data-ttu-id="f2905-118">Интерфейс представляет задачу пользователя.</span><span class="sxs-lookup"><span data-stu-id="f2905-118">The interface represents a user task.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f2905-119">Требования</span><span class="sxs-lookup"><span data-stu-id="f2905-119">Requirements</span></span>  
 <span data-ttu-id="f2905-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2905-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2905-121">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f2905-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2905-122">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f2905-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2905-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2905-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2905-124">См. также</span><span class="sxs-lookup"><span data-stu-id="f2905-124">See also</span></span>

- [<span data-ttu-id="f2905-125">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="f2905-125">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
