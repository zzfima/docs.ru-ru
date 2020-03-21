---
title: Перечисление EMemoryAvailable
ms.date: 03/30/2017
api_name:
- EMemoryAvailable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryAvailable
helpviewer_keywords:
- EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type:
- apiref
ms.openlocfilehash: 0073a532f680d8764ec9e76ea22326a630457043
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176439"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="acb51-102">Перечисление EMemoryAvailable</span><span class="sxs-lookup"><span data-stu-id="acb51-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="acb51-103">Содержит значения, указывающие количество свободной физической памяти на компьютере.</span><span class="sxs-lookup"><span data-stu-id="acb51-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="acb51-104">Эти значения логически отображают события для высокой и низкой памяти, возвращенные из `CreateMemoryResourceNotification` функции в API Windows.</span><span class="sxs-lookup"><span data-stu-id="acb51-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acb51-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="acb51-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="acb51-106">Члены</span><span class="sxs-lookup"><span data-stu-id="acb51-106">Members</span></span>  
  
|<span data-ttu-id="acb51-107">Участник</span><span class="sxs-lookup"><span data-stu-id="acb51-107">Member</span></span>|<span data-ttu-id="acb51-108">Описание</span><span class="sxs-lookup"><span data-stu-id="acb51-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="acb51-109">Много физической памяти доступно.</span><span class="sxs-lookup"><span data-stu-id="acb51-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="acb51-110">Очень мало физической памяти доступна.</span><span class="sxs-lookup"><span data-stu-id="acb51-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="acb51-111">Доступная физическая память нейтральна.</span><span class="sxs-lookup"><span data-stu-id="acb51-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acb51-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="acb51-112">Remarks</span></span>  
 <span data-ttu-id="acb51-113">Это значение передается хостом на общее время выполнения языка (CLR) с помощью вызова в метод [ICLRMemoryNotificationCallback::OnMemoryNotification.](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)</span><span class="sxs-lookup"><span data-stu-id="acb51-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acb51-114">Требования</span><span class="sxs-lookup"><span data-stu-id="acb51-114">Requirements</span></span>  
 <span data-ttu-id="acb51-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acb51-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acb51-116">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="acb51-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="acb51-117">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="acb51-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="acb51-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acb51-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acb51-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="acb51-119">See also</span></span>

- [<span data-ttu-id="acb51-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="acb51-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
