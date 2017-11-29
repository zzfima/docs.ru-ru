---
title: "Перечисление EMemoryAvailable"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EMemoryAvailable
api_location: mscoree.dll
api_type: COM
f1_keywords: EMemoryAvailable
helpviewer_keywords: EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c378f2cd9b033e578ff15472a10a6dc295ad6539
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="4e643-102">Перечисление EMemoryAvailable</span><span class="sxs-lookup"><span data-stu-id="4e643-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="4e643-103">Содержит значения, указывающие объем свободной физической памяти на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4e643-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="4e643-104">Эти значения логически сопоставления с событиями для высокой и низкой памяти возвращается из `CreateMemoryResourceNotification` функции Win32 API.</span><span class="sxs-lookup"><span data-stu-id="4e643-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Win32 API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e643-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e643-105">Syntax</span></span>  
  
```  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="4e643-106">Члены</span><span class="sxs-lookup"><span data-stu-id="4e643-106">Members</span></span>  
  
|<span data-ttu-id="4e643-107">Член</span><span class="sxs-lookup"><span data-stu-id="4e643-107">Member</span></span>|<span data-ttu-id="4e643-108">Описание</span><span class="sxs-lookup"><span data-stu-id="4e643-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="4e643-109">Доступно достаточное количество физической памяти.</span><span class="sxs-lookup"><span data-stu-id="4e643-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="4e643-110">Доступен физической памяти очень мало.</span><span class="sxs-lookup"><span data-stu-id="4e643-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="4e643-111">Объем доступной физической памяти нейтральной.</span><span class="sxs-lookup"><span data-stu-id="4e643-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e643-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="4e643-112">Remarks</span></span>  
 <span data-ttu-id="4e643-113">Это значение передается узлом для среды (CLR), с помощью вызова [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="4e643-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e643-114">Требования</span><span class="sxs-lookup"><span data-stu-id="4e643-114">Requirements</span></span>  
 <span data-ttu-id="4e643-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e643-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e643-116">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4e643-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4e643-117">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4e643-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e643-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e643-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e643-119">См. также</span><span class="sxs-lookup"><span data-stu-id="4e643-119">See Also</span></span>  
 [<span data-ttu-id="4e643-120">Перечисления размещения</span><span class="sxs-lookup"><span data-stu-id="4e643-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
