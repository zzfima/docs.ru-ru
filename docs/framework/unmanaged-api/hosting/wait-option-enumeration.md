---
title: Перечисление WAIT_OPTION
ms.date: 03/30/2017
api_name:
- WAIT_OPTION
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAIT_OPTION
helpviewer_keywords:
- WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type:
- apiref
ms.openlocfilehash: 9ecfb551b55551e5f6cc7e7e9ffb55e5a96259ee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141516"
---
# <a name="wait_option-enumeration"></a><span data-ttu-id="7934e-102">Перечисление WAIT_OPTION</span><span class="sxs-lookup"><span data-stu-id="7934e-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="7934e-103">Содержит значения, указывающие действие, которое должен выполнить узел при выполнении операции, запрашиваемой блоками среды CLR.</span><span class="sxs-lookup"><span data-stu-id="7934e-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7934e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7934e-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="7934e-105">Члены</span><span class="sxs-lookup"><span data-stu-id="7934e-105">Members</span></span>  
  
|<span data-ttu-id="7934e-106">Член</span><span class="sxs-lookup"><span data-stu-id="7934e-106">Member</span></span>|<span data-ttu-id="7934e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7934e-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="7934e-108">Уведомляет узел о том, что задача должна быть пробуждена, если среда CLR вызывает метод [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7934e-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="7934e-109">Уведомляет узел о том, что он должен передавать сообщения в текущем потоке операционной системы, если поток блокируется.</span><span class="sxs-lookup"><span data-stu-id="7934e-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="7934e-110">Среда выполнения задает это значение только в потоке <xref:System.Threading.ApartmentState.STA>.</span><span class="sxs-lookup"><span data-stu-id="7934e-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="7934e-111">Сообщает узлу, что указанный запрос на синхронизацию не может быть разбит узлом.</span><span class="sxs-lookup"><span data-stu-id="7934e-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="7934e-112">Это значит, что узел не может возвращать `HOST_E_DEADLOCK`.</span><span class="sxs-lookup"><span data-stu-id="7934e-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7934e-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="7934e-113">Remarks</span></span>  
 <span data-ttu-id="7934e-114">Методы [IHostTaskManager:: Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) и [IHostTaskManager:: свитчтотаск](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) принимают параметр этого типа.</span><span class="sxs-lookup"><span data-stu-id="7934e-114">The [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7934e-115">Требования</span><span class="sxs-lookup"><span data-stu-id="7934e-115">Requirements</span></span>  
 <span data-ttu-id="7934e-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7934e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7934e-117">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7934e-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7934e-118">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7934e-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7934e-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7934e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7934e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="7934e-120">See also</span></span>

- [<span data-ttu-id="7934e-121">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="7934e-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
