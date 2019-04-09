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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ac28f28d4d284ba26fadd46e53ebeb8e5b5f3cd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139585"
---
# <a name="waitoption-enumeration"></a><span data-ttu-id="febbb-102">Перечисление WAIT_OPTION</span><span class="sxs-lookup"><span data-stu-id="febbb-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="febbb-103">Содержит значения, указывающие, что действия узла следует предпринять операцию, запрошенную общих блоков языковой среды исполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="febbb-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="febbb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="febbb-104">Syntax</span></span>  
  
```  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="febbb-105">Участники</span><span class="sxs-lookup"><span data-stu-id="febbb-105">Members</span></span>  
  
|<span data-ttu-id="febbb-106">Член</span><span class="sxs-lookup"><span data-stu-id="febbb-106">Member</span></span>|<span data-ttu-id="febbb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="febbb-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="febbb-108">Уведомляет основное приложение, что задачи должны пробуждения, если среда CLR вызывает [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="febbb-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="febbb-109">Уведомляет основное приложение, что его необходимо передавать сообщения в текущем потоке операционной системы, если поток блокируется.</span><span class="sxs-lookup"><span data-stu-id="febbb-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="febbb-110">Среда выполнения задает это значение только в <xref:System.Threading.ApartmentState.STA> потока.</span><span class="sxs-lookup"><span data-stu-id="febbb-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="febbb-111">Уведомляет основное приложение, что узел не может блокировать заданный запрос синхронизации.</span><span class="sxs-lookup"><span data-stu-id="febbb-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="febbb-112">То есть узел не может возвращать `HOST_E_DEADLOCK`.</span><span class="sxs-lookup"><span data-stu-id="febbb-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="febbb-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="febbb-113">Remarks</span></span>  
 <span data-ttu-id="febbb-114">[IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) и [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) оба метода принимают параметр этого типа.</span><span class="sxs-lookup"><span data-stu-id="febbb-114">The [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="febbb-115">Требования</span><span class="sxs-lookup"><span data-stu-id="febbb-115">Requirements</span></span>  
 <span data-ttu-id="febbb-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="febbb-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="febbb-117">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="febbb-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="febbb-118">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="febbb-118">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="febbb-119">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="febbb-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="febbb-120">См. также</span><span class="sxs-lookup"><span data-stu-id="febbb-120">See also</span></span>

- [<span data-ttu-id="febbb-121">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="febbb-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
