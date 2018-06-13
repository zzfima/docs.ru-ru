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
ms.openlocfilehash: 139cf540617e278eeaae8a2a5acf10dd797d5d10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429890"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="e6f9c-102">Перечисление EMemoryAvailable</span><span class="sxs-lookup"><span data-stu-id="e6f9c-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="e6f9c-103">Содержит значения, указывающие объем свободной физической памяти на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e6f9c-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="e6f9c-104">Эти значения логически сопоставления с событиями для высокой и низкой памяти возвращается из `CreateMemoryResourceNotification` функции Win32 API.</span><span class="sxs-lookup"><span data-stu-id="e6f9c-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Win32 API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6f9c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6f9c-105">Syntax</span></span>  
  
```  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="e6f9c-106">Участники</span><span class="sxs-lookup"><span data-stu-id="e6f9c-106">Members</span></span>  
  
|<span data-ttu-id="e6f9c-107">Член</span><span class="sxs-lookup"><span data-stu-id="e6f9c-107">Member</span></span>|<span data-ttu-id="e6f9c-108">Описание</span><span class="sxs-lookup"><span data-stu-id="e6f9c-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="e6f9c-109">Доступно достаточное количество физической памяти.</span><span class="sxs-lookup"><span data-stu-id="e6f9c-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="e6f9c-110">Доступен физической памяти очень мало.</span><span class="sxs-lookup"><span data-stu-id="e6f9c-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="e6f9c-111">Объем доступной физической памяти нейтральной.</span><span class="sxs-lookup"><span data-stu-id="e6f9c-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6f9c-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="e6f9c-112">Remarks</span></span>  
 <span data-ttu-id="e6f9c-113">Это значение передается узлом для среды (CLR), с помощью вызова [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="e6f9c-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6f9c-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e6f9c-114">Requirements</span></span>  
 <span data-ttu-id="e6f9c-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6f9c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6f9c-116">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e6f9c-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6f9c-117">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e6f9c-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6f9c-118">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6f9c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6f9c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="e6f9c-119">See Also</span></span>  
 [<span data-ttu-id="e6f9c-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="e6f9c-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
