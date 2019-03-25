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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 55463985a7ac93bf0ec3cda92f91f8a326f92406
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410567"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="a1f33-102">Перечисление EMemoryAvailable</span><span class="sxs-lookup"><span data-stu-id="a1f33-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="a1f33-103">Содержит значения, указывающие объем свободной физической памяти на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a1f33-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="a1f33-104">Эти значения логически сопоставления с событиями для высокой и низкой память, возвращаемая вызовом `CreateMemoryResourceNotification` функции в Windows API.</span><span class="sxs-lookup"><span data-stu-id="a1f33-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1f33-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a1f33-105">Syntax</span></span>  
  
```  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="a1f33-106">Участники</span><span class="sxs-lookup"><span data-stu-id="a1f33-106">Members</span></span>  
  
|<span data-ttu-id="a1f33-107">Член</span><span class="sxs-lookup"><span data-stu-id="a1f33-107">Member</span></span>|<span data-ttu-id="a1f33-108">Описание</span><span class="sxs-lookup"><span data-stu-id="a1f33-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="a1f33-109">Доступно множество физической памяти.</span><span class="sxs-lookup"><span data-stu-id="a1f33-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="a1f33-110">Доступна очень мало физической памяти.</span><span class="sxs-lookup"><span data-stu-id="a1f33-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="a1f33-111">Доступная физическая память является нейтральным.</span><span class="sxs-lookup"><span data-stu-id="a1f33-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1f33-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="a1f33-112">Remarks</span></span>  
 <span data-ttu-id="a1f33-113">Это значение передается по основному приложению выполнения (CLR), используя вызов [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="a1f33-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1f33-114">Требования</span><span class="sxs-lookup"><span data-stu-id="a1f33-114">Requirements</span></span>  
 <span data-ttu-id="a1f33-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1f33-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1f33-116">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a1f33-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a1f33-117">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a1f33-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1f33-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1f33-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1f33-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a1f33-119">See also</span></span>
- [<span data-ttu-id="a1f33-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="a1f33-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
